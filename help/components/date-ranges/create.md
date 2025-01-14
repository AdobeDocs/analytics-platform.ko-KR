---
title: 날짜 범위 만들기
description: 보고에 사용할 날짜 범위를 만듭니다.
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
role: User
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 39%

---

# 날짜 범위 만들기


누구나 사용자 지정 날짜 범위를 만들 수 있습니다. 다음과 같은 방법으로 날짜 범위를 만듭니다.

![주석 만들기](assets/create-date-range.png)

* ?? 주 인터페이스에서 **[!UICONTROL 구성 요소]**&#x200B;를 선택하고 **[!UICONTROL 날짜 범위]**&#x200B;를 선택합니다. [[!UICONTROL 날짜 범위] 관리자](/help/components/date-ranges/manage.md)에서 ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL 추가]**]를 선택합니다.
* ?? Workspace 프로젝트의 시각화의 컨텍스트 메뉴에서 **[!UICONTROL 이 날짜 범위까지의 사용자 지정 날짜 범위]**&#x200B;를 선택합니다.
* ?? Workspace 프로젝트의 메뉴에서 **[!UICONTROL 구성 요소]**&#x200B;를 선택하고 **[!UICONTROL 날짜 범위 만들기]**&#x200B;를 선택합니다.
* ?? Workspace 프로젝트에서 바로 가기 **[!UICONTROL ctrl+shift+d]**(Windows) 또는 **[!UICONTROL shift+command+d]**(macOS)을 사용합니다.
* ?? Workspace 프로젝트의 구성 요소 왼쪽 패널에서 ![달력](/help/assets/icons/Calendar.svg) **날짜 범위**&#x200B;의 ![추가](/help/assets/icons/Add.svg)를 선택합니다.

주석을 정의하려면 [[!UICONTROL 날짜 범위 빌더]](#annotation-builder)를 사용합니다.

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## 날짜 범위 빌더 {#date-range-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="종료 시간"
>abstract="종료 시간은 항상 59초를 포함합니다."

<!-- markdownlint-enable MD034 -->




**[!UICONTROL 새 날짜 범위]** 또는 **[!UICONTROL 날짜 범위 편집]** 대화 상자를 사용하여 새 날짜 범위를 만들거나 기존 날짜 범위를 편집합니다.

![다음 섹션에 설명된 필드와 옵션을 보여 주는 주석 세부 정보 창입니다.](assets/edit-date-range.png)


1. 날짜 범위에 대해 **[!UICONTROL 제목]**&#x200B;을 지정하십시오. 예: **[!UICONTROL 분기별]**.
1. 필요한 경우 **[!UICONTROL 설명]**&#x200B;을 지정하십시오.
1. 하나 이상의 **[!UICONTROL 태그]**&#x200B;를 만들거나 적용하여 필터를 구성합니다. 이름을 입력하여 선택할 수 있는 기존 태그를 찾습니다. 또는 **[!UICONTROL Enter]**&#x200B;를 눌러 새 태그를 추가하십시오. 태그를 제거하려면 ![CrossSize75](/help/assets/icons/CrossSize75.svg)을(를) 선택하십시오. |
1. 먼저 시작 날짜를 선택한 다음 종료 날짜를 선택하여 **[!UICONTROL 날짜 범위]**를 선택하십시오.
또는 [!UICONTROL *사전 설정 선택*] 드롭다운 메뉴에서 **[!UICONTROL 사전 설정]**&#x200B;을 선택할 수 있습니다.

1. 필요한 경우 **[!UICONTROL 고급 설정 표시]**&#x200B;를 선택하여 다음 작업을 수행합니다.

   * 기본 `12:00 AM`(`0:00`) 및 `11:59 PM`(`23:59`)가 아닌 다른 **[!UICONTROL 시작 시간]** 및 **[!UICONTROL 종료 시간]**&#x200B;을 지정합니다. 종료 시간은 항상 59초를 포함합니다. 날짜 범위가 여러 날에 걸친 경우 시작 시간은 날짜 범위의 첫 번째 날에 적용되고 종료 시간은 날짜 범위의 마지막 날에 적용됩니다. **[!UICONTROL (시간 값 재설정)]**&#x200B;을 사용하여 시작 및 종료 시간을 기본값으로 재설정합니다.
   * **[!UICONTROL 순환 날짜 사용]**. 활성화된 경우 **[!UICONTROL 최근 7일 전체]**&#x200B;와 같은 사전 설정된 날짜 범위가 현재 날짜 및 시간 진행률로 동적으로 업데이트됩니다. 비활성화되면 해당 사전 설정이 적용되어 업데이트되지 않습니다.

     대괄호로 묶인 텍스트(예: **[!UICONTROL 고정된 시작 - 분기별 순환]**)를 선택하여 패널을 확장하고 **[!UICONTROL 시작]** 및 **[!UICONTROL 종료]**&#x200B;에 대한 세부 정보를 지정할 수 있습니다.

     ![Rollinf 날짜](assets/rolliing-dates.png)

      1. **[!UICONTROL 시작]**, **[!UICONTROL 종료]** 또는 **[!UICONTROL 고정일]**&#x200B;을 선택합니다.
      1. **[!UICONTROL 시작]** 또는 **[!UICONTROL 종료]**&#x200B;를 선택한 경우 전체 표현식을 작성할 수 있습니다. 예: **[!UICONTROL 종료]** **[!UICONTROL 현재 분기]** **[!UICONTROL 마이너스]** `20` **[!UICONTROL 일]**. 표현식의 각 개별 부분에 적합한 값을 선택합니다.
         * 현재 값을 선택합니다. 예: **[!UICONTROL 현재 분기]**.
         * 추가 계산 값을 선택합니다. 예: **[!UICONTROL 마이너스]**.
         * 추가 계산을 지정한 경우 값을 지정합니다. (예: `20`)
         * 추가 계산을 지정한 경우 계산에 사용할 기간을 선택합니다. 예: **[!UICONTROL 일]**.

     **[!UICONTROL 세부 정보 숨기기]**&#x200B;를 선택하여 순환 날짜 계산에 대한 세부 정보를 숨깁니다.

1. 선택 :
   * 날짜 범위를 저장하려면 **[!UICONTROL 저장]**&#x200B;하세요.
   * 날짜 범위의 복사본을 저장하려면 **[!UICONTROL 다른 이름으로 저장]**&#x200B;하세요.
   * **[!UICONTROL 취소]**&#x200B;를 클릭하여 날짜 범위 변경을 취소하거나 새 날짜 범위 만들기를 취소합니다.


<!--


You can create a date range using either of the following two methods:

* Directly in a workspace project by clicking the '`+`' button next to the list of date range components on the left
* Within the date range manager

To create a date range in the date range manager:

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. Navigate to [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Click the [!UICONTROL Add] button to open the modal window that creates a date range.

## Create a date range modal window

The modal window has four fields you can edit:

* **Date range**: The date range you want for this component.
* **Title**: The name you want for this component. The title is used in workspace projects.
* **Description**: The description you want for this component. The description is seen when clicking the ![i](../assets/i.png) icon.
* **Tags**: Use tags to organize your date ranges. A date range can belong to multiple tags.

## Selecting a date range

When clicking the date range in the modal window, you have several options:

* **Calendar**: Select the start and end date.
* **Use rolling dates**: Check this box if you want the date range to change as time goes on. Do not check this box if you want your date range to remain static.
* **Select preset**: Use this drop-down selection if you want a custom date range based on a range that Adobe offers by default. When you select a preset, you can further customize the date range to suit your needs. It does not affect the preset that Adobe offers.

## Rolling date ranges

If you want a rolling date range, you can customize when it rolls. You can control when the start and end dates roll independently of each other.

* **When the date starts**: Choose if the date starts at the beginning of a time period, at the end of a time period, or use a fixed day.
* **The time period to use**: Choose how often the date range rolls. You can have it roll every day, every week, every month, every quarter, or every year.
* **Offset**: Choose the offset of the date range. You can add or subtract days, weeks, months, quarters, or years.

## Rolling date examples

Some date ranges can be useful in certain reports.

Year-to-date:

```text
Start: Start of current year
End: End of current day
```

Last Thursday to this Thursday:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Fiscal year (for example, if a fiscal year starts in December)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```


-->