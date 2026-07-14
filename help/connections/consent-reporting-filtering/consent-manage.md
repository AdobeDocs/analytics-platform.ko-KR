---
title: 동의 보고 및 필터링 구성 관리
description: 동의 보고 및 필터링 구성을 보고, 편집하고, 삭제하는 방법과 동의 정책 조회 데이터 세트가 Customer Journey Analytics에서 동기화되는 방법에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Privacy
role: Admin
hold: true
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2: id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: eafeab50e86b3e98f372c70a0fd43494015ca002
workflow-type: tm+mt
source-wordcount: 452
ht-degree: 5%

---

# 동의 보고 및 필터링 구성 관리

[동의 보고 및 필터링 구성을 만들기](/help/connections/consent-reporting-filtering/consent-configure.md)한 후 이를 보거나 편집하거나 삭제할 수 있습니다.

시스템 관리자만 동의 보고 및 필터링 구성을 관리할 수 있습니다.

개요 정보는 [동의 보고 및 필터링 개요](/help/connections/consent-reporting-filtering/consent-overview.md)를 참조하십시오.

## 기존 구성 보기

기존 구성을 보려면 다음 작업을 수행하십시오.

1. Customer Journey Analytics에서 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 동의 보고 및 필터링]**&#x200B;을 선택합니다.

   각 구성에 대해 다음 정보 열을 사용할 수 있습니다.

   * **[!UICONTROL 작성자]**: 구성을 만든 사용자입니다.

   * **[!UICONTROL 샌드박스]**: 프로필 데이터 세트가 포함된 Experience Platform 샌드박스입니다.

   * **[!UICONTROL 연결]**: 구성이 적용되는 연결입니다.

   * **[!UICONTROL 필터링]**: 필터링이 활성화된 마케팅 액션(있는 경우).

   * **[!UICONTROL 만든 날짜]**: 구성을 만든 날짜입니다.

   * **[!UICONTROL 마지막 수정일]**: 구성을 마지막으로 수정한 날짜입니다.

   * **[!UICONTROL 상태]**: 구성의 상태입니다.

   열 아이콘 ![열 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)을 선택하고 숨길 열을 선택 취소한 다음 **[!UICONTROL 적용]**&#x200B;을 선택하여 열을 숨길 수 있습니다.

1. (선택 사항) 구성 목록을 필터링하려면 **필터** ![필터 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)을 선택한 후 다음 조건 중 하나를 기준으로 필터링합니다.

   * **[!UICONTROL 연결]**

   * **[!UICONTROL 작성자]**

   * **[!UICONTROL 샌드박스]**

   * **[!UICONTROL 상태]**

## 구성 편집

>[!IMPORTANT]
>
>필터링 변경 사항은 구성 변경 사항을 저장한 후 수집되는 데이터에만 영향을 줍니다. 필터링을 활성화해도 변경 전에 수집된 동의하지 않는 방문자 데이터는 제거되지 않으며, 필터링을 비활성화해도 필터링이 활성화된 동안 제외된 데이터는 복구되지 않습니다.

기존 구성을 편집하는 방법:

1. Customer Journey Analytics에서 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 동의 보고 및 필터링]**&#x200B;을 선택합니다.

1. 편집할 구성의 이름을 선택합니다.

   또는

   편집할 구성 옆의 확인란을 선택한 다음 **[!UICONTROL 편집]**&#x200B;을 선택합니다.

1. 변경한 다음 **[!UICONTROL 저장]**&#x200B;을 선택합니다.

## 구성 삭제

기존 구성을 삭제하려면 다음을 수행합니다.

1. Customer Journey Analytics에서 **[!UICONTROL 데이터 관리]** > **[!UICONTROL 동의 보고 및 필터링]**&#x200B;을 선택합니다.

1. 삭제할 구성 옆의 확인란을 선택한 다음 **[!UICONTROL 삭제]**&#x200B;를 선택합니다.

## 동의 정책 조회 데이터 세트가 동기화되는 방식

Customer Journey Analytics은 동의 정책 조회 데이터 세트를 Experience Platform과 자동으로 동기화합니다. Experience Platform에서 동의 정책을 만들거나, 업데이트하거나, 이름을 바꾸거나, 삭제하면 조회 데이터 세트의 해당 정책 이름과 설명이 업데이트됩니다.

다음 사항에 유의하십시오.

* 샌드박스당 최대 1개의 동의 정책 조회 데이터 세트가 있습니다. 동일한 샌드박스의 여러 구성이 해당 조회 데이터 세트를 공유합니다.
* 정책 이름과 설명은 Experience Platform에서 가져오므로 조회 데이터 세트를 직접 편집하지 않고 Experience Platform에서 정책 메타데이터를 업데이트하십시오.
