---
title: Customer Journey Analytics 잘못된 ID
description: Customer Journey Analytics의 잘못된 ID(BAVID) 이해 데이터에서 잘못된 ID를 식별하는 방법, 보고에 영향을 주는 이유 및 연결에서 잘못된 ID 노출을 조사하고 해결하는 방법에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: b7b2a1f3eb1c149caf65ab3e4321e4f4347695cc
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 0%

---


# 잘못된 ID

이 문서에서는 쿼리 서비스를 사용하여 잘못된 ID에 대한 컨텍스트와 데이터의 존재 또는 발생 위험을 감지하는 방법을 제공합니다.


>[!INFO]
>
>Customer Journey Analytics 인터페이스에서 잘못된 ID는 BAVID라고도 합니다([Analytics BAVID](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16444)부터 시작).
>

## 정의

Customer Journey Analytics에서 잘못된 ID는 연결에 정의된 모든 데이터의 일부인 식별자입니다.

* (출처: 특정 ID 값)
   * 개인 ID 필드(연결되지 않은 데이터 세트)에서 **또는**
   * 영구 ID 또는 개인 ID 필드(결합이 활성화된 데이터 세트)에서

  **및**
* 는 한 달 내에 연결 데이터(연결 내의 모든 데이터 세트에 대해 계산됨)의 1백만 개 이상의 이벤트(100만 개)에 있습니다.

ID 값이 잘못된 ID로 표시되면 해당 ID 값이 포함된 이후 이벤트는 연결 데이터에서 삭제되고 보고에 표시되지 않습니다.

### 예

잘못된 ID 시나리오의 예로는 개인 ID 필드에 사용자 지정 또는 자리 표시자 값이 있습니다(예: 익명 트래픽의 경우 `undefined`). 결합이 활성화된 데이터 세트의 경우 결합 품질에 가장 큰 영향을 미칠 수 있으므로 이 상황은 보고 데이터에 훨씬 더 큰 영향을 줄 수 있습니다. 이 문제를 해결하려면 연결에서 데이터 세트 내역 데이터를 삭제하는 등 결합 설정을 지우고 다시 활성화해야 할 수 있습니다.


## 지표

Customer Journey Analytics 연결 인터페이스는 인터페이스의 여러 위치에서 **[!UICONTROL 잘못된 ID]** 지표 정보를 제공합니다.

* **[!UICONTROL 건너뛴 세부 정보 확인]** 대화 상자에서 레코드를 건너뛰는 가능한 이유로 **[!UICONTROL 잘못된 ID]**(또는 **[!UICONTROL BAVID]**)를 볼 수 있습니다. 연결의 **[!UICONTROL 세부 정보 화면에서]**&#x200B;생략된 레코드&#x200B;**[!UICONTROL 아래의]**&#x200B;세부 정보 확인[(가능한 경우)을 사용합니다](/help/connections/create-connection.md).
* 연결이 활성화된 데이터 세트의 경우 [**[!UICONTROL 데이터 세트 미리 보기]**](/help/stitching/use-stitching-ui.md#bad-ids)에 **[!UICONTROL 연결 지표]**&#x200B;의 일부로 **[!UICONTROL 잘못된 ID]**&#x200B;이(가) 표시됩니다. 이 지표는 가능한 잘못된 ID 사례를 식별하는 데 도움이 될 수 있습니다. 그러나 이 지표는 제한된 데이터 세트를 기반으로 계산됩니다.

연결 내에서 사용할 데이터 세트에 대해 잘못된 ID가 있는지 식별하려면 [잘못된 ID 노출](#bad-ids-exposure)을 참조하십시오(연결이 활성화되었는지 여부에 상관없이).


## 노출

특정 데이터 세트 필드에 대한 잘못된 ID 노출을 조사하려면 Experience Platform 쿼리 서비스에서 다음 쿼리를 수행하는 것이 좋습니다. 반환된 상위 ID 값을 확인하여 잘못된 ID에 대한 후보가 있는지 확인하십시오. [잘못된 ID 정의](#definition)은(는) 연결 내의 모든 데이터 세트를 고려합니다.


### 필드 내에서 잘못된 ID 식별(위험)

Experience Platform 쿼리를 사용하여 필드 내에서 잘못된 ID의 잠재적 위험을 식별하는 서비스를 제공할 수 있습니다.

아래 쿼리는 필드의 처음 20개 ID 값을 반환합니다. 총 이벤트 수를 기준으로 내림차순으로 정렬됩니다. 각 값이 특정 간격(예: 최근 30일 이내) 내에 감지된 경우.

분석할 특정 개인 ID 필드에 대해 이 쿼리를 실행합니다. 결합이 필요한 데이터 세트의 경우 영구 ID 필드에 대한 쿼리를 실행할 수도 있습니다.

```sql
SELECT
    /* INSERT FIELD HERE */,
    COUNT(*) AS occurrences
FROM /* INSERT DATASET TABLE NAME HERE */
WHERE timestamp >= NOW() - INTERVAL '30 days' 
GROUP BY /* INSERT FIELD HERE */
ORDER BY occurrences DESC
LIMIT 20; 
```

쿼리에서 잘못된 ID를 조사하는 필드 유형에 따라 `INSERT FIELD HERE`을(를) 바꾸십시오.

* `full.field.path.from.XDM.schema`(XDM 스키마에 정의된 문자열 필드의 경우)
* `identityMap['namespace_value'][0].id`(`namespace_value`에서 `identityMap`(으)로 정의된 필드)

결과를 확인하여 문제가 있는 ID 값이 있는지 확인하십시오. 사용자 지정 또는 자리 표시자 값, 또는 연결 데이터 수준에서 한 달 내에 100만개에 도달하거나 근접할 수 있는 발생 빈도가 높은 값.
구현이 아직 개발 단계에 있더라도 설정이 안정되고 프로덕션이 준비되면 잘못된 ID가 존재할 위험을 평가해야 합니다.
