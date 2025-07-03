---
description: 요약 숫자 및 요약 변경 시각화를 사용하여 프로젝트의 중요 데이터 포인트를 표시할 수 있습니다.
title: 요약 번호 및 요약 변경 사항
feature: Visualizations
exl-id: 8872fc58-0957-415d-9958-ce564612ce87
role: User
source-git-commit: 639c3d3c349615078c76f8806bcd5bb458b0f6f2
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 99%

---

# 요약 숫자 및 변경 사항

>[!BEGINSHADEBOX]

_이 문서에서는_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;의 요약 숫자와 요약 변경 시각화에 대해 설명합니다._<br/>_이 문서의_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 버전은 [요약 숫자 및 요약 변경](https://experienceleague.adobe.com/ko/docs/analytics/analyze/analysis-workspace/visualizations/summary-number-change)을 참조하십시오._

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

데모 비디오를 보려면 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [요약 숫자 및 요약 변경 시각화](https://video.tv.adobe.com/v/335564/?quality=12&learn=on){target="_blank"}를 확인하십시오.

>[!ENDSHADEBOX]

## 요약 숫자 {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="요약 숫자"
>abstract="총계와 소계를 보여 주는 시각화를 만듭니다."

<!-- markdownlint-enable MD034 -->

프로젝트에서 중요한 큰 숫자를 강조 표시하려면 ![요약](/help/assets/icons/123.svg) **[!UICONTROL 요약 숫자]** 시각화를 사용하십시오. 이 시각화는 연관된 데이터 소스를 사용하여 다음과 같은 방식으로 작동합니다.

* 셀을 선택하지 않은 경우 열의 합계를 선택합니다.
* 단일 셀을 선택하면 해당 셀의 요약이 표시됩니다.
* 두 개 이상의 셀을 선택하면 선택한 첫 번째 셀이 표시됩니다.
* 열을 선택하면 열의 첫 번째 셀 값이 선택됩니다.

![요약 숫자 시각화](asses/../assets/summary-number.png)

시각화 설정의 일부로 특정 요약 숫자 옵션을 이용할 수 있습니다.

| 옵션 | 정의 |
|--- |--- |
| **[!UICONTROL 값 생략]** | 숫자 값을 지능적으로 축약하도록 **[!UICONTROL 값 생략]**&#x200B;을 선택합니다. 선택하면 숫자를 입력하여 축약 수를 정의합니다. 예:<br/><table><tr><td>**원래 값**</td><td>**축약 값**</td><td>**결과**</td></tr><tr><td>$12,011,141.25</td><td>선택되지 않음</td><td  align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>선택된 경우, `0`으로 설정</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td> 선택된 경우, `1`로 설정</td><td  align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>선택된 경우, `2`로 설정</td><td align="right">$12.01M</td></tr><tr><td>$12,011,141.25</td><td>선택된 경우, `3`으로 설정</td><td align="right">$12.011M</td></tr></table> |
| **[!UICONTROL 다음을 기준으로 값 요약]** | 선택한 데이터의 최대, 최소, 평균, 중간값 또는 합계를 표시하도록 선택합니다. |

## 요약 변경 {#summary-change}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarychange_button"
>title="요약 변경"
>abstract="두 숫자 사이의 델타(변경)를 보여 주는 시각화를 만듭니다."

<!-- markdownlint-enable MD034 -->


![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL 요약 변경]** 시각화를 사용하여 두 숫자 간의 델타(변화량)를 표시합니다. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html?lang=ko) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=ko) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=ko) option.
-->

이 시각화는 다음과 같은 방식으로 동작합니다.

* 셀을 선택하지 않으면 열의 처음 두 셀 값을 비교합니다.
* 하나의 셀을 선택하면 셀 값을 자신과 비교하기 때문에 0을 표시합니다.
* 두 개의 셀을 선택하면 처음 선택한 셀을 분자로, 두 번째 셀을 분모로 취합니다.
* 세 개 이상의 셀을 선택하면 처음 두 개만 비교합니다.
* 셀 범위를 선택하면 범위에서 선택한 첫 번째 셀과 마지막 셀을 비교합니다.
* 열을 선택하면 첫 번째 값과 자신을 비교하여 0이 표시됩니다.


![두 숫자 사이의 델타를 보여 주는 요약 변경 시각화.](assets/summary-change.png)


시각화 설정의 일부로 특정 **[!UICONTROL 요약 변경 옵션]**&#x200B;을 이용할 수 있습니다.

| 옵션 | 정의 |
|--- |--- |
| **[!UICONTROL 백분율 변경 표시]** | 두 숫자 사이의 퍼센트 변화량을 표시합니다. |
| **[!UICONTROL 원시 차이 표시]** | 두 숫자 사이의 원시 차이를 표시합니다. 이 옵션을 사용하여 값들을 축약하고 소수점 이하 최대 3자리를 표시할 수도 있습니다. |
| **[!UICONTROL 값 생략]** | 변경된 값을 지능적으로 축약하도록 **[!UICONTROL 값 생략]**&#x200B;을 선택합니다. 선택하면 숫자를 입력하여 축약 수를 정의합니다. 예:<br/><table><tr><td>**원래 값**</td><td>**축약 값**</td><td>**결과**</td></tr><tr><td>$12,011,141.25</td><td>선택되지 않음</td><td  align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>선택된 경우, `0`으로 설정</td><td align="right">$12M</td></tr><tr><td>$12,011,141.25</td><td> 선택된 경우, `1`로 설정</td><td  align="right">$12.0M</td></tr><tr><td>$12,011,141.25</td><td>선택된 경우, `2`로 설정</td><td align="right">$12.01M</td></tr><tr><td>$12,011,141.25</td><td>선택된 경우, `3`으로 설정</td><td align="right">$12.011M</td></tr></table> |

>[!MORELIKETHIS]
>
>[패널 내에 시각화 추가](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[시각화 설정](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[시각화 컨텍스트 메뉴](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
