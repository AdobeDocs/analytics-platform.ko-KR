---
title: Customer Journey Analytics에 양자 지표 마찰 이벤트 추가
description: Quantum Metric에서 수집된 마찰 이벤트를 사용하여 Customer Journey Analytics의 인사이트에 깊이를 추가합니다.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
source-git-commit: 10a70743d292e50ca5aea3225897e7097fa4fc8a
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---

# Customer Journey Analytics에 양자 지표 마찰 이벤트 추가

Quantum Metric은 페이지 로드 속도, 페이지 로드 오류, 페이지 클릭 수 등과 같은 마찰 이벤트를 수집합니다. 이러한 이벤트는 사용자 여정에서 보조 이벤트로 Customer Journey Analytics에 전달할 수 있습니다. 이렇게 결합된 데이터를 사용하면 마찰이 다운스트림 지표에 미치는 영향을 더 잘 이해할 수 있습니다.

## 전제 조건:

이 사용 사례에는 두 가지 요구 사항이 있습니다.

* Quantum 지표의 **개발 작업** 패키지에 대한 권한이 있어야 합니다.
* Adobe Experience Platform 데이터 수집에서 태그를 사용해야 합니다.

## 1단계: 양자 지표 태그 확장을 사용하여 마찰 이벤트 캡처

양자 지표 CSM 팀은 추가할 올바른 스키마 요소를 결정하고 Customer Journey Analytics에서 사용할 데이터를 수집하도록 구현을 수정하도록 지시하는 데 도움이 됩니다. 자세한 내용은 Quantum Metric 고객 성공 관리자에게 문의하십시오.

궁극적으로, 필드에서 마찰 이벤트 이름을 추적하기 시작할 것입니다.

## 2단계: 포함된 데이터 세트 필드 확인

이제 연결의 데이터 세트에 원하는 데이터 세트에 양자 지표 세션 ID가 있는지 확인합니다.

## 3단계: Customer Journey Analytics의 데이터 보기에 하나 이상의 차원 및 지표 추가

기존 데이터 보기를 편집하여 세션 ID를 Customer Journey Analytics에서 사용 가능한 차원으로 추가합니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. Customer Journey Analytics으로 이동하여 상단 메뉴에서 **[!UICONTROL 데이터 보기]**&#x200B;를 선택합니다.
1. 원하는 기존 데이터 보기를 선택합니다.
1. 왼쪽의 양자 지표 마찰 이벤트 필드 목록을 찾아 가운데에 있는 지표 영역으로 끌어서 놓습니다.
1. 오른쪽 창에서 [값 포함/제외](/help/data-views/component-settings/include-exclude-values.md) 설정을 추적하려는 마찰 이벤트로 설정합니다. 여러 마찰 이벤트를 동일한 지표에 추가하여 결합할 수 있습니다. 마찰 이벤트 필드의 다른 사본을 지표 영역으로 드래그하여 다른 마찰 이벤트를 별도의 지표로 추적할 수도 있습니다.
1. 원하는 차원 및 지표를 모두 만들었으면 **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

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
* 더 자세한 분석을 위해 마찰 이벤트를 경험하는 방문자를 위한 필터 만들기 및 적용
