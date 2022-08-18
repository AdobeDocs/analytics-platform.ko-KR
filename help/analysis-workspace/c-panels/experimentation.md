---
description: CJA 실험 패널에서 A/B 테스트 결과를 분석하는 방법에 대해 알아봅니다.
title: 실험 패널
feature: Panels
source-git-commit: 2c217c7d31819ac8eb27d2d1010e0df787601e21
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---


# 실험 패널

>[!NOTE]
>
>이 기능은 현재 [제한적인 테스트](/help/release-notes/releases.md)가 실시되고 있습니다.

다음 **[!UICONTROL 실험]** 패널을 사용하면 다양한 사용자 경험, 마케팅 또는 메시지 변형을 비교하여 특정 결과를 도출하는 데 가장 적합한 경험을 결정할 수 있습니다. 온라인, 오프라인, Adobe 솔루션, Adobe Journey Optimizer 및 BYO(직접 가져오기) 데이터에서 모든 실험 플랫폼에서 A/B 실험의 향상도와 신뢰도를 평가할 수 있습니다.

>[!IMPORTANT]
>
>이 시점에서 [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=ko-KR) (A4T) 데이터는 [!UICONTROL 실험] 패널.

## 액세스 제어

모든 Customer Journey Analytics(CJA) 사용자가 실험 패널을 사용할 수 있습니다. 관리자 권한 또는 기타 권한이 필요하지 않습니다. 하지만, 설정을 사용하려면 관리자만 할당할 수 있는 데이터 보기에 레이블이 필요합니다.

## 용어

* **실험**: 실험은 영구적인 것이 가장 좋은 것을 결정하기 위해 최종 사용자에게 노출된 경험에 대한 변형들의 집합입니다. 실험은 둘 이상의 변형으로 구성되며, 그 중 하나는 제어 변형으로 간주됩니다.

* **변형**: 더 나은 대체 요소를 식별하기 위해 비교되고 있는 최종 사용자의 경험에 대한 두 가지 이상 변경 중 하나. 하나의 변형을 제어로 선택해야 하고 하나의 변형이 제어 변형으로 간주될 수 있습니다.

* **제어**: 현재 상태나 사용자 경험의 기본 상태를 나타내는 특정 변수입니다. 다른 모든 변형이 비교되고 있습니다.

* **지표 정규화**: 테스트가 실행될 기준(세션 또는 사람)입니다. 예를 들어, 테스트에서는 전환율이 세션당 전환으로 계산되거나 1인당 전환으로 계산되는 여러 변형의 전환율을 비교할 수 있습니다.

* **전환 지표**: 사용자가 변형을 비교하고 있는 지표입니다. 전환 지표에 대해 가장 바람직한 결과를 갖는 변형(가장 높든 낮든)은 실험의 &quot;우승자&quot;로 선언됩니다.

## 1단계: 실험 데이터 세트에 대한 연결 만들기

실험 데이터가 [수집된 항목](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) Adobe Experience Platform에 [cja에서 연결 만들기](/help/connections/create-connection.md) 하나 이상의 실험 데이터 세트에 매핑해야 합니다.

## 2단계: 데이터 보기에 컨텍스트 레이블 추가

CJA 데이터 보기 설정에서 관리자는 [컨텍스트 레이블](/help/data-views/component-settings/overview.md) 다음과 같은 차원 또는 지표 및 CJA 서비스에 연결할 수 있습니다. [!UICONTROL 실험] 패널은 이러한 레이블을 용도 대로 사용할 수 있습니다. 실험 패널에 두 개의 사전 정의된 레이블이 사용됩니다.

* [!UICONTROL 실험]
* [!UICONTROL 변형]

실험 데이터가 포함된 데이터 뷰에서 실험 데이터가 있는 차원 및 변형 데이터가 있는 차원 2개를 선택합니다. 그런 다음 로 해당 차원에 레이블을 지정합니다. **[!UICONTROL 실험]** 그리고 **[!UICONTROL 변형]** 레이블.

![컨텍스트 레이블](assets/context-label.png)

이러한 레이블이 없으면 실험 패널이 작동하지 않습니다.

## 3단계: 실험 패널 구성

1. CJA Workspace에서 실험 패널을 프로젝트로 드래그합니다.

![실험 패널](assets/experiment.png)




