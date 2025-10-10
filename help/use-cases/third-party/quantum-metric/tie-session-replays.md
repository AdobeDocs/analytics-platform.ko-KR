---
title: Customer Journey Analytics의 데이터에 양자 지표 세션 재생 연결
description: 양자 지표 연결 세션은 "무엇을"의 "이유"를 더 잘 이해하기 위해 CJA 데이터로 재생됩니다.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 95a107c6bbc6dce6cc43c4a1b51beeaa1fa7aff1
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 2%

---

# Customer Journey Analytics의 데이터에 양자 지표 세션 재생 연결

Quantum Metric 세션 재생과 CJA 데이터를 연결함으로써 고객은 &quot;내용&quot; 이면의 &quot;이유&quot;를 더 잘 이해할 수 있습니다.  Workspace을 사용하여 마찰이 있는 세션을 검색한 다음 하이퍼링크된 세션 ID를 클릭하여 Quantum 지표에서 세션 재생 을 탐색할 수 있습니다.  이 데이터를 사용하면 세션 내의 비헤이비어를 볼 수 있으며 무엇이 소비자 마찰을 유도하는지 더 잘 이해할 수 있습니다.  CJA과 연결된 세션 재생을 통해 경험에서 고객 행동에 대한 중요한 컨텍스트를 캡처할 수 있습니다.

## 사전 요구 사항

다음 단계에서는 Adobe Experience Platform 데이터 수집에서 태그를 사용한다고 가정합니다. 조직에서 태그를 사용하지 않는 경우 이러한 데이터 수집 방법을 수동 웹 SDK 구현에 적용할 수 있습니다.

자세한 내용은 [Quantum Metric Tag Extension](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) 설명서를 참조하십시오.

## 1단계: Quantum 지표 세션 ID를 수용할 스키마 필드 만들기

이 사용 사례는에 데이터를 전송할 전용 스키마 필드가 필요합니다. 스키마의 원하는 위치에 이 필드를 만들고 원하는 이름으로 지정할 수 있습니다. 조직에 이름 또는 위치에 대한 기본 설정이 없는 경우 예제 값이 제공됩니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. **[!UICONTROL 데이터 수집]** > **[!UICONTROL 스키마]**&#x200B;로 이동합니다.
1. 목록에서 원하는 스키마를 선택합니다.
1. 원하는 개체 옆에 있는 ![필드 추가 아이콘](/help/assets/icons/AddCircle.svg) 아이콘을 선택합니다. 예를 들어 `Implementation Details` 옆에 있을 수 있습니다.
1. 오른쪽에서 원하는 [!UICONTROL 이름]을 입력합니다. (예: `qmSessionId`)
1. 원하는 [!UICONTROL 표시 이름]을 입력하십시오. (예: `Quantum Metric session ID`)
1. [!UICONTROL Type]을(를) **[!UICONTROL String]**(으)로 선택하십시오.
1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

## 2단계: Quantum Metric 태그 확장을 사용하여 Quantum Metric 세션 ID 캡처

다음 단계에 따라 Adobe Experience Platform으로 전송하는 데이터에 양자 지표 세션 ID를 추가합니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**(으)로 이동합니다.
1. 원하는 태그 속성을 선택합니다.
1. **[!UICONTROL 데이터 요소]**&#x200B;를 선택한 다음 **[!UICONTROL 데이터 요소 추가]**&#x200B;를 선택합니다.
1. 다음 설정을 지정합니다.
   * **[!UICONTROL 이름]**: `Quantum Metric session ID`
   * **[!UICONTROL 확장]**: [!UICONTROL 코어]
   * **[!UICONTROL 데이터 요소 형식]**: [!UICONTROL 사용자 지정 코드]
1. **[!UICONTROL 편집기 열기]** 단추를 선택하고 다음 코드에 붙여넣습니다.

   ```js
   // Check for the presence of the Quantum Metric session ID cookie
   const qmCookie = _satellite.cookie.get("QuantumMetricSessionID");
   if(qmCookie != null) return qmCookie;
   // If a cookie is not set, check local storage
   const qmLocalStorage = JSON.parse(localStorage.getItem("QM_S") || "{}");
   if (qmLocalStorage?.s != null) return qmLocalStorage.s;
   ```

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

## 3단계: 데이터 요소를 원하는 XDM 스키마 필드에 매핑

이제 데이터 요소에 원하는 값을 얻는 논리가 있으므로 데이터 요소를 XDM 개체에 매핑합니다.

1. 태그 속성에서 **[!UICONTROL 데이터 요소]**&#x200B;를 선택한 다음 XDM 개체가 있는 데이터 요소를 선택합니다.
1. 이 데이터 요소의 오른쪽 열에서 스키마 필드를 만들 때 설정한 경로로 이동합니다.
1. 값을 퍼센트 기호로 둘러싸인 데이터 요소의 이름으로 설정합니다. (예: `%Quantum Metric session ID%`)
1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.
1. 라이브러리를 추가한 다음 변경 사항을 프로덕션에 게시합니다.

XDM 개체가 이벤트 보내기 작업 구성에 이미 포함되어 있는 경우 변경 사항이 게시되면 데이터가 표시됩니다.

>[!NOTE]
>
>웹 SDK이 양자 지표 코드보다 더 빨리 실행되는 경우가 있습니다. 이러한 경우 세션 ID는 후속 히트에서 전송됩니다. 방문자가 바운스되면 세션 ID는 이러한 인스턴스에서 수집되지 않습니다.

## 3단계: Quantum 지표 세션 ID를 사용 가능한 차원으로 추가

구현에 위의 변경 사항이 게시되면 기존 데이터 보기를 편집하여 세션 ID를 Customer Journey Analytics에서 사용 가능한 차원으로 추가합니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. Customer Journey Analytics으로 이동하여 상단 메뉴에서 **[!UICONTROL 데이터 보기]**&#x200B;를 선택합니다.
1. 원하는 기존 데이터 보기를 선택합니다.
1. 왼쪽의 양자 지표 세션 ID 필드를 찾아 가운데에 있는 차원 영역으로 끌어서 놓습니다.
1. 오른쪽 창에서 [지속성](/help/data-views/component-settings/persistence.md) 설정을 `Session`(으)로 설정합니다.
1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

## 4단계: 세션 ID 차원을 수용하도록 Analysis Workspace 구성

Workspace에서 자유 형식 테이블을 만들고 세션 ID 값이 Quantum 지표에 직접 연결되도록 구성합니다.

1. [experience.adobe.com](https://experience.adobe.com)에 로그인합니다.
1. Customer Journey Analytics으로 이동하고 상단 메뉴에서 **[!UICONTROL Workspace]**&#x200B;을(를) 선택합니다.
1. 기존 프로젝트를 선택하거나 프로젝트를 만듭니다.
1. [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)을 만듭니다.
1. 세션 ID 차원을 Workspace 캔버스로 드래그합니다.
1. 차원 열 헤더를 마우스 오른쪽 단추로 클릭한 다음 **[!UICONTROL 모든 차원 항목에 대한 하이퍼링크 만들기]**&#x200B;를 선택합니다.
1. **[!UICONTROL 사용자 지정 URL 만들기]**&#x200B;를 선택합니다.
1. 다음 URL 구조를 붙여넣습니다.

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

이제 각 세션 ID를 클릭 가능한 링크로 지정할 수 있습니다. Analysis Workspace 차원 항목에 하이퍼링크를 추가하는 방법에 대한 자세한 내용은 [자유 형식 테이블에 하이퍼링크 만들기](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)를 참조하십시오.

![세션 재생](assets/session-replay.png)

## 5단계: Customer Journey Analytics에서 세션 보기

세션 재생을 탐색할 흥미로운 세그먼트가 발견되면 세션 ID 링크가 포함된 패널에 적용할 수 있습니다. 테이블은 해당 세그먼트의 모든 세션을 반환하며, 이 중 하나를 클릭하여 양자 지표에서 자세히 탐색할 수 있습니다.

자세한 내용은 Quantum Metric에서 [세션 재생에 대한 Enterprise 안내서](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay)를 참조하십시오. [Quantum Metric 고객 요청 포털](https://community.quantummetric.com/s/public-support-page)을 통해 Quantum Metric 고객 지원 담당자에게 문의하거나 요청을 제출할 수도 있습니다.
