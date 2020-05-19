---
title: 연결 만들기
description: 플랫폼 데이터 세트에 연결하는 방법이 Customer Journey Analytics에 설명되어 있습니다.
translation-type: tm+mt
source-git-commit: 204eb143d513b9b73fad020efabe6891a1253608
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 68%

---


# 연결 만들기

A connection lets you integrate datasets from [!DNL Adobe Experience Platform] into [!UICONTROL Workspace]. In order to report on [!DNL Experience Platform] datasets, you first have to establish a connection between datasets in [!DNL Experience Platform] and [!UICONTROL Workspace].

비디오 개요를 보려면 [여기](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html)를 클릭하십시오.

>[!IMPORTANT] 여러 [!DNL Experience Platform] 데이터 세트를 하나의 연결로 결합할 수 있습니다.

1. [https://analytics.adobe.com](https://analytics.adobe.com)으로 이동합니다.

1. Click the **[!UICONTROL Connections]** tab.

1. 오른쪽 **[!UICONTROL 상단에 있는 새 연결]** 만들기를 클릭합니다.

   ![연결 생성](assets/create-connection.png)

1. 연결을 만들 데이터 세트/s가 포함된 경험 플랫폼의 샌드박스를 선택합니다.

   Adobe Experience Platform은 디지털 경험 애플리케이션을 개발하고 발전시키는 데 도움이 되는 단일 플랫폼 인스턴스를 별도의 가상 환경으로 분할하는 [샌드박스를](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) 제공합니다. 샌드박스를 데이터 세트가 포함된 &quot;데이터 사일로&quot;로 간주할 수 있습니다. 샌드박스는 데이터 세트에 대한 액세스를 제어하는 데 사용됩니다. 샌드박스 간에 데이터에 액세스할 수 없습니다. 샌드박스를 선택하면 왼쪽 레일은 해당 샌드박스의 모든 데이터 세트를 표시합니다.

1. Select one or more dataset(s) you want to pull into [!UICONTROL Customer Journey Analytics] and click **[!UICONTROL Add]**.

   선택할 데이터 세트가 많을 경우 데이터 세트 목록 위에 있는 검색 막대를 사용하여 올바른 데이터 세트를 검색할 수 있습니다.

1. Next, for each dataset that you added to this connection, [!UICONTROL Customer Journey Analytics] automatically sets the dataset type based on the data coming in.

   There are 3 different dataset types: [!UICONTROL Event] data, [!UICONTROL Profile] data, and [!UICONTROL Lookup] data.

   | 데이터 세트 유형 | 설명 | 타임스탬프 | 스키마 | 개인 ID |
   |---|---|---|---|---|
   | [!UICONTROL 이벤트] | 시간으로 이벤트를 나타내는 데이터(예: 웹 방문, 상호 작용, 거래, POS 데이터, 설문 조사 데이터, 광고 노출 데이터 등). 예를 들어 고객 ID 또는 쿠키 ID와 타임스탬프가 있는 일반적인 클릭스트림 데이터일 수 있습니다. 이벤트 데이터를 사용하면 개인 ID로 사용할 ID를 유연하게 선택할 수 있습니다. | [UICONTROL Experience Platform]의 이벤트 기반 스키마에서 기본 타임스탬프 필드로 자동 설정됩니다. | 시간 일련 동작 있는 XDM 클래스를 기반으로 하는 모든 내장 또는 스키마 또는 사용자 지정 스키마. 예를 들면 &quot;XDM 경험 이벤트&quot; 또는 &quot;XDM 결정 이벤트&quot;가 해당됩니다. | 포함할 개인 ID를 선택할 수 있습니다. Experience Platform에 정의된 각 데이터 세트 스키마에는 1개 이상의 ID가 ID 네임스페이스로 정의되고 연결된 고유한 ID 세트가 있을 수 있습니다. 이 중 원하는 ID를 개인 ID로 사용할 수 있습니다. 예를 들면 쿠키 ID, 결합된 ID, 사용자 ID, 추적 코드 등이 있습니다. |
   | [!UICONTROL 조회] | 분류 파일과 유사합니다. 이 데이터는 이벤트 또는 프로필 데이터에 있는 값이나 키를 찾는 데 사용됩니다. 예를 들어 이벤트 데이터의 숫자 ID를 제품 이름에 매핑하는 조회 데이터를 업로드할 수 있습니다. | 해당 없음 | XDM 개별 프로필 클래스를 제외하고, &quot;기록&quot; 동작이 있는 XDM 클래스를 기반으로 한 모든 내장 스키마 또는 사용자 지정 스키마. | 해당 없음 |
   | [!UICONTROL 프로필] | Analogous to [!UICONTROL Customer Attributes] - for non-changing and non-temporal attributes. Data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. 예를 들어 고객에 대한 CRM 데이터를 업로드할 수 있습니다. | 해당 없음 | XDM 개인 프로필 클래스를 기반으로 하는 모든 내장 또는 사용자 지정 스키마. | 포함할 개인 ID를 선택할 수 있습니다. [!DNL Experience Platform]에 정의된 각 데이터 세트에는 쿠키 ID, 결합된 ID, 사용자 ID, 추적 코드 등과 같은 개인 ID가 하나 이상 정의된 고유한 ID 세트가 있습니다.<br>![개인 ID](assets/person-id.png)**참고&#x200B;**: ID가 다른 데이터 세트가 포함된 연결을 만들면 이러한 내용이 보고에 반영됩니다. 데이터 세트를 실제로 병합하려면 동일한 개인 ID를 사용해야 합니다. |

1. 다음을 **[!UICONTROL 클릭하여]** 연결 [!UICONTROL 만들기 대화] 상자로 이동합니다.

   ![연결 생성](assets/create-connection2.png)

1. In the [!UICONTROL Create Connection] dialog, define these settings:

   | 필드 | 설명 |
   |---|---|
   | [!UICONTROL 이름 연결] | 연결을 설명하는 이름을 지정합니다. 연결을 저장할 때 반드시 이름을 지정해야 합니다. |
   | [!UICONTROL 설명] | 이 연결을 다른 연결과 구분하려면 세부 사항을 더 추가합니다. |
   | [!UICONTROL 데이터 세트] | 이 연결에 포함된 데이터 세트입니다. |
   | [!UICONTROL 이 연결에 있는 모든 새 데이터 세트를 자동으로 가져옵니다.] | Select this option if you want to establish an ongoing connection, so that any new data batches that get added to the datasets in this connection automatically flow into [!UICONTROL Workspace]. |
   | [!UICONTROL 기존 데이터 모두 가져오기] | 이 옵션을 선택하고 연결을 저장하면 이 연결에 있는 모든 데이터 세트에 대한 기존(이전) 데이터를 모두 [!DNL Experience Platform]에서 가져옵니다. 이후에 여기에 저장된 연결에 추가된 새로운 데이터 세트에 대한 기존의 모든 이전 데이터도 자동으로 가져옵니다. <br>**이 연결이 저장되면 이 설정을 변경할 수 없습니다.** |

   **주의 사항:**

   * 연결하는 모든 데이터 세트에 대한 이전 데이터의 누적 크기가 15억 행을 초과하는 경우 이 크기의 이전 데이터를 가져올 수 없다는 오류 메시지가 표시됩니다. 하지만 10억 개의 이전 데이터 행이 포함된 데이터 세트를 추가하고 해당 데이터를 가져온 다음 1주일 후에 동일한 크기의 다른 데이터 세트를 추가하고 해당하는 이전 데이터를 가져오는 경우에는 문제 없이 수행됩니다.
   * 연결하는 데이터 세트에 추가된 새 데이터에 우선 순위를 두므로 이 데이터의 지연 시간이 가장 짧습니다.
   * 모든 채우기(이전) 데이터는 더 느린 속도로 가져옵니다.

1. **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

워크플로우의 다음 단계는 [데이터 보기를 만드는](/help/data-views/create-dataview.md) 것입니다.
