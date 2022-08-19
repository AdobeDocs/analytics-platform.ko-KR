---
description: CJA 실험 패널에서 A/B 테스트 결과를 분석하는 방법에 대해 알아봅니다.
title: 실험 패널
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 57a52c21b1850574e5d85ab560fb5399f9b37631
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 8%

---

# 실험 패널

>[!NOTE]
>
>이 기능은 현재 [제한적인 테스트](/help/release-notes/releases.md)가 실시되고 있습니다.

다음 **[!UICONTROL 실험]** 패널을 사용하면 분석가가 서로 다른 사용자 경험, 마케팅 또는 메시지 변형을 비교하여 특정 결과를 도출하는 데 가장 적합한 경험을 결정할 수 있습니다. 온라인, 오프라인, Adobe 솔루션, Adobe Journey Optimizer 및 BYO(직접 가져오기) 데이터에서 모든 실험 플랫폼에서 A/B 실험의 향상도와 신뢰도를 평가할 수 있습니다.

>[!IMPORTANT]
>
>이 시점에서 [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=ko-KR) (A4T) 데이터를 Analytics 소스 커넥터를 통해 Adobe Experience Platform에 가져왔습니다 **사용할 수 없음** 에서 분석 [!UICONTROL 실험] 패널. 우리는 2023년에 이 문제에 대한 해결을 기대한다.

## 액세스 제어

실험 패널은 모든 Customer Journey Analytics(CJA) 사용자가 사용할 수 있습니다. 관리자 권한 또는 기타 권한이 필요하지 않습니다. 그러나 설정(1~2단계)에는 관리자만 수행할 수 있는 작업이 필요합니다.

## 1단계: 실험 데이터 세트에 대한 연결 만들기

실험 데이터가 [수집된 항목](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) Adobe Experience Platform에 [cja에서 연결 만들기](/help/connections/create-connection.md) 하나 이상의 실험 데이터 세트에 매핑해야 합니다.

## 2단계: 데이터 보기에 컨텍스트 레이블 추가

CJA 데이터 보기 설정에서 관리자는 [컨텍스트 레이블](/help/data-views/component-settings/overview.md) 다음과 같은 차원 또는 지표 및 CJA 서비스에 연결할 수 있습니다. [!UICONTROL 실험] 패널은 이러한 레이블을 용도 대로 사용할 수 있습니다. 실험 패널에 두 개의 사전 정의된 레이블이 사용됩니다.

* [!UICONTROL 실험]
* [!UICONTROL 변형]

실험 데이터가 포함된 데이터 뷰에서 실험 데이터가 있는 차원 및 변형 데이터가 있는 차원 2개를 선택합니다. 그런 다음 로 해당 차원에 레이블을 지정합니다. **[!UICONTROL 실험]** 그리고 **[!UICONTROL 변형]** 레이블.

![컨텍스트 레이블](assets/context-label.png)

이러한 레이블이 없으면 사용할 실험이 없으므로 실험 패널이 작동하지 않습니다.

## 3단계: 실험 패널 구성

1. CJA Workspace에서 실험 패널을 프로젝트로 드래그합니다.

![실험 패널](assets/experiment.png)

>[!IMPORTANT]
>CJA 데이터 보기의 필요한 설정이 완료되지 않은 경우 계속하기 전에 해당 효과에 대한 메시지를 받게 됩니다.

1. 패널 입력 설정을 구성합니다.

   | 설정 | 정의 |
   | --- | --- |
   | **[!UICONTROL 실험]** | 어떤 것이 영속적으로 유지되는지를 결정하기 위해 최종 사용자에게 노출된 경험에 대한 변형 세트입니다. 실험은 2개 이상의 변형으로 구성되며, 그중 하나가 제어 변형으로 간주됩니다. 이 설정은  **[!UICONTROL 실험]** 데이터 보기에 있는 레이블 및 최근 3개월 동안의 실험 데이터 값입니다. |
   | **[!UICONTROL 컨트롤 변형]** | 더 나은 대체 요소를 식별하기 위해 비교되고 있는 최종 사용자의 경험에 대한 두 가지 이상 변경 중 하나. 하나의 변형을 제어로 선택해야 하며 하나의 변형은 제어 변형으로 간주할 수 있습니다. 이 설정은  **[!UICONTROL 변형]** 데이터 보기의 레이블. 이 설정은 이 실험과 연결된 변형 데이터를 가져옵니다. |
   | **[!UICONTROL 성공 지표 를 참조하십시오]** | 사용자가 변형을 비교하는 지표 또는 지표입니다. 전환 지표에 가장 적합한 결과(가장 높든 낮든)를 가진 변형은 실험의 &quot;가장 성과가 좋은 변형&quot;으로 선언됩니다. 최대 5개의 지표를 추가할 수 있습니다. |
   | **[!UICONTROL 표준화 지표]** | 기준 ([!UICONTROL 사람], [!UICONTROL 세션], 또는 [!UICONTROL 이벤트]) 테스트 실행 예를 들어, 테스트에서는 다음과 같은 여러 변형의 전환율을 비교할 수 있습니다. **[!UICONTROL 전환율]** 는 **[!UICONTROL 세션당 전환 수]** 또는 **[!UICONTROL 1인당 전환]**. |

1. **[!UICONTROL 빌드]**&#x200B;를 클릭합니다.

## 4단계: 패널 출력 해석

실험 패널은 실험이 수행하는 방식을 더 잘 이해할 수 있도록 풍부한 데이터 및 시각화 세트를 반환합니다. 패널 맨 위에는 선택한 패널 설정을 알려 주는 요약 줄이 제공됩니다. 언제든지 오른쪽 상단의 연필 편집을 클릭하여 패널을 편집할 수 있습니다.

또한 실험 결과가 확정되었는지 여부를 나타내는 텍스트 요약을 얻을 수 있으며 결과를 요약합니다. 결론은 통계적 중요도에 기초한다. (아래의 &quot;통계적 방법론&quot;을 참조하십시오.) 상승도 및 신뢰도가 가장 높은 성과가 가장 좋은 변형에 대한 요약 번호를 볼 수 있습니다.

>[!NOTE]
>
>향상도와 신뢰도는 CJA에서 고급 계산된 지표 기능이므로 향상도와 신뢰도 지표를 작성할 수 있습니다.

![실험 출력](assets/exp-output1.png)

선택한 각 성공 지표에 대해 하나의 자유 형식 테이블 및 하나의 전환 비율 트렌드가 표시됩니다.

![실험 출력](assets/exp-output2.png)

다음 [!UICONTROL 라인] 차트를 통해 [!UICONTROL 제어] 비교 [!UICONTROL 컨트롤 변형] 성능:

![실험 출력](assets/exp-output3.png)


## 통계적 방법론

팔로우.



