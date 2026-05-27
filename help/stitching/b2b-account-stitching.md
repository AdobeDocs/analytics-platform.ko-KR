---
title: B2B 계정 결합
description: Customer Journey Analytics의 B2B 계정 결합은 계정 정보로 이벤트 데이터 세트를 강화하고 B2B 데이터 전반에서 완전한 여정 분석을 가능하게 하는 방법을 알아봅니다.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
role: Admin
autotag-review: '2026-05-19T11:01:07.331Z'
TQID: 'https://experienceleague.adobe.com/-7rHOhYVCp-nSMqdE7YlAlCJ0zRQYvPOViMHSCNuKV8'
product_v2: id: d3f42e9e-bb51-4077-a732-358b801d8b29id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 11156e1f2db094595cc3333ccb0b896037da4715
workflow-type: tm+mt
source-wordcount: 1178
ht-degree: 21%

---

# B2B 계정 결합

B2B 계정 결합은 계정 정보로 이벤트 데이터 세트를 강화하고 Customer Journey Analytics의 전체 고객 여정 전반에서 전체 분석을 가능하게 합니다. 이벤트에 수집을 위해 Customer Journey Analytics B2B edition에 필요한 계정 ID가 없는 경우 계정 결합은 사용자가 제공한 [개인-계정 간 매핑 데이터 세트](#prerequisites)를 사용하여 해당 정보를 자동으로 파생하고 추가합니다.

계정 결합을 사용하지 않으면, 계정 ID가 포함되지 않은 모든 이벤트가 수집 중에 삭제됩니다. 계정 결합은 각 이벤트에서 사용자와 연결된 계정을 검색하고 이벤트가 수집될 때 및 소급하여 계정 ID를 추가하여 이 장벽을 제거합니다.

>[!NOTE]
>
>B2B 계정을 연결하려면 기능을 구성하려면 먼저 환경에서 [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md)에 대한 권한이 있어야 합니다.

계정 결합은 데이터 세트에 대해 다음 작업을 수행합니다.

* **개인 ID 상승**: 각 이벤트의 개인 ID는 ID 그래프를 사용하여 구성된 ID 네임스페이스로 상승됩니다.
* **누락된 계정 정보 추가**: 개인 ID가 포함된 이벤트의 경우 [개인-계정 매핑](#prerequisites)을 사용하여 계정 정보를 파생하고 추가합니다. 이벤트 자체에 대한 모든 계정 정보는 대체 방법으로 사용됩니다.

## 사전 요구 사항

B2B 계정 결합을 활성화하기 전에 Adobe Experience Platform에서 다음 데이터 세트를 준비하십시오.

| 데이터 세트 | 필수 여부 | 설명 |
|---|---|---|
| **개인-계정 데이터 세트** | 필수 여부 | 최소한 개인 ID(네임스페이스 있음)와 계정 ID가 포함된 조회(레코드, 비시계열) 데이터 세트입니다. 이러한 ID는 사용자-계정 관계 맵을 파생하는 데 사용됩니다. |

>[!IMPORTANT]
>
>**[!UICONTROL 개인 대 계정]** 데이터 세트의 개인 ID 필드는 스키마에서 ID로 표시해야 합니다.

## 계정 결합 활성화 {#enable-account-stitching}

연결 수준에서 B2B 계정 결합을 활성화하고 구성한 다음 해당 연결 내의 개별 이벤트 데이터 세트에서 계정 결합을 활성화합니다.

### B2B 결합 설정 구성 {#configure-b2b-stitching-settings}

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_open_configuration"
>title="B2B 계정 결합 구성"
>abstract="**[!UICONTROL B2B 결합 구성 열기]**&#x200B;를 선택하여 B2B 계정 결합을 구성합니다. 연결이 아직 저장되지 않은 경우 구성에 **[!UICONTROL _저장되지 않은 변경 사항_]** 레이블이 지정됩니다."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_identifier_namespace"
>title="개인 식별자 네임스페이스"
>abstract="개인 ID를 향상시키고자 하는 개인 식별자 네임스페이스(예: 이메일)를 선택합니다."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_to_account_dataset"
>title="개인 - 계정 데이터 세트"
>abstract="개인 ID를 계정 ID에 매핑하는 조회 데이터 세트를 선택합니다."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person"
>title="개인"
>abstract="개인 ID가 포함된 데이터 세트에서 필드를 선택합니다. 해당 필드는 ID로 표시되어야 하며 **[!UICONTROL 계정]** 필드 또는 **[!UICONTROL 시작 시간]** 필드와 같을 수 없습니다."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_account"
>title="계정"
>abstract="계정 ID가 포함된 데이터 세트에서 필드를 선택합니다. 해당 필드는 **[!UICONTROL 개인]** 필드 또는 **[!UICONTROL 시작 시간]** 필드와 같을 수 없습니다."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_start_time"
>title="시작 시간"
>abstract="개인-계정 관계가 활성화된 시기를 나타내는 타임스탬프 필드를 선택합니다."
>additional-url=""
additional-url=""


1. Customer Journey Analytics에서 **[!UICONTROL 연결]** 및 [새 연결 만들기](/help/connections/create-connection.md#create-a-connection) 또는 [기존 연결 편집](/help/connections/create-connection.md#edit-a-connection)으로 이동합니다.

1. **[!UICONTROL 연결 설정]**&#x200B;에서 **[!UICONTROL 기본 ID]**&#x200B;을(를) ![빌드](/help/assets/icons/Building.svg) **[!UICONTROL 계정]**(으)로 설정합니다.

1. **[!UICONTROL B2B 결합 구성 열기]**&#x200B;를 선택합니다.

   ![B2B 계정 제목 구성](assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >저장되지 않은 연결에 대해 이전에 구성된 B2B 결합 구성이 **[!UICONTROL _저장되지 않은 변경 내용_]**(으)로 표시됩니다. 이전에 구성한 B2B 결합 구성에 대해 **[!UICONTROL 선택적 컨테이너]**&#x200B;을(를) 수정할 수 없습니다.

1. **[!UICONTROL B2B 결합 구성]** 대화 상자에서:

   ![B2B 결합 구성](assets/b2b-stitching-configuration.png)

   1. **[!UICONTROL 사용자]** 섹션을 구성하십시오.

      * 개인 ID를 높이고자 하는 **[!UICONTROL 개인 식별자 네임스페이스]**(예: **[!UICONTROL 이메일]**)를 선택하십시오. 이 필드는 반드시 입력해야 합니다.

   1. **[!UICONTROL 계정에 대한 사용자]** 아래의 **[!UICONTROL 계정]** 섹션을 구성하십시오.

      | 필드 | 필수 여부 | 설명 |
      |---|:---:|---|
      | **[!UICONTROL 계정에 대한 개인 데이터 세트]** | ![필수](/help/assets/icons/Required.svg) | 개인을 계정에 매핑하는 조회(레코드 또는 비시계열 데이터 세트)를 선택합니다. |
      | **[!UICONTROL 개인]** | ![필수](/help/assets/icons/Required.svg) | 개인 ID가 포함된 데이터 세트에서 필드를 선택합니다. 해당 필드는 ID로 표시되어야 하며 **[!UICONTROL 계정]** 필드 또는 **[!UICONTROL 시작 시간]** 필드와 같을 수 없습니다. |
      | **[!UICONTROL 계정]** | ![필수](/help/assets/icons/Required.svg) | 계정 ID가 포함된 데이터 세트에서 필드를 선택합니다. 해당 필드는 **[!UICONTROL 개인]** 필드 또는 **[!UICONTROL 시작 시간]** 필드와 같을 수 없습니다. |
      | **시작 시간** | | 개인-계정 관계가 활성화된 시기를 나타내는 타임스탬프 필드를 선택합니다. |

      >[!NOTE]
      >
      >필드 옵션을 로드하는 동안 오류가 발생하면 드롭다운 메뉴가 비어 있고 영향을 받는 각 필드 아래에 오류 표시기가 나타납니다. 데이터 세트 스키마를 확인하고 다시 시도하십시오.

   1. **[!UICONTROL 저장]**&#x200B;을 선택하여 **[!UICONTROL B2B 결합 구성]** 대화 상자를 닫고 연결 설정으로 돌아갑니다.

   1. 연결을 [저장](#save)할 때까지 **B2B 결합 구성 열기** 단추 옆에 **[!UICONTROL _저장하지 않은 변경 내용_]** 표시기가 나타납니다.


### 이벤트 데이터 세트에서 B2B 결합 활성화


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_enable_person_to_account"
>title="개인 - 계정 결합 활성화"
>abstract="활성화된 경우 이 데이터 세트는 B2B 계정 결합을 사용합니다. 개인-계정 데이터 세트를 기반으로 계정 ID를 조회하려면 필수 **[!UICONTROL 개인 ID]**&#x200B;을(를) 선택하십시오.<br/>사용하지 않도록 설정된 경우 이 데이터 집합은 B2B 계정 결합을 *사용하지 않습니다*. 대신 필요한 **[!UICONTROL 계정 ID]**&#x200B;를 선택해야 합니다."
>additional-url=""
additional-url=""


연결 수준에서 B2B 결합을 구성한 후에는 결합할 각 이벤트 데이터 세트에 대해 개별적으로 B2B 계정 결합을 활성화해야 합니다.

1. 연결 설정에서 **[!UICONTROL 데이터 세트 추가]**&#x200B;를 선택하거나 기존 이벤트 데이터 세트에 대한 설정을 엽니다.<br/>자세한 내용은 [데이터 세트 추가](/help/connections/create-connection.md#add-datasets) 또는 [데이터 세트 편집](/help/connections/create-connection.md#edit-a-dataset)을 참조하십시오.

1. B2B 계정 결합을 구성할 특정 이벤트 데이터 세트의 경우 **[!UICONTROL 개인을 계정에 연결 활성화]**&#x200B;로 전환하십시오.

>[!BEGINTABS]

>[!TAB 날짜]

**[!UICONTROL 개인 계정 연결 활성화]**&#x200B;가 **on**&#x200B;인 경우 데이터 세트에 대한 B2B 계정 연결을 구성했습니다.

* 개인 ID 구성이 필요합니다. 해당 개인 ID는 [개인 대 계정 데이터 세트](#prerequisites)를 기반으로 계정 ID를 조회하는 데 사용됩니다.
* 계정 ID 구성은 선택 사항입니다.

](assets/b2b-event-dataset-stitching-on.png)의 이벤트 데이터 세트에 대한 ![B2B 계정 연결

>[!TAB 해제]

**[!UICONTROL 개인 계정 연결 활성화]**&#x200B;가 **해제**&#x200B;인 경우 데이터 세트에 대해 B2B 계정 연결이 *구성되지*&#x200B;않았습니다.

* 계정 ID를 구성해야 합니다.
* 개인 ID 구성은 선택 사항입니다.

![이벤트 데이터 세트에 대한 B2B 계정 연결 해제](assets/b2b-event-dataset-stitching-off.png)


>[!ENDTABS]




### 저장

B2B 결합 구성을 구성하고 데이터 세트 추가 또는 편집을 완료한 후 **[!UICONTROL 저장]**&#x200B;을(를) 선택하여 연결을 저장합니다.

>[!IMPORTANT]
>
>연결이 저장되면 B2B 결합 구성을 변경할 수 없습니다. 저장한 후 설정을 보려면 **B2B 결합 구성 열기**&#x200B;를 선택합니다. 모든 필드는 읽기 전용 상태로 표시됩니다. 또한 [개인-계정 간 매핑](#prerequisites)에 사용되는 데이터 세트가 Experience Platform에서 삭제되면 이 연결이 삭제됩니다.

## 데이터 업데이트 일정

계정 연결은 매일 [개인-계정 데이터 세트](#prerequisites)에서 ID 맵을 파생하고 이 정보를 사용하여 다음 일정에 따라 연결을 사용하도록 설정된 데이터 세트를 업데이트합니다.

| 재생 | 빈도 | 데이터 창 |
|---|---|---|
| 단기 | 주별 | 지난 7일 |
| 장기간 | 월별 | 최근 3개월 |

## 개인 정보 보호 및 데이터 위생

계정 결합은 B2C 결합 동작과 일치하는 개인 ID에 대한 표준 개인 정보 및 위생 요청을 처리합니다. 개인 ID가 나중에 개인 정보 보호 또는 위생 요청을 통해 제거되는 경우 ID 그래프를 사용하여 수행되는 관련 연결이 반전됩니다.

결합을 통해 이벤트에 추가된 계정, 계정 ID 및 글로벌 계정 ID와 같은 B2B 엔티티는 개인 정보 보호 또는 위생 요청의 일부로 제거되지 않습니다. 이러한 값에는 개인 식별 정보가 포함되어 있지 않으므로 이러한 값을 제거할 법적 의무가 존재하지 않습니다.

>[!MORELIKETHIS]
>
>* [결합 개요](overview.md)
>* [B2B에 대한 연결 구성](../connections/create-connection.md)
>* [결합에 대해 자주 묻는 질문](faq.md)

