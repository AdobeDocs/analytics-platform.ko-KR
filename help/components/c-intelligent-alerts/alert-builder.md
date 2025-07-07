---
description: Analysis Workspace에서 경고를 만드는 방법을 알아봅니다.
title: 경고 만들기
feature: Workspace Basics
role: User, Admin
exl-id: 5b4b2e2b-0a73-48df-a40c-98d2c47f94c8
source-git-commit: 9e07dfc84bc06aef987d99c225cefb4e0406f552
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 79%

---

# 경고 만들기 {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="시간 세부 기간"
>abstract="시간 세부 기간이란 경고를 확인하는 빈도를 의미합니다."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>예외 항목 탐지가 있는 경고 사용(_지능형 경고_)은 Customer Journey Analytics Prime 또는 Ultimate 패키지를 보유한 조직에서만 사용할 수 있습니다.

Customer Journey Analytics의 경고 기능을 사용하면 변경된 백분율이나 특정 데이터 포인트에 따라 알림을 받을 수 있습니다. Customer Journey Analytics 패키지를 기반으로 예외 항목 임계값에 따라 경고를 트리거하도록 설정할 수도 있습니다.

경고에 대한 자세한 개요 정보는 [경고 개요](/help/components/c-intelligent-alerts/intelligent-alerts.md)를 참조하십시오.

경고 만드는 방법:

<!-- Note that there are difference in how alerts are created in CJA vs AA. In AA you can create alerts from the Workspace menu and using a shortcut; these are not possible in CJA... -->

1. Customer Journey Analytics에서 **[!UICONTROL 구성 요소]** > **[!UICONTROL 경고]**&#x200B;를 선택합니다. [경고 관리자](alert-manager.md)에서 ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 추가]**&#x200B;를 선택하여 새 경고를 만들거나, 나열된 경고 중에서 선택하여 기존 경고를 수정합니다.

1. Analysis Workspace의 자유 형식 테이블에서 하나 이상의 라인 항목을 선택하고 컨텍스트 메뉴에서 **[!UICONTROL 선택 항목으로 경고 만들기]**&#x200B;를 선택합니다. 이 작업을 수행하면 즉시 경고 빌더가 미리 채워져서 올바른 지표와 세그먼트로 경고가 만들어집니다.

[경고 빌더](#alert-builder) 인터페이스가 표시됩니다.


## 경고 빌더

경고 빌더 인터페이스는 Customer Journey Analytics에서 세그먼트 또는 계산된 지표를 작성할 때 사용하는 인터페이스에 익숙합니다.

![경고 빌더 인터페이스](assets/alert-builder.png)

경고 빌더에서 경고에 대한 다음 세부 정보를 지정합니다.

| 요소 | 설명 |
|---------|----------|
| **[!UICONTROL 제목]** | 경고 이름을 지정합니다. 경고 이름에는 보고서 또는 지표 임계값 이름이 포함될 수 있습니다. |
| **[!UICONTROL 설명 (선택 사항)]** | 경고의 설명을 작성합니다. |
| **[!UICONTROL 시간 세부 기간]** | 지표를 확인할 주기(일별, 주별 또는 월별)를 선택합니다.<p><b>참고</b>: [사용자 지정 달력](/help/data-views/create-dataview.md#calendar)이 있는 데이터 보기의 경우 월별 세부기간은 경고 빌더에서 지원되지 않습니다.<!--true?--></p> |
| **[!UICONTROL 수신자]** | 경고를 전송할 대상을 지정합니다. 경고는 Analytics 사용자, Analytics 그룹, 원시 이메일 주소 또는 전화번호에 보낼 수 있습니다.<p><b>중요</b>: 전화 번호 앞에는 `+`와 [국가 코드](https://countrycode.org/)가 있어야 합니다.</p><p>경고 후 사용자가 받는 이메일:</p><p>![경고 이메일](assets/alerts-email.PNG)</p> |
| **[!UICONTROL 만료 날짜]** | 경고가 만료되기 원하는 날짜와 시간을 설정합니다. |
| **[!UICONTROL 지연]** | 데이터가 완료되어 Customer Journey Analytics에 보고되는 데 필요한 시간은 조직마다 다르며, 일반적으로 데이터 이벤트 시간 이후 3~9시간 정도 소요됩니다. 경고가 정확하려면 지정된 이벤트 범위에 대한 이벤트 데이터가 완료되어야 하므로 Adobe는 더 이상 지정된 이벤트 범위에 대한 이벤트 데이터를 수신하지 않습니다.<p>이러한 수집 시간 지연을 고려하여 경고가 전송되기까지 기본적으로 9시간이 지연됩니다.</p><p>기본 지연 시간인 9시간을 0~24시간 사이의 값으로 조정할 수 있습니다. 그러나 지연 시간을 9시간 이하로 줄이면 불완전한 데이터를 보고하게 되어 부정확한 경고 정보가 제공될 수 있습니다.</p><p>지연 시간을 줄일 때 다음 사항을 고려해야 합니다.</p><ul><li>**데이터 가용성과 데이터 완전성을 파악합니다**: 배치 데이터는 3~9시간 후에 Experience Platform 데이터 세트로 수집됩니다. 경고가 정확하려면 데이터 수집이 완료되어야 하며, 모든 배치 데이터가 데이터 세트에 포함되어 있어야 합니다.</li><li>**데이터 세트에서 데이터가 완료되고 사용 가능해지는 데 걸리는 시간 결정**: 데이터 수집 시간은 조직에 따라 다릅니다. 경고 게재를 위해 선택한 지연 시간이 Platform 데이터 세트에서 배치 데이터를 사용하는 데 걸리는 시간과 같거나 덜 빈번한지 확인합니다<!--add link? -->.</li><p>**팁:** 모든 일괄 처리 데이터를 완료하여 Experience Platform 데이터 세트로 수집하는 데 필요한 시간을 가장 정확하게 파악하는 방법은 조직의 데이터 엔지니어와 상담하는 것입니다.</p><p>또는 조직에서 일괄 게재를 Platform 데이터 세트에서 사용할 수 있는 데 걸리는 시간에 대한 일반적인 아이디어를 얻을 수 있습니다. Analysis Workspace에서 다음 자유 형식 테이블을 만듭니다.</p><ol><li>Analysis Workspace의 자유 형식 테이블에 [!UICONTROL **이벤트**] 지표와 [!UICONTROL **일**] 차원을 추가합니다.</li><li>[!UICONTROL **시간**] 차원을 사용하여 [!UICONTROL **일**] 차원을 분류합니다.<p>데이터가 없는 시간은 0으로 표시됩니다.</p></li></ol><li>**계산 오류 고려**: 기본 지연 시간을 줄이려면 데이터 수집 완료에 걸리는 시간보다 최소 한 시간 길게 지연을 설정해야 합니다. 예를 들어 데이터 수집이 완료되기까지 3시간 지연이 발생하면 지연 시간을 4시간으로 설정해야 합니다.</li></ul><p>자세한 내용은 [경고 기능 비교: Customer Journey Analytics와 Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) 문서에서 [Customer Journey Analytics 내 데이터 수집 시간 변경](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics)을 참조하십시오. |
| **[!UICONTROL 다음의 경우에 경고 보내기]** | [!UICONTROL **지표 중 하나 이상의 트리거**]: 여기에 지표(계산된 지표 포함)를 끌어다 놓아 경고 트리거를 생성합니다.<p>경고에 뜬 모든 지표, 차원 또는 세그먼트 중 일부가 현재 선택된 데이터 보기와 호환하지 않을 경우 **“호환하지 않는 구성 요소”** 메시지가 표시됩니다.</p><p>경고를 설정하기 전에 지표가 초과되는 임계값을 결정합니다. 이 값을 임계값으로 설정한 후 다음 조건 중 하나로 설정할 수 있습니다.</p><ul><li>예외 항목이 있음</li><li>예외 항목이 예상 이상임</li><li>예외 항목이 예상 미만임</li><li>위 또는 같음</li><li>아래 또는 같음</li><li>변경</li><li>90%, 95%, 99%, 99.75% 및 99.9%의 임계값을 설정할 수 있습니다.</li></ul><p>[!UICONTROL **이 모든 필터 사용**]: 세그먼트나 차원을 끌어다 놓아 경고에 필터를 추가할 수 있습니다. 예를 들어, *모바일 장치만* 세그먼트를 추가한다는 것은 모바일 장치에 대해서만 규칙이 트리거됨을 의미합니다. AND 구문을 사용하여 추가 필터를 적용할 수 있습니다. 톱니바퀴 아이콘을 클릭하여 AND 또는 OR 규칙을 추가할 수 있습니다.</p><p>[경고 - 사용 사례](/help/components/c-intelligent-alerts/alerts-use-cases.md)를 참조하세요.</p> |
| **[!UICONTROL 미리보기]** | 대화형 경고 미리보기에서는 경고가 과거의 경험을 기반으로 얼마나 자주 표시되는지를 근사적으로 보여 줍니다.<p>예를 들어 시간 세부 기간을 매일로 설정하는 경우, 미리보기에서는 경고가 지난 30 또는 31일 동안 특정 지표 x 배수에 대해 트리거됨을 알 수 있습니다.</p><p>너무 많은 경고가 트리거 되면 [경고 관리](/help/components/c-intelligent-alerts/alert-manager.md)에서 임계값을 조정할 수 있습니다.</p><p>![](assets/alert-preview.png){width="50%"}</p> |
