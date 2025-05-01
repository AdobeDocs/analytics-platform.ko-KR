---
title: Customer Journey Analytics에 양자 지표 마찰 이벤트 추가
description: Customer Journey Analytics 행동 데이터에 양자 지표 수집 마찰 이벤트를 추가하여 CJA의 통찰력에 깊이를 더합니다.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
source-git-commit: 11dc62cda2ceb7afabd3abd0944420601c8fa235
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 1%

---

# Customer Journey Analytics에 양자 지표 마찰 이벤트 추가

Quantum Metric은 페이지 로드 속도, 페이지 로드 오류, 페이지 클릭 수 등과 같은 마찰 이벤트를 수집합니다. 이러한 이벤트는 사용자 여정에서 보조 이벤트로 Customer Journey Analytics에 전달할 수 있습니다. 이렇게 결합된 데이터를 사용하면 마찰이 다운스트림 지표에 미치는 영향을 더 잘 이해할 수 있습니다.

## 전제 조건:

이 사용 사례에는 두 가지 요구 사항이 있습니다.

* Quantum 지표의 **개발 작업** 패키지에 대한 권한이 있어야 합니다.
* Adobe Experience Platform 데이터 수집에서 태그를 사용해야 합니다.

## 1단계: 양자 지표 마찰 이벤트를 수용할 스키마 필드 만들기

이 사용 사례는에 데이터를 전송할 전용 스키마 필드가 필요합니다. 스키마의 원하는 위치에 이 필드를 만들고 원하는 이름으로 지정할 수 있습니다. 조직에 이름 또는 위치에 대한 기본 설정이 없는 경우 예제 값이 제공됩니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. **[!UICONTROL 데이터 수집]** > **[!UICONTROL 스키마]**&#x200B;로 이동합니다.
1. 목록에서 원하는 스키마를 선택합니다.
1. 원하는 개체 옆에 있는 ![필드 추가 아이콘](/help/assets/icons/AddCircle.svg) 아이콘을 선택합니다. 예를 들어 `Implementation Details` 옆에 있을 수 있습니다.
1. 오른쪽에서 원하는 [!UICONTROL 이름]을 입력합니다. (예: `qmErrorName`)
1. 원하는 [!UICONTROL 표시 이름]을 입력하십시오. (예: `Quantum Metric error name`)
1. [!UICONTROL Type]을(를) **[!UICONTROL String]**(으)로 선택하십시오.
1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

## 2단계: 양자 지표 태그 확장을 사용하여 마찰 이벤트 캡처

양자 지표 데이터를 포함하도록 태그를 설정하는 방법에 대한 지침은 Adobe Experience Platform 대상 안내서의 [양자 지표 확장](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric)을 참조하십시오. 이 확장을 사용하면 기존 데이터 세트에 더 많은 행이 전달됩니다.

Adobe Experience Platform 데이터 수집 의 태그를 사용하여 XDM 개체에 포함되고 분석될 수 있도록 마찰 이벤트의 이름을 수동으로 설정합니다. 이를 수행하는 한 가지 방법은 규칙의 사용자 지정 코드입니다.

```js
_satellite.setVar('qm_error_name','error rage click');
return true;
```

그런 다음 동적으로 설정된 데이터 요소를 XDM 개체에 추가합니다.

![Quantum 지표 오류 이름 스크린샷](assets/error-name.png)

## 3단계: Customer Journey Analytics의 데이터 보기에 하나 이상의 차원 및 지표 추가

기존 데이터 보기를 편집하여 세션 ID를 Customer Journey Analytics에서 사용 가능한 차원으로 추가합니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. Customer Journey Analytics으로 이동하여 상단 메뉴에서 **[!UICONTROL 데이터 보기]**(선택 사항: **[!UICONTROL 데이터 관리]**)을(를) 선택합니다.
1. 원하는 기존 데이터 보기를 선택합니다.
1. 왼쪽의 양자 지표 마찰 이벤트 필드 목록을 찾아 가운데에 있는 지표 영역으로 끌어서 놓습니다.
1. 오른쪽 창에서 [값 포함/제외](/help/data-views/component-settings/include-exclude-values.md) 설정을 추적하려는 마찰 이벤트로 설정합니다. 여러 마찰 이벤트를 동일한 지표에 추가하여 결합할 수 있습니다. 마찰 이벤트 필드의 다른 사본을 지표 영역으로 드래그하여 다른 마찰 이벤트를 별도의 지표로 추적할 수도 있습니다.
1. 원하는 차원 및 지표를 모두 만들었으면 **[!UICONTROL 저장]**&#x200B;을 클릭합니다.
1. 오류 이벤트의 전체 목록은 Quantum Metric 설명서를 참조하십시오. 추가 질문이 있는 경우 Quantum Metric 고객 지원 담당자에게 문의하거나 [Quantum Metric 고객 요청 포털](https://community.quantummetric.com/s/public-support-page)을 통해 요청을 제출하십시오.

## 4단계: Analysis Workspace의 나머지 데이터와 함께 차원 및 지표 사용

나머지 방문자 데이터와 함께 수집된 양자 지표 마찰 이벤트 데이터를 사용하면 Customer Journey Analytics의 다른 차원 또는 지표와 동일하게 사용할 수 있습니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. Customer Journey Analytics으로 이동하고 상단 메뉴에서 **[!UICONTROL Workspace]**&#x200B;을(를) 선택합니다.
1. 기존 프로젝트를 선택하거나 프로젝트를 만듭니다.
1. [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)을 만듭니다.
1. 분석을 위해 원하는 차원 및 지표를 Workspace 캔버스로 드래그합니다.

가능한 분석 아이디어는 다음과 같습니다.

* 시간 경과에 따른 트렌드 마찰 이벤트 데이터
* 폴아웃 또는 단계 시각화에서 Customer Journey Analytics 이벤트를 일부 단계로 추가하고, 양자 지표 마찰 이벤트를 다른 단계로 추가합니다. 이 보고서를 통해 방문자가 가장 일반적으로 문제가 발생하는 위치를 확인할 수 있습니다.
* 더 자세한 분석을 위해 마찰 이벤트를 경험하는 방문자를 위한 세그먼트 만들기 및 적용
