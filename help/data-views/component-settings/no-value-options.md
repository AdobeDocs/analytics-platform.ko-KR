---
title: 값 옵션 없음 구성 요소 설정
description: 비어 있는 경우 차원을 처리하는 방법을 결정합니다.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 16e8668d88dda2784ba60a1fa4302225ceff190f
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 53%

---

# 값 옵션 없음 구성 요소 설정 {#no-value-options-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_novalueoptions"
>title="값 옵션 없음"
>abstract="차원에 값이 없는 경우 기본 비헤이비어를 구성합니다."

<!-- markdownlint-enable MD034 -->


[!UICONTROL 값 옵션 없음]을 통해 데이터 집합에 있는 이벤트에 지표가 포함되어 있지만 차원에 값이 없는 상황을 Analysis Workspace에서 처리하는 방법을 결정할 수 있습니다. 이 차원 항목의 이름을 선택하고 완전히 숨기거나 실제 값으로 처리할 수도 있습니다.

![값 옵션 없음](../assets/no-value-options.png)

## 설정 {#settings}

| 설정 | 설명 |
| --- | --- |
| **[!UICONTROL 표시되면 “값 없음” 호출]** | 텍스트 필드를 통해 **[!UICONTROL 값 없음]** 차원 항목의 이름을 다른 이름으로 바꿀 수 있습니다. |
| **[!UICONTROL 기본적으로 &quot;값 없음&quot;을 표시하지 않음]** | 보고 시 이 값을 표시하지 않습니다. 이 차원에 귀속되지 않는 지표 발생 횟수는 보고서에 표시되지 않습니다. |
| **[!UICONTROL 기본적으로 &quot;값 없음&quot; 표시]** | 보고 시 이 값을 표시합니다. |
| **[!UICONTROL &quot;값 없음&quot;을 값으로 취급]** | (숫자 차원에서는 지원되지 않음) 데이터의 빈 값을 [!UICONTROL 에 지정한 텍스트로 바꿉니다. 표시되면 &quot;값 없음&quot;]을 호출합니다. 예를 들어 모바일 디바이스 유형이 차원으로 있는 경우 **[!UICONTROL 값 없음]** 항목의 이름을 “데스크탑”으로 바꿀 수 있습니다. 이 필드를 사용자 지정 값으로 변경하면 해당 사용자 지정 값은 적합한 문자열 값으로 처리됩니다. 따라서 이 필드에 값 “빨간색”을 입력하면 데이터 자체에 나타나는 문자열 “빨간색”의 인스턴스도 사용자가 지정한 동일한 라인 항목 아래로 롤링됩니다. |

## 숫자 차원에 대한 &quot;값 없음&quot; 지원 {#numeric}

숫자 값을 차원으로 사용할 때 다음 작업을 수행할 수 있습니다

* 데이터 보기에서 &quot;값 없음&quot; 옵션을 구성합니다. **[!UICONTROL 값 없음을 값으로 취급]**&#x200B;하는 경우를 제외하고 모든 구성 설정이 지원됩니다.
* Workspace의 자유 형식 테이블에서 숫자 차원에 대해 [!UICONTROL 값 없음 포함]을 사용합니다.
* 필터 빌더에서 숫자 차원이 있는 &quot;존재함&quot; 또는 &quot;존재하지 않음&quot; 연산자를 사용합니다.

>[!MORELIKETHIS]
>
>다음은 [Customer Journey Analytics에서 &quot;값 없음&quot; 처리](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/handling-quot-no-value-quot-in-customer-journey-analytics/ba-p/597339)에 대한 관련 블로그 게시물입니다.

