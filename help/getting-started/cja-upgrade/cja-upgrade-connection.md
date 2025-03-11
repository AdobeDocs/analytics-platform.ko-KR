---
title: Customer Journey Analytics에 대한 스키마 만들기
description: Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 22d3e7b8-4a4d-48a8-a98d-5172a9876286
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '1629'
ht-degree: 94%

---

# Customer Journey Analytics와 함께 사용할 연결 만들기 및 구성 {#upgrade-create-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-connection"
>title="Customer Journey Analytics에 연결 만들기"
>abstract="연결을 통해 Adobe Experience Platform의 데이터를 Customer Journey Analytics 보고에 최적화된 형식으로 변환할 수 있습니다. Customer Journey Analytics에서 연결을 만드는 것은 간단하며, 완료하는 데 몇 분밖에 걸리지 않습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/connections/create-connection.md -->

다음 정보는 연결을 만들고 구성하는 방법과 더불어 만든 연결에 Experience Platform 데이터 세트를 추가하는 방법을 설명합니다. 연결 만들기 및 구성에 대한 자세한 내용은 [연결 만들기 또는 편집](/help/connections/create-connection.md)을 참조하세요.

## 연결 만들기 및 구성 {#create-connection}

1. Customer Journey Analytics에서 **[!UICONTROL 연결]** 탭을 선택합니다.
1. **[!UICONTROL 새 연결 만들기]**&#x200B;를 선택합니다.

   ![제목 없는 연결 설정](assets/create-conn1.png)

1. 연결 설정을 구성합니다.

   | 설정 | 설명 |
   | --- | --- |
   | **[!UICONTROL 연결 이름]** | 연결의 고유한 이름을 입력합니다. |
   | **[!UICONTROL 연결 설명]** | 이 연결의 목적에 대해 설명합니다. |
   | **[!UICONTROL 샌드박스]** | 연결을 만들 데이터 세트가 포함된 Experience Platform의 샌드박스를 선택합니다.<p>Adobe Experience Platform은 디지털 경험 애플리케이션을 개발하고 발전시키는 데 도움이 되는 단일 플랫폼 인스턴스를 별도의 가상 환경으로 분할하는 [샌드박스](https://experienceleague.adobe.com/ko/docs/experience-platform/sandbox/home)를 제공합니다. 샌드박스를 데이터 세트가 포함된 “데이터 사일로”로 간주할 수 있습니다. 샌드박스는 데이터 세트에 대한 액세스를 제어하는 데 사용됩니다.<p>샌드박스를 선택하면 왼쪽 레일에 해당 샌드박스에서 가져올 수 있는 모든 데이터 세트가 표시됩니다. |
   | **[!UICONTROL 롤링 데이터 기간 활성화]** | 이 확인란이 선택되어 있으면 Customer Journey Analytics 데이터 보존을 연결 수준에서 개월(1개월, 3개월, 6개월 등) 단위의 롤링 기간으로 정의할 수 있습니다.<p>데이터 보존은 이벤트 데이터 세트 타임스탬프를 기반으로 하며 이벤트 데이터 세트에만 적용됩니다. 적용 가능한 타임스탬프가 없기 때문에 프로필 또는 조회 데이터 세트에 대한 롤링 데이터 기간 설정이 없습니다. 그러나 연결에 프로필 또는 조회 데이터 세트(하나 이상의 이벤트 데이터 세트 제외)가 포함된 경우 해당 데이터는 동일한 기간 동안 유지됩니다.<p> 주요 이점은 적용 가능하고 유용한 데이터에 대해서만 저장하거나 보고하고 더 이상 유용하지 않은 오래된 데이터를 삭제한다는 것입니다. 계약 한도를 유지하고 초과 비용의 위험을 줄이는 데 도움이 됩니다.<p>기본값(선택 해제)을 그대로 두면 보존 기간이 Adobe Experience Platform 데이터 보존 설정으로 대체됩니다. Experience Platform에 25개월 분량의 데이터가 있는 경우 Customer Journey Analytics는 채우기를 통해 25개월 분량의 데이터를 받습니다. 플랫폼에서 이러한 개월 중 10개월을 삭제하면 Customer Journey Analytics는 나머지 15개월을 유지합니다. |
   | **[!UICONTROL 데이터 세트 추가]** (아래 참조) | 데이터 세트 목록에 데이터 세트가 표시되지 않으면 데이터 세트를 추가합니다. |
   | **[!UICONTROL 데이터 세트 이름]** | Customer Journey Analytics으로 가져올 데이터 세트를 한 개 이상 선택하고 **[!UICONTROL 추가]**&#x200B;를 선택합니다.<p>(선택할 데이터 세트가 여러 개인 경우 데이터 세트 목록 위에 있는 데이터 세트 검색 막대를 사용하여 올바른 데이터 세트를 검색할 수 있습니다.) |
   | **[!UICONTROL 마지막으로 업데이트됨]** | 이벤트 데이터 세트의 경우에만 이 설정이 Experience Platform의 이벤트 기반 스키마에서 기본 타임스탬프 필드로 자동 설정됩니다. “N/A”는 이 데이터 세트에 데이터가 없음을 의미합니다. |
   | **[!UICONTROL 레코드 수]** | Experience Platform의 데이터 세트에 대한 지난달의 총 레코드입니다. |
   | **[!UICONTROL 스키마]** | Adobe Experience Platform에서 데이터 세트를 만드는 데 사용한 [스키마](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/schema/composition)입니다. |
   | **[!UICONTROL 데이터 세트 유형]** | 이 연결에 추가한 각 데이터 세트에 대해 가져오는 데이터를 기반으로 데이터 세트 유형을 Customer Journey Analytics에서 자동으로 설정합니다. 이벤트 데이터, 프로필 데이터 및 조회 데이터의 3가지 데이터 세트 유형이 있습니다. 데이터 세트 유형에 대한 설명은 아래 테이블을 참조하십시오. |
   | **[!UICONTROL 세부 기간]** | 데이터 세트의 데이터 세부 기간입니다. 요약 데이터 세트에만 적용됩니다. |
   | **[!UICONTROL 데이터 소스 유형]** | 데이터 세트의 데이터 소스 유형입니다. 요약 데이터 세트에 해당되지 않습니다. |
   | **[!UICONTROL 개인 ID]** | 사용 가능한 ID의 드롭다운 목록에서 개인 ID를 선택합니다. 이러한 ID는 Experience Platform의 데이터 세트 스키마에 정의되어 있습니다. ID 맵을 개인 ID로 사용하는 방법에 대한 자세한 내용은 아래를 참조하십시오.<p>중요: 선택할 개인 ID가 없는 경우 하나 이상의 개인 ID가 스키마에 정의되어 있지 않음을 의미합니다. [이 비디오](https://www.youtube.com/watch?v=G_ttmGl_LRU)를 보고 Experience Platform에서 ID를 정의하는 방법을 확인하십시오. |
   | **[!UICONTROL 키]** | 조회 데이터 세트(예: _id)에만 해당됩니다. |
   | **[!UICONTROL 일치하는 키]** | 조회 데이터 세트(예: _id)에만 해당됩니다. |
   | **[!UICONTROL 새 데이터 가져오기]** | 켜기 또는 끄기로 설정합니다. |
   | **[!UICONTROL 채우기 데이터]** | 데이터 세트의 데이터를 채우도록 요청할 수 있습니다. 예를 들어 지난 7일간의 데이터를 채우도록 요청할 수 있습니다. 데이터 세트를 올바르게 구성하고 연결을 테스트하십시오. 모두 정상적인 경우 나머지 모든 데이터를 간편하게 다시 채울 수 있습니다.<p>또한 데이터 세트별로 새 데이터 가져오기를 활성화할 수 있습니다. |
   | **[!UICONTROL 채우기 상태]** | 이 상태는 데이터 채우기가 처리 중인지 여부를 나타냅니다. |

   {style="table-layout:auto"}

## 데이터 세트 추가 및 구성 {#add-dataset}

연결을 만들 때 Experience Platform 데이터 세트를 추가할 수 있습니다.

1. 연결 설정 대화 상자에서 **[!UICONTROL 데이터 세트 추가]**&#x200B;를 선택합니다.

1. [!UICONTROL 데이터세트 선택] 단계에서는 Experience Platform 데이터 세트의 목록이 표시됩니다.

   ![데이터 세트 선택](assets/select-datasets.png)

   각 데이터 세트에 대해, 목록은 다음과 같이 나타납니다.

   | 열 | 설명 |
   |---|---|
   | 데이터 세트 | 데이터 세트의 이름입니다. Experience Platform의 데이터 세트로 사용자를 이동시킬 이름을 선택합니다. 데이터 세트에 대한 더 자세한 내용이 포함된 팝업이 표시되도록 하려면 ![정보](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)를 선택합니다. **[!UICONTROL 플랫폼에서 편집]**&#x200B;을 선택하면 Experience Platform에서 바로 데이터 세트를 편집할 수 있습니다. |
   | 데이터 세트 유형 | 데이터 세트 유형: 이벤트, 프로필, 조회 또는 요약. |
   | 레코드 수 | Experience Platform의 데이터 세트에 대한 지난달의 총 레코드입니다. |
   | 스키마 | 데이터 세트의 스키마입니다. Experience Platform의 스키마로 사용자를 이동시킬 이름을 선택합니다. |
   | 마지막 배치 | Experience Platform에서 수집된 마지막 배치의 상태입니다. 더 자세한 내용은 [배치 상태](https://experienceleague.adobe.com/ko/docs/experience-platform/ingestion/batch/troubleshooting#batch-states)를 참조하시기 바랍니다. |
   | 데이터 세트 ID | 데이터 세트의 ID입니다. |
   | 마지막으로 업데이트됨 | 데이터 세트에서 마지막으로 업데이트된 타임스탬프입니다. |


1. 하나 이상의 데이터 세트를 선택하고 **[!UICONTROL 다음]**&#x200B;을 선택합니다. 하나 이상의 이벤트 데이터 세트가 연결의 일부가 되어야 합니다.
   * 데이터 세트 목록에 표시되는 열을 변경하려면 ![열 설정](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)을 선택한 다음 [!UICONTROL 테이블 맞춤화] 대화 상자에 표시할 열을 선택합니다.
   * 특정 데이터 세트를 검색하려면 ![검색](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) 검색 필드를 사용합니다.
   * 선택한 데이터 세트 표시 또는 숨기기 간 전환하려면 ![선택](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg) **[!UICONTROL 선택 항목 숨기기]** 또는 **[!UICONTROL 선택 항목 표시]**&#x200B;를 선택합니다.
   * 선택한 데이터 세트 목록에서 데이터 세트를 제거하려면 ![닫기](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg)를 사용합니다. 선택한 데이터 세트를 모두 제거하려면 **[!UICONTROL 모두 지우기]**&#x200B;를 선택합니다.




1. 이제 데이터 세트를 하나씩 구성합니다.

   ![데이터 세트 구성](assets/add-dataset.png)

   | 설정 | 설명 |
   | --- | --- |
   | **[!UICONTROL 개인 ID]** | 이벤트 및 프로필 데이터 세트에만 사용할 수 있습니다. 사용 가능한 ID의 드롭다운 목록에서 개인 ID를 선택합니다. 이러한 ID는 Experience Platform의 데이터 세트 스키마에 정의되어 있습니다. ID 맵을 개인 ID로 사용하는 방법에 대한 자세한 내용은 아래를 참조하십시오.<p>선택할 개인 ID가 없는 경우 하나 이상의 개인 ID가 스키마에 정의되어 있지 않음을 의미합니다. 자세한 내용은 [UI에서 ID 필드 정의](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/ui/fields/identity)를 참조하십시오. <p>선택한 개인 ID의 값은 대소문자를 구분하는 것으로 간주됩니다. 예를 들어 `abc123` 및 `ABC123`은 서로 다른 두 값입니다. |
   | **[!UICONTROL 타임스탬프]** | 이벤트 및 요약 데이터 세트의 경우에만 이 설정이 Experience Platform의 이벤트 기반 스키마에서 기본 타임스탬프 필드로 자동 설정됩니다. |
   | **[!UICONTROL 키]** | 조회 데이터 세트에만 사용할 수 있습니다. 조회 데이터 세트에 사용할 키입니다. |
   | **[!UICONTROL 일치하는 키]** | 조회 데이터 세트에만 사용할 수 있습니다. 이벤트 데이터 세트 중 하나에 연결할 일치하는 키입니다. 이 목록이 비어 있다면 이벤트 데이터 세트를 추가하거나 구성하지 않았을 가능성이 높습니다. |
   | **[!UICONTROL 시간대]** | 요약 데이터에만 사용할 수 있습니다. 시계열 요약 데이터에 적합한 시간대를 선택합니다. |
   | **[!UICONTROL 데이터 소스 유형]** | 데이터 소스 유형을 선택합니다. <br/>데이터 소스 유형에는 다음이 포함됩니다. <ul><li>[!UICONTROL 웹 데이터]</li><li>[!UICONTROL 모바일 앱 데이터]</li><li>[!UICONTROL POS 데이터]</li><li>[!UICONTROL CRM 데이터]</li><li>[!UICONTROL 설문 조사 데이터]</li><li>[!UICONTROL 콜 센터 데이터]</li><li>[!UICONTROL 제품 데이터]</li><li> [!UICONTROL 계정 데이터]</li><li> [!UICONTROL 트랜잭션 데이터]</li><li>[!UICONTROL 고객 피드백 데이터]</li><li> [!UICONTROL 기타]</li></ul>이 필드를 사용하여 사용 중인 데이터 소스 유형을 조사합니다. |
   | **[!UICONTROL 새 데이터 가져오기]** | 지속적인 연결을 설정하려면 이 옵션을 활성화합니다. 지속적인 연결을 통해 데이터 세트에 추가된 새 데이터 배치를 Workspace에서 자동으로 사용할 수 있습니다. |
   | **[!UICONTROL 데이터 세트 채우기]** | **[!UICONTROL 기존의 모든 데이터 다시 채우기]**&#x200B;를 활성화하여 기존의 모든 데이터를 다시 채웁니다.<br/><br/>특정 기간의 내역 데이터를 다시 채우려면 **[!UICONTROL 다시 채우기 요청]**&#x200B;을 선택합니다. 최대 10개의 데이터 세트 채우기 기간을 정의할 수 있습니다.<ol><li>시작 및 종료 데이터를 입력하거나 ![캘린더](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)를 사용하여 날짜를 선택하여 기간을 정의합니다.</li><li>**[!UICONTROL 대기열 다시 채우기]**&#x200B;를 선택하여 목록에 다시 채우기를 추가하거나 **[!UICONTROL 취소]**&#x200B;를 선택하여 취소합니다.</li></ol>각 항목에 대해 ![편집](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)을 선택하여 기간을 편집하거나 ![삭제](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg)를 선택하여 항목을 삭제합니다.<br/><br/>다시 채우기 이후에는<ul><li>각 데이터 세트를 개별적으로 채울 수 있습니다.</li><li>연결하는 데이터 세트에 추가된 새 데이터에 우선순위를 두므로 이 새 데이터의 지연 시간이 가장 짧습니다.</li><li>모든 채우기 (이전) 데이터는 더 느린 속도로 가져옵니다. 내역 데이터의 양은 지연 시간에 영향을 미칩니다.</li><li>Analytics 소스 커넥터는 프로덕션 샌드박스의 경우 (크기에 상관없이) 최대 13개월의 데이터를 가져옵니다. 비프로덕션 샌드박스의 다시 채우기는 3개월로 제한됩니다.</li></ul> |
   | **[!UICONTROL 데이터 세트 변환]** | 특정 B2B 조회 데이터 세트의 경우 적절한 B2B 개인 기반 보고 시나리오에 대해 데이터 세트 변환을 활성화할 수 있습니다. |
   | **[!UICONTROL 채우기 상태]** | 가능한 상태 표시기는 다음과 같습니다.<ul><li>성공</li><li>X 채우기 처리</li><li>꺼짐</li></ul> |
   | **[!UICONTROL 데이터 세트 ID]** | 이 ID는 자동으로 생성됩니다. |
   | **[!UICONTROL 설명]** | 이 데이터 세트가 생성될 때 제공된 설명입니다. |
   | **[!UICONTROL 데이터 세트 크기]** | 데이터 세트 크기입니다. |
   | **[!UICONTROL 스키마]** | Adobe Experience Platform에서 데이터 세트를 만드는 데 사용한 스키마입니다. |
   | **[!UICONTROL 데이터 세트]** | 데이터 세트의 이름입니다. |
   | **[!UICONTROL 미리보기: *데이터 세트 이름&#x200B;*]** | 날짜, 내 ID 및 식별자 열을 사용하여 데이터 세트를 미리 봅니다. |
   | **[!UICONTROL 제거]** | 전체 연결을 삭제하지 않고 데이터 세트를 삭제하거나 제거하고 개인 ID를 변경할 수 있습니다. 삭제 또는 제거하게 되면 데이터 수집과 관련된 비용과 전체 연결 및 관련 데이터 보기를 다시 만드는 번거로운 프로세스를 줄일 수 있습니다. |

   {style="table-layout:auto"}

{{upgrade-final-step}}
