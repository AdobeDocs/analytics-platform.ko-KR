---
title: 연결에 Analytics 소스 커넥터 데이터 세트 추가
description: 연결에 Analytics 소스 커넥터 데이터 세트 추가 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 98%

---

# 연결에 Analytics 소스 커넥터 데이터 세트 추가 {#upgrade-source-connector-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-dataset"
>title="연결에 Analytics 소스 커넥터 데이터 세트 추가"
>abstract="Analytics 보고서 모음의 과거 데이터가 Adobe Experience Platform에 있으므로, Customer Journey Analytics를 처음 구성할 때 만든 기존 연결에 해당 데이터 세트를 추가합니다. 이 단계가 완료되면 Customer Journey Analytics의 과거 데이터를 사용할 수 있습니다.<br><br>Customer Journey Analytics에서 연결에 데이터 세트를 추가하는 작업은 간단하여 완료하는 데 몇 분밖에 걸리지 않습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## Analytics 소스 커넥터가 내역 데이터를 Customer Journey Analytics로 가져오는 방식 파악

Analytics 소스 커넥터를 사용하여 Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform으로 가져올 수 있습니다. 이러한 데이터는 Customer Journey Analytics에서 내역 데이터로 사용될 수 있습니다.

이 프로세스는 조직의 요구와 사용하는 특정 Platform 애플리케이션에 맞춘 간소화된 스키마가 필요하기 때문에 [Customer Journey Analytics로 업그레이드할 때 XDM 스키마를 만들고자](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md) 한다고 가정합니다.

Analytics 소스 커넥터를 사용하여 내역 데이터를 Customer Journey Analytics로 가져오려면 다음 작업을 수행해야 합니다.

1. [Analytics 소스 커넥터용 XDM 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. 아직 Analytics 소스 커넥터가 없는 경우 [Analytics 소스 커넥터를 생성하고 필드를 XDM 스키마에 매핑](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)합니다.

   또는

   이미 Analytics 소스 커넥터가 있는 경우 [소스 커넥터에서 XDM 스키마로 필드를 매핑](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)합니다.

1. 아래 설명한 대로 연결에 Analytics 소스 커넥터 데이터 세트를 추가합니다.

## 연결에 Analytics 소스 커넥터 데이터 세트 추가

[내역 데이터에 대한 분석 소스 커넥터를 만들고](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md) 나면 Analytics 데이터에 대한 데이터 세트가 자동으로 생성됩니다.

자동으로 생성된 데이터 세트를 Web SDK 구현을 위해 생성한 동일한 연결에 추가해야 합니다. 이렇게 하면 Analytics 데이터가 Customer Journey Analytics의 Web SDK 데이터와 동일한 데이터 보기로 전송됩니다.

자동으로 생성된 데이터 세트를 Web SDK 구현을 위해 생성한 동일한 연결에 추가하는 방법:

1. Customer Journey Analytics에서 상단 메뉴의 **[!UICONTROL 데이터 관리]**&#x200B;에서(선택 사항) **[!UICONTROL 연결]**&#x200B;을 선택합니다.

1. [Web SDK 구현을 위해 생성된](/help/getting-started/cja-upgrade/cja-upgrade-connection.md) 연결을 선택합니다.

1. **[!UICONTROL 편집]**&#x200B;을 선택합니다.

   ![연결 편집](assets/connection-add-dataset.png)

1. 오른쪽 상단의 **[!UICONTROL 데이터 세트 추가]**&#x200B;를 선택합니다.

   ![연결 편집](assets/connection-add-dateset2.png)

1. Analytics 소스 커넥터를 생성할 때 자동으로 생성된 데이터 세트를 스크롤하거나 검색합니다.

   이 데이터 세트의 이름은 보고서 세트의 이름 뒤에 `midValues`가 붙습니다. 예: `My report suite midValues`

1. 데이터 세트 이름 옆에 있는 확인란을 선택한 다음 **[!UICONTROL 다음]**&#x200B;을 선택합니다.

   ![연결 편집](assets/connection-add-dataset3.png)

1. 다음 정보를 지정합니다.

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | 설정 | 설명 |
   | --- | --- |
   | **[!UICONTROL 개인 ID]** | 이벤트 및 프로필 데이터 세트에만 사용할 수 있습니다. 사용 가능한 ID의 드롭다운 메뉴에서 개인 ID를 선택합니다. 이러한 ID는 Experience Platform의 데이터 세트 스키마에 정의되어 있습니다. ID 맵을 개인 ID로 사용하는 방법에 대한 자세한 내용은 아래를 참조하십시오.<p>선택할 개인 ID가 없는 경우 하나 이상의 개인 ID가 스키마에 정의되어 있지 않음을 의미합니다. 자세한 내용은 [UI에서 ID 필드 정의](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/ui/fields/identity)를 참조하십시오. <p>선택한 개인 ID의 값은 대소문자를 구분하는 것으로 간주됩니다. 예를 들어 `abc123` 및 `ABC123`은 서로 다른 두 값입니다. |
   | **[!UICONTROL 타임스탬프]** | 이벤트 및 요약 데이터 세트의 경우에만 이 설정이 Experience Platform의 이벤트 기반 스키마에서 기본 타임스탬프 필드로 자동 설정됩니다. |
   | **[!UICONTROL 시간대]** | 요약 데이터에만 사용할 수 있습니다. 시계열 요약 데이터에 적합한 시간대를 선택합니다. |
   | **[!UICONTROL 데이터 소스 유형]** | 데이터 소스 유형을 선택합니다. <br/>데이터 소스 유형에는 다음이 포함됩니다. <ul><li>[!UICONTROL 웹 데이터]</li><li>[!UICONTROL 모바일 앱 데이터]</li><li>[!UICONTROL POS 데이터]</li><li>[!UICONTROL CRM 데이터]</li><li>[!UICONTROL 설문 조사 데이터]</li><li>[!UICONTROL 콜 센터 데이터]</li><li>[!UICONTROL 제품 데이터]</li><li> [!UICONTROL 계정 데이터]</li><li> [!UICONTROL 트랜잭션 데이터]</li><li>[!UICONTROL 고객 피드백 데이터]</li><li> [!UICONTROL 기타]</li></ul>이 필드를 사용하여 사용 중인 데이터 소스 유형을 조사합니다. |

   {style="table-layout:auto"}

1. **[!UICONTROL 새로운 데이터 가져오기]** 섹션에서 **[!UICONTROL 모든 새로운 데이터 가져오기]** 옵션을 비활성화한 상태로 둡니다.

   내역 데이터에 대한 Analytics 소스 커넥터 데이터 세트를 사용하고 있기 때문에 이 데이터 세트에 수집된 이후의 데이터를 가져오고 싶지 않을 것입니다.

1. **[!UICONTROL 데이터 세트 채우기]** 섹션에서 **[!UICONTROL 채우기 요청]**&#x200B;을 선택합니다.

1. Customer Journey Analytics에 연결 채우기를 포함할 기간을 정의하려면 시작 및 종료 날짜를 입력하거나 캘린더 아이콘 ![캘린더](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)를 선택합니다.

   채우기를 요청할 때는 날짜를 명확하게 지정합니다. 여러 가지 요소에 따라 다음 중 하나를 수행할 수 있습니다.

   * Web SDK 구현에서 데이터를 처음 수집하기 시작한 날짜와 동일한 종료 날짜를 선택합니다.

   * Web SDK 구현에서 데이터를 처음 수집하기 시작한 날짜 직후의 종료 날짜를 선택한 다음 데이터 보기 세그먼트를 사용하여 겹치는 데이터를 세그먼트화합니다.

   * 데이터가 더 많이 겹치는 종료 날짜를 선택한 다음 데이터 보기 세그먼트를 사용하여 겹치는 데이터를 세그먼트화합니다.

     **참고:** 이 옵션은 연결에 더 많은 행이 있기 때문에 비용이 증가할 것입니다.

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the segment. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. **[!UICONTROL 대기열 채우기]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 세트 추가]**&#x200B;를 선택한 다음 **[!UICONTROL 저장]**&#x200B;을 선택하여 연결을 저장합니다.

1. (조건부) 조회 데이터 세트를 사용하는 경우, 조회 데이터 세트를 생성하고 연결에 추가해야 합니다. 자세한 내용은 [Customer Journey Analytics에서 데이터를 분류하기 위한 조회 데이터 세트 만들기](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)를 참조하십시오.

   이는 Web SDK 구현을 구성할 때 아직 수행하지 않은 경우에만 필요합니다.

{{upgrade-final-step}}
