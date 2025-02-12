---
title: Customer Journey Analytics FAQ
description: Customer Journey Analytics - 자주 묻는 질문
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
role: User
source-git-commit: 1bea6a1bc7d2070f01a60ef859675a0f9d03c86d
workflow-type: ht
source-wordcount: '2582'
ht-degree: 100%

---

# 자주 묻는 질문

Adobe Customer Journey Analytics는 차세대 분석 제품입니다. 이 문서에서는 Customer Journey Analytics와 관련하여 자주 묻는 질문에 대한 답변을 제공합니다. 자세한 내용은 [Customer Journey Analytics 기능 지원](/help/getting-started/aa-vs-cja/cja-aa.md)을 검토하십시오.

## 1. 사전 요구 사항 {#prerequisites}

+++**[!UICONTROL Customer Journey Analytics]에 [!UICONTROL Private Device Graph] 또는 [!UICONTROL Device Coop]가 필요합니까?**

아니요. [!UICONTROL Customer Journey Analytics]에는 [!UICONTROL Private Device Graph] 또는 [!UICONTROL Device Coop]가 필요하지 않습니다. 실제로 아직 지원되지 않습니다.

+++


+++**[!UICONTROL Customer Journey Analytics]에 [!UICONTROL Experience Cloud ID] (ECID)가 필요합니까?**

아니요. [!UICONTROL Customer Journey Analytics]는 데이터 세트에서 선택한 ID가 ECID든 다른 ID이든 모두 지원합니다.

+++


+++**[!UICONTROL Customer Journey Analytics] 전에 데이터를 ETL(추출, 변환, 로드)해야 하는 경우엔 어떻게 해야 합니까?**

Customer Journey Analytics에는 [데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=ko-KR) 기능이 포함되어 있으므로 데이터를 Adobe Experience Platform 데이터 레이크에 삽입하기 전에 데이터를 변환할 수 있습니다. 이미 데이터를 수집한 후 ETL이 필요한 경우 [Adobe Experience Platform 쿼리 서비스](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=ko-KR#queries)에서 일부 제한된 옵션을 제공합니다. 단, 이 경우 추가 비용이 발생할 수 있습니다.

+++


## 2. 데이터 결합 {#stitching}

+++**[!UICONTROL Customer Journey Analytics]를 디바이스 또는 데이터 세트 간에 “결합”할 수 있습니까?**

예. [!UICONTROL Customer Journey Analytics]의 [결합](../stitching/overview.md) 기능은 데이터 세트 내 인증된 이벤트와 인증되지 않은 이벤트에서 작동합니다. 이 연결을 통해 개인 수준에서 결합된 단일 ID에 대한 개별 레코드 문제를 해결하고 크로스 디바이스 관점에서 분석할 수 있습니다.
또한 공통 네임스페이스 ID(개인 ID)가 [연결](/help/connections/overview.md) 내 데이터 세트에서 사용되는 경우 개인 수준에서 “연결된” 여러 데이터 세트를 매끄럽게 결합하고 이에 대한 분석을 실행할 수 있습니다.

+++


+++**익명 동작에서 인증 동작으로 결합하는 작업이 지원됩니까?**

예. [결합](../stitching/overview.md)은 인증된 세션과 인증되지 않은 세션의 사용자 데이터를 확인하여 결합된 ID를 생성합니다.

+++


+++**결합에서 “재생”은 어떻게 작동합니까?**

결합은 학습한 고유 식별자를 기반으로 데이터를 “재생”합니다. 재생은 그 동안 식별된 디바이스에서 초기에 인증되지 않은 이벤트를 결합하는 것을 목표로 합니다. [자세히 알아보기](../stitching/overview.md)

+++


+++**내역 데이터(채우기)의 결합은 어떻게 작동합니까?**

처음으로 활성화할 때 Adobe는 사용자가 선택한 범위(사용 권한이 있는 Customer Journey Analytics 패키지에 따라 최대 25개월)까지 연결된 데이터의 채우기를 제공합니다. 이 채우기 작업을 수행하려면 오래된 결합되지 않은 데이터에 임시 ID가 있어야 합니다. [자세히 알아보기](../stitching/overview.md)

+++


+++**연결되지 않은 프로필 데이터 세트 레코드에 대한 예상 동작은 무엇입니까?**

**예시 상황**: 개인 ID로 `CRMid`를 사용하여 Customer Journey Analytics 연결에서 2개의 데이터 세트를 결합합니다. 하나는 모든 레코드에서 `CRMid`를 가진 웹 이벤트 데이터 세트입니다. 다른 하나는 CRM 프로필 데이터 세트입니다. CRM 데이터 세트의 40%가 웹 이벤트 데이터 세트에 있는 `CRMid`를 갖습니다. 다른 60%는 웹 이벤트 데이터 세트에 없습니다. 이들 레코드가 Analysis Workspace의 보고에 표시됩니까?<p> **답변**: 연결된 이벤트가 없는 프로필 행은 Customer Journey Analytics에 저장됩니다. 단, 해당 ID에 연결된 이벤트가 나타날 때까지 Analysis Workspace에서 이를 조회할 수 없습니다.

+++

## 3. [!UICONTROL Customer Journey Analytics]에 데이터 가져오기 {#ingest}

+++**하나의 [!UICONTROL Customer Journey Analytics] 연결에 다른 [!UICONTROL Adobe Experience Platform] 샌드박스의 데이터를 결합할 수 있습니까?**

아니요. 샌드박스에서 데이터에 액세스할 수 없습니다. 동일한 샌드박스 내에 있는 데이터 세트만 결합할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ko-KR#select-sandbox-and-datasets)

+++


+++**[!UICONTROL Customer Journey Analytics]에서 온라인 데이터를 오프라인 데이터로 어떻게 연결합니까?**

개인 ID가 데이터 세트 간에 일치하는 경우 [!UICONTROL Customer Journey Analytics]는 전체 데이터 세트에서 필터, 기여도, 흐름, 폴아웃 등을 연결할 수 있습니다.

+++


+++**오프라인 데이터를 [!UICONTROL Customer Journey Analytics]로 가져오려면 어떻게 해야 합니까?**

Customer Journey Analytics에 대한 자격 증명을 통해 데이터를 Experience Platform에 수집할 수 있습니다. 그런 다음 Analysis Workspace에서의 보고를 위해 [!UICONTROL Customer Journey Analytics]에서 해당 데이터 및 데이터 보기에 대한 연결을 만들 수 있습니다. 필요한 경우 Experience Platform의 데이터 온보딩팀에서 추천이나 컨설팅 서비스를 제공할 수 있습니다.

+++


+++**[!UICONTROL Adobe Analytics] 데이터를 [!UICONTROL Customer Journey Analytics]로 가져오려면 어떻게 해야 합니까?**

[!UICONTROL Adobe Analytics] 데이터는 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR)를 통해 Experience Platform에 연결할 수 있습니다. [!UICONTROL Adobe Analytics] 필드는 대부분 XDM 형식으로 가져오지만 다른 필드는 아직 사용할 수 없습니다.

+++


+++**데이터 세트 요소를 데이터 보기로 취합하는 데 얼마나 걸립니까?**

시작하는 데 몇 시간이 소요되고 지난 13개월간의 데이터를 채우는 데는 며칠이 소요됩니다.

+++


+++**데이터 간의 연결을 설정하려면 PII 데이터를 가져와야 합니까?**

아니요. PII가 아닌 고객 ID의 해시를 포함하여 모든 ID를 사용할 수 있습니다.

+++


+++**과거 또는 미래 날짜/타임스탬프를 Customer Journey Analytics 이벤트 데이터 세트로 수집하는 것에 대한 제한은 얼마입니까?**

* 과거 날짜/타임스탬프 관련: 최대 10년 이전의 이벤트 데이터.
* 미래 날짜/타임스탬프 관련: 최대 1개월 후의 이벤트 데이터(예측).

+++


## 4. 지연 고려 사항 {#latency}

>[!NOTE]
>
>Customer Journey Analytics에는 고정된 데이터 크기가 없으므로 Adobe는 표준 수집 시간을 약속할 수 없습니다. Adobe는 새로운 업데이트와 수집 최적화를 통해 이러한 지연 시간을 줄이기 위해 적극적으로 노력하고 있습니다.

* 라이브 데이터 또는 이벤트: Adobe Experience Platform에서 데이터를 사용할 수 있게 되면 90분 이내에 처리 및 수집됩니다. (배치 크기가 5,000만 행 이상: 90분 이상) 스티칭이 활성화된 경우 수집에 최대 4시간 정도 소요될 수 있습니다. 자세한 내용은 [가드레일](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/technotes/guardrails)을 참조하십시오.
* 소규모 채우기: 7일 이내
* 대규모 채우기: 30일 이내

최근 Customer Journey Analytics에서 데이터를 처리하는 방법이 변경되었습니다.

* “현재” 날짜에 대한 이벤트 데이터는 라이브 데이터로 스트리밍됩니다. 전날 오후 11:59:59(23:59:59) 이전의 이벤트 시간을 포함하는 모든 데이터는 채우기로 처리됩니다.
* 타임스탬프가 24시간 이상 지난 모든 이벤트 데이터(최신 데이터와 동일한 배치에 있는 경우 포함)는 채우기로 간주되며 낮은 우선 순위로 수집됩니다.

## 5. [!UICONTROL 연결] 데이터 보존에 대한 롤링 기간 설정 {#data-retention}

[**[!UICONTROL 롤링 데이터 기간 활성화&#x200B;]**설정](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#create-connection)을 사용하면 Customer Journey Analytics 데이터 보존을 개월(3개월, 6개월 등) 단위의 롤링 기간으로 정의할 수 있습니다. [!UICONTROL 데이터 세트] 수준이 아닌 [!UICONTROL 연결] 수준에서 설정됩니다. 데이터 보존은 이벤트 데이터 세트 타임스탬프를 기반으로 하며 이벤트 데이터 세트에만 적용됩니다. 적용 가능한 타임스탬프가 없기 때문에 프로필 또는 조회 데이터 세트에 대한 데이터 보존 설정은 없습니다.

주요 이점은 적용 가능하고 유용한 데이터에 대해서만 저장하거나 보고하고 더 이상 유용하지 않은 오래된 데이터를 삭제한다는 것입니다. 계약 한도를 유지하고 초과 비용의 위험을 줄이는 데 도움이 됩니다.

## 6. 데이터 구성 요소 삭제의 영향 {#deletion}

데이터 삭제는 여섯 가지 유형의 구성 요소인 샌드박스, 스키마, 데이터 세트, 연결, 데이터 보기, 작업 영역 프로젝트를 고려해야 합니다. 다음은 이러한 구성 요소 중 하나를 삭제하는 것과 관련된 몇 가지 가능한 시나리오입니다.

| 다음 작업을 수행하는 경우 | 발생하는 결과 |
| --- | --- |
| [!UICONTROL Adobe Experience Platform]에서 샌드박스 삭제 | 샌드박스를 삭제하면 해당 샌드박스의 데이터 세트에 대한 [!UICONTROL Customer Journey Analytics] 연결로의 데이터 흐름이 정지됩니다. 삭제된 샌드박스와 관련된 연결, 데이터 보기, 지표 및 차원도 삭제됩니다. | |
| [!UICONTROL Adobe Experience Platform]에서 스키마를 삭제하지만 이 스키마와 연결된 데이터 세트는 삭제하지 않음 | [!UICONTROL Adobe Experience Platform]에서는 연관된 [!UICONTROL 데이터 세트]가 하나 이상 있는 [!UICONTROL 스키마]를 삭제할 수 없습니다. 그러나 적절한 권한 세트가 있는 관리자는 먼저 데이터 세트를 삭제한 다음 스키마를 삭제할 수 있습니다. |
| [!UICONTROL Adobe Experience Platform] 데이터 레이크에서 데이터 세트 삭제 | Adobe Experience Platform 데이터 레이크에서 데이터 세트를 삭제하면 해당 데이터 세트에서 해당 데이터 세트를 포함하는 Customer Journey Analytics 연결로의 데이터 흐름이 중지됩니다. 해당 데이터 세트의 데이터는 연관된 Customer Journey Analytics 연결에서 자동으로 삭제됩니다. |
| [!UICONTROL Customer Journey Analytics]에서 데이터 세트 삭제 | 저장된 연결 내에서 데이터 세트를 삭제하는 프로세스를 진행하려면 Adobe 계정 팀에 문의하십시오. |
| [!UICONTROL Adobe Experience Platform]의 데이터 세트에서 배치를 삭제 | [!UICONTROL Adobe Experience Platform] 데이터 세트에서 일괄 처리가 삭제되면 해당 특정 일괄 처리가 들어 있는 Customer Journey Analytics 연결에서 동일한 일괄 처리가 제거됩니다. Customer Journey Analytics는 [!UICONTROL Adobe Experience Platform]에서 일괄 삭제 알림을 수신합니다. |
| 배치를 **Customer Journey Analytics**&#x200B;에 [!UICONTROL 수집하는 동안] 배치를 삭제 | 데이터 세트에 일괄 처리가 한 개만 있는 경우 해당 일괄 처리의 데이터가 [!UICONTROL Customer Journey Analytics]에서 전혀 표시되지 않거나 일부 표시됩니다. 수집이 롤백됩니다. 데이터 세트에 5개의 일괄 처리가 있고 그 중 3개가 이미 데이터 세트를 삭제할 때 수집된 경우 해당 3개 일괄 처리의 데이터가 [!UICONTROL Customer Journey Analytics]에 표시됩니다. |
| [!UICONTROL Customer Journey Analytics]에서 연결을 삭제 | 오류 메시지에 다음 내용이 표시됩니다.<ul><li>삭제된 연결에 대해 만들어진 모든 데이터 보기가 더 이상 작동하지 않습니다.</li><li> 마찬가지로, 삭제된 연결의 데이터 보기에 의존하는 모든 Workspace 프로젝트의 작동이 중지됩니다.</li></ul> |
| [!UICONTROL Customer Journey Analytics]에서 데이터 보기를 삭제 | 이 삭제된 데이터 보기에 의존하는 모든 Workspace 프로젝트의 작동이 중지된다는 오류 메시지가 표시됩니다. |

## 7. Customer Journey Analytics에서 보고서 세트 병합 시 고려 사항 {#merge-reportsuite}

[Adobe Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR)를 통해 Adobe Analytics 데이터를 수집하여 2개 이상의 Adobe Analytics 보고서 세트를 병합할 경우 해당 결과를 고려하십시오.

| 문제 | 고려 사항 |
| --- | --- |
| 변수 | 보고서 세트에 [!UICONTROL eVar]와 같은 변수를 정렬할 수 없습니다. 예를 들어 보고서 세트 1의 eVar1은 **[!UICONTROL 페이지]**&#x200B;를 지정할 수 있습니다. eVar1이 보고서 세트2에서 **[!UICONTROL 내부 캠페인]**&#x200B;을 지정하는 경우 보고가 혼합되고 정확하지 않을 수 있습니다. |
| [!UICONTROL 세션] 및 [!UICONTROL 인원] 수 | 보고서 세트에 대해서는 중복 제거되지 않습니다. 결과적으로 수는 일치하지 않을 수 있습니다. |
| 지표 중복 제거 | 여러 행에 동일한 거래 ID(예: [!UICONTROL 구매 ID])가 있는 경우 지표의 인스턴스(예: [!UICONTROL 주문])를 중복 제거합니다. 이로써 주요 지표의 초과 계산을 방지합니다. 따라서 보고서 세트에서 [!UICONTROL 주문]과 같은 지표를 추가할 수 없습니다. |
| 통화 | 통화 전환은 Customer Journey Analytics에서 지원되지 않습니다. 병합하려는 보고서 세트가 서로 다른 기본 통화를 사용하는 경우 문제가 발생할 수 있습니다. |
| [!UICONTROL 지속성] | [지속성](../data-views/component-settings/persistence.md)이 보고서 세트 전반에 확장되어 [!UICONTROL 필터] [!UICONTROL 속성] 등에 영향을 미칩니다. 번호가 제대로 추가될 수 없습니다. |
| [!UICONTROL 분류] | [!UICONTROL 분류]: 보고서 세트를 병합하는 경우 자동으로 중복 제거되지 않습니다. 여러 분류 파일을 단일 [!UICONTROL 조회] 데이터 세트에 결합하는 경우 문제가 발생할 수 있습니다. |

## 8. [!UICONTROL Adobe Analytics] 구성 요소

+++**[!DNL Customer Journey Analytics]에서 Experience Platform Real-Time CDP 또는 기타 Experience Cloud 애플리케이션으로 [!UICONTROL 대상자]를 공유/게시할 수 있습니까?**

고객 타기팅 및 맞춤화를 위해 Customer Journey Analytics에서 식별된 [대상자를 Adobe Experience Platform의 실시간 고객 프로필을 만들어 게시](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-components/audiences/publish)할 수 있습니다.

+++

+++**이전 [!UICONTROL eVar] 설정은 어떻게 됩니까?**

Adobe Analytics 센스의 [!UICONTROL eVar], [!UICONTROL 속성], [!UICONTROL 이벤트]는 [!UICONTROL Customer Journey Analytics]에 더 이상 존재하지 않습니다. 무제한 스키마 요소(차원, 지표, 목록 필드)가 있습니다. 따라서 이제 데이터 수집 프로세스 동안 적용했던 모든 속성 설정이 쿼리 시간에 적용됩니다.

+++

+++**모든 세션 및 변수 지속성 설정은 현재 어디에 있습니까?**

[!UICONTROL Customer Journey Analytics]의 경우 이러한 모든 설정은 보고서 시간에 적용되며 데이터 보기에 있습니다. 이제 이러한 설정을 변경하면 소급 적용되며, 여러 데이터 보기를 사용하여 여러 버전을 보유할 수 있습니다.

+++

+++**기존 세그먼트/계산된 지표는 어떻게 됩니까?**

[!UICONTROL Customer Journey Analytics]는 더 이상 eVar, 속성 또는 이벤트를 사용하지 않고 대신 Adobe Experience Platform 스키마를 사용합니다. 즉, 기존 세그먼트나 계산된 지표는 [!UICONTROL Customer Journey Analytics]와 호환되지 않습니다.

+++

+++**[!UICONTROL Customer Journey Analytics]는 `Uniques Exceeded` 제한 사항을 어떻게 처리합니까?**

[!UICONTROL Customer Journey Analytics에는 고유 값 제한이 없으므로 걱정할 필요가 없습니다.]

+++

+++**기존 [!DNL Data Workbench] 고객은 바로 Customer Journey Analytics로 이동할 수 있습니까?**

사용 사례에 따라 다릅니다. Adobe 계정 팀의 도움을 받으십시오. 현재 사용 사례가 이미 Customer Journey Analytics에 적합할 수도 있습니다.

+++

## 9. 연결 크기 예측 {#estimate-size}

[사용량 예측 및 관리](/help/technotes/estimate-usage.md)를 참조하십시오.

## 10. 사용 초과에 관한 사항 {#overage}

사용 제한은 Adobe에서 정기적으로 모니터링하고 시행합니다. “데이터 행”은 Customer Journey Analytics 내에서 분석에 사용할 수 있는 데이터의 일일 평균 행을 의미합니다.

예를 들어 계약에 따라 1백만 행의 데이터에 대한 권한이 있습니다. Customer Journey Analytics를 사용한 첫 날에 2백만 행의 데이터를 업로드한다고 가정해 보겠습니다. 2일째에는 1백만 행을 삭제하고 라이선스 기간이 끝날 때까지 약정된 최대값(즉, 1백만 행의 데이터)으로 사용량을 유지합니다. 계약 조건에 따라 “데이터 행”에 대한 라이선스 권한을 초과했기 때문에 일할 계산된 1일 차 초과 사용 요금이 부과될 수 있습니다.

## 11. 데이터 불일치 진단 {#discrepancies}

경우에 따라 연결에서 수집된 총 이벤트 수가 [!UICONTROL Adobe Experience Platform]의 데이터 세트에 있는 행 수와 다를 수 있습니다. 이 예에서 데이터 세트 “B2B 노출 횟수”에는 7650개의 행이 있지만 데이터 세트에 [!UICONTROL Adobe Experience Platform]의 3830개의 행이 포함됩니다. 불일치 발생에는 몇 가지 이유가 있으며 다음 단계를 수행하여 진단할 수 있습니다.

1. 이 차원을 **[!UICONTROL 플랫폼 데이터 세트 ID]**&#x200B;로 분류하면 크기가 같지만 다른 **[!UICONTROL 플랫폼 데이터 세트 ID]**&#x200B;를 사용하는 데이터 세트가 2개 있음을 알 수 있습니다. 각 데이터 세트에 3825개의 레코드가 있습니다. 즉, 개인 ID가 없거나 타임스탬프가 누락되어 [!UICONTROL Customer Journey Analytics]에서 5개의 레코드를 무시했습니다.

   ![breakdown](assets/data-size2.png)

1. 또한 [!UICONTROL Adobe Experience Platform]에서 체크인하는 경우 첫 연결이 만들어졌을 때 누군가 이 특정 데이터 세트를 [!UICONTROL Adobe Experience Platform]에서 삭제했으므로 ID가 “5f21c12b732044194bffc1d0”인 데이터 세트가 없습니다. 나중에, Customer Journey Analytics에 다시 추가되었지만 다른 [!UICONTROL 플랫폼 데이터 세트 ID]가 [!UICONTROL Adobe Experience Platform]에 의해 생성되었습니다.

[!UICONTROL Customer Journey Analytics] 및 [!UICONTROL Adobe Experience Platform]의 [데이터 세트 및 연결 삭제에 대한 의미](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ko-KR#implications-of-deleting-data-components)에 관하여 자세히 읽어보십시오.


## 12. 지역 데이터 수집

Adobe Experience Cloud는 RDC(지역 데이터 수집)를 사용하므로 방문자와 Adobe 및 Adobe 이외의 솔루션 간의 상호 작용이 방문자에게 가까운 위치에서 발생할 수 있습니다. 데이터가 데이터 수집 센터(DCC, Platform Edge Network의 일부인 에지 사이트라고도 함)에 지역적으로 수집되면 데이터스트림 및/또는 이벤트 전달 구성을 기반으로 보안 연결을 통해 관련 솔루션으로 전달됩니다.

![Data flow using Edge Networks](https://experienceleague.adobe.com/docs/experience-platform/assets/collection.png)

지역 데이터 수집 프로세스는 다음과 같은 단계를 사용합니다.

1. DNS는 방문자에게 가장 가까운 데이터 수집 센터의 IP 주소에 대한 수집 호스트 이름을 자동으로 확인합니다.
1. 방문자가 이 위치로 데이터를 보냅니다.
1. 데이터는 보안 연결을 통해 데이터스트림 또는 이벤트 전달 구성에 의해 정의된 솔루션으로 즉시 전달됩니다.

지역 데이터 수집을 사용하면 다음과 같은 몇 가지 이점이 있습니다.

* **성능**: RDC를 사용하면 방문자가 가장 가까운 DCC에 연결됩니다. 이러한 최적화를 통해 추적이 더 정확해지고 로딩 시간이 더 빨라집니다.
* **중복**: DCC와 DPC 간의 통신이 중단되면 Adobe의 RDC 인프라에서 데이터를 로컬에 저장했다가 통신이 복원될 때 DPC로 전달합니다.

현재 RDC에는 다음 위치(변경될 수 있음)가 포함되어 있습니다.


| RDC 유형 | 데이터 수집 센터 |
| --- | --- |
| 글로벌 (기본값) | 오리건, 버지니아, 아일랜드, 파리, 뭄바이, 싱가포르, 도쿄, 시드니 |
| 아메리카만 | 오리건, 버지니아 |
| 유럽만 | 아일랜드, 파리 |
| 아시아 태평양만 | 뭄바이, 싱가포르, 도쿄, 시드니 |

{style="table-layout:auto"}

데이터가 지역 데이터 센터를 히트하면 데이터스트림 구성에 따라 데이터가 추가로 라우팅되는 방식이 결정됩니다.

Customer Journey Analytics에는 Adobe Experience Platform의 데이터 세트가 필요하므로 데이터스트림/이벤트 전달 구성에는 지역 데이터 센터에서 Adobe Experience Platform 인스턴스가 위치한 데이터 센터로 데이터를 라우팅하는 Adobe Experience Platform 서비스가 필요합니다. Customer Journey Analytics와 지원 서비스 및 인프라는 동일한 Adobe Experience Platform 인스턴스에 배포됩니다.


Adobe Experience Platform Edge Network 및 지역 데이터 센터 외부의 데이터 수집 프로세스에 대한 자세한 내용은 [데이터 수집 개요](https://experienceleague.adobe.com/docs/experience-platform/collection/home.html)를 참조하십시오.
