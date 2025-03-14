---
title: Customer Journey Analytics에서 Quantum Metric 세션 ID 수집
description: Customer Journey Analytics에서 분석할 수 있도록 세션 ID를 포함하도록 구현을 수정합니다.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: cfe4bafd-afe6-4738-94f1-30882893b3b6
source-git-commit: 2d6c5d5b546ef8ba952d4ba4397d897ed4566283
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# Customer Journey Analytics에서 Quantum Metric 세션 ID 수집

[양자 지표 세션 재생 연결](tie-session-replays.md) 또는 [양자 지표 히트맵 사용](heatmap.md)과 같은 일부 사용 사례에서는 양자 지표 세션 ID를 수집하도록 구현을 수정해야 합니다. 이 페이지에서는 해당 데이터를 기존 구현으로 성공적으로 가져오는 프로세스에 대해 간략하게 설명합니다.

다음 단계에서는 Adobe Experience Platform 데이터 수집에서 태그를 사용한다고 가정합니다. 조직에서 태그를 사용하지 않는 경우 이러한 데이터 수집 방법을 수동 웹 SDK 구현에 적용할 수 있습니다.

## 1단계: Quantum 지표 태그 확장을 사용하여 Quantum 지표 세션 ID 캡처

다음 단계에 따라 Adobe Experience Platform으로 전송하는 데이터에 양자 지표 세션 ID를 추가합니다.

1. 태그 UI에서 Quantum 지표 확장 기능을 사용하여 데이터를 Quantum 지표로 전송합니다.
1. 4개의 데이터 요소를 만듭니다.
   1. Quantum Metric의 쿠키 `QuantumMetricSessionID`에서 Quantum Metric 세션 ID를 캡처하는 것입니다.
   1. `localStorage`에서 양자 지표 세션 ID를 추출하는 ID입니다. 경우에 따라 이 데이터 요소는 다른 데이터 요소에 설정된 쿠키보다 빠르게 로드됩니다.
   1. 데이터 요소 길잡이 또는 사용자 지정 JavaScript을 사용하여 `localStorage` 데이터 요소에서 `s` 노드를 추출하십시오.
   1. 논리를 사용하여 먼저 쿠키 데이터 요소를 찾아 XDM 개체 경로(있는 경우)로 반환하는 변수입니다. 정의되지 않은 경우 추출된 `localStorage` 개체 데이터 요소를 확인해 보십시오.
1. 모든 이벤트에서 전송된 XDM 개체에 최종 Quantum Metric 세션 ID 데이터 요소를 보냅니다.

>[!NOTE]
>웹 SDK이 양자 지표 코드보다 더 빨리 실행되는 경우가 있습니다. 이러한 경우 세션 ID는 후속 히트에서 전송됩니다. 방문자가 바운스되면 세션 ID는 이러한 인스턴스에서 수집되지 않습니다.

자세한 내용은 [Quantum Metric Tag Extension](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) 설명서를 참조하십시오.

## 2단계: 포함된 데이터 세트 필드 확인

이제 연결의 데이터 세트에 원하는 데이터 세트에 양자 지표 세션 ID가 있는지 확인합니다.

## 3단계: Quantum 지표 세션 ID를 사용 가능한 차원으로 추가

기존 데이터 보기를 편집하여 세션 ID를 Customer Journey Analytics에서 사용 가능한 차원으로 추가합니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. Customer Journey Analytics으로 이동하여 상단 메뉴에서 **[!UICONTROL 데이터 보기]**&#x200B;를 선택합니다.
1. 원하는 기존 데이터 보기를 선택합니다.
1. 왼쪽의 양자 지표 세션 ID 필드 목록을 찾아 가운데에 있는 차원 영역으로 끌어서 놓습니다.
1. 오른쪽 창에서 [지속성](/help/data-views/component-settings/persistence.md) 설정을 &#39;세션&#39;으로 설정합니다.
1. **[!UICONTROL 저장]**&#x200B;을 클릭합니다.


