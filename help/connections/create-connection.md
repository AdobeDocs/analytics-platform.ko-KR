---
title: 연결 만들기
description: 플랫폼 데이터 세트에 연결하는 방법이 Customer Journey Analytics에 설명되어 있습니다.
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '2629'
ht-degree: 95%

---

# 연결 만들기

연결 생성 및 편집 워크플로 환경은 모든 데이터 세트 및 연결 구성 설정을 보조 워크플로와 함께 화면 중앙으로 가져옵니다. 데이터 세트 유형, 크기, 스키마, 데이터 세트 ID, 배치 상태, 채우기 상태, 개인 ID 등과 같은 중요한 정보와 함께 상세한 데이터 세트 선택, 구성 및 검토 경험을 제공하여 잘못된 연결 구성의 위험을 줄입니다. 다음은 기능에 대한 개요입니다.

* 연결을 생성할 때 롤링 데이터 보존 기간을 활성화할 수 있습니다.
* 연결에서 데이터 세트를 추가하거나 제거할 수 있습니다. (데이터 세트를 제거하면 연결에서 데이터 세트가 제거되고 연결된 모든 데이터 보기 및 기본 Analysis Workspace 프로젝트에 영향을 미칩니다.)
* 각 데이터 세트에 대해 데이터 채우기를 활성화하고 요청할 수 있습니다.
* 예를 들어 데이터 세트를 편집하여 다른 채우기를 요청할 수 있습니다.
* 각 데이터 세트에 대한 기존 데이터를 가져올 수 있습니다.

>[!VIDEO](https://video.tv.adobe.com/v/343044/?quality=12&learn=on)

>[!IMPORTANT]
>
>다음을 보유해야 합니다. **선택** 패키지에 포함하면 연결에 데이터 세트를 무제한으로 추가할 수 있습니다. 다음 **Foundation** 패키지는 하나의 데이터 세트로 제한됩니다. 어떤 Customer Journey Analytics 패키지가 있는지 확실하지 않은 경우 관리자에게 문의하십시오&#x200B;.

## 연결 만들기 및 구성 {#create-connection}

1. Customer Journey Analytics에서 **[!UICONTROL 연결]** 탭을 클릭합니다.
1. **[!UICONTROL 새 연결 만들기]**&#x200B;를 클릭합니다.

   ![연결 설정](assets/create-conn1.png)

1. 연결 설정을 구성합니다.

   | 설정 | 설명 |
   | --- | --- |
   | **[!UICONTROL 연결 이름]** | 연결의 고유한 이름을 입력합니다. |
   | **[!UICONTROL 연결 설명]** | 이 연결의 목적에 대해 설명합니다. |
   | **[!UICONTROL 샌드박스]** | 연결을 만들 데이터 세트가 포함된 Experience Platform의 샌드박스를 선택합니다.<p>Adobe Experience Platform은 디지털 경험 애플리케이션을 개발하고 발전시키는 데 도움이 되는 단일 플랫폼 인스턴스를 별도의 가상 환경으로 분할하는 [샌드박스](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ko-KR)를 제공합니다. 샌드박스를 데이터 세트가 포함된 “데이터 사일로”로 간주할 수 있습니다. 샌드박스는 데이터 세트에 대한 액세스를 제어하는 데 사용됩니다.<p>샌드박스를 선택하면 왼쪽 레일에 해당 샌드박스에서 가져올 수 있는 모든 데이터 세트가 표시됩니다. |
   | **[!UICONTROL 롤링 데이터 기간 활성화]** | 이 확인란이 선택되어 있으면 Customer Journey Analytics 데이터 보존을 연결 수준에서 개월(1개월, 3개월, 6개월 등) 단위의 롤링 기간으로 정의할 수 있습니다.<p>데이터 보존은 이벤트 데이터 세트 타임스탬프를 기반으로 하며 이벤트 데이터 세트에만 적용됩니다. 적용 가능한 타임스탬프가 없기 때문에 프로필 또는 조회 데이터 세트에 대한 롤링 데이터 기간 설정이 없습니다. 그러나 연결에 프로필 또는 조회 데이터 세트(하나 이상의 이벤트 데이터 세트 제외)가 포함된 경우 해당 데이터는 동일한 기간 동안 유지됩니다.<p> 주요 이점은 적용 가능하고 유용한 데이터에 대해서만 저장하거나 보고하고 더 이상 유용하지 않은 오래된 데이터를 삭제한다는 것입니다. 계약 한도를 유지하고 초과 비용의 위험을 줄이는 데 도움이 됩니다.<p>기본값(선택 해제)을 그대로 두면 보존 기간이 Adobe Experience Platform 데이터 보존 설정으로 대체됩니다. Experience Platform에 25개월 분량의 데이터가 있는 경우 Customer Journey Analytics는 채우기를 통해 25개월 분량의 데이터를 받습니다. 플랫폼에서 이러한 개월 중 10개월을 삭제하면 Customer Journey Analytics는 나머지 15개월을 유지합니다. |
   | **[!UICONTROL 데이터 세트 추가]** (아래 참조) | 데이터 세트 목록에 데이터 세트가 표시되지 않으면 데이터 세트를 추가합니다. |
   | **[!UICONTROL 데이터 세트 이름]** | Customer Journey Analytics으로 가져올 데이터 세트를 한 개 이상 선택하고 **[!UICONTROL 추가]**&#x200B;를 클릭합니다.<p>(선택할 데이터 세트가 여러 개인 경우 데이터 세트 목록 위에 있는 데이터 세트 검색 막대를 사용하여 올바른 데이터 세트를 검색할 수 있습니다.) |
   | **[!UICONTROL 마지막으로 업데이트됨]** | 이벤트 데이터 세트의 경우에만 이 설정이 Experience Platform의 이벤트 기반 스키마에서 기본 타임스탬프 필드로 자동 설정됩니다. “N/A”는 이 데이터 세트에 데이터가 없음을 의미합니다. |
   | **[!UICONTROL 스키마]** | Adobe Experience Platform에서 데이터 세트를 만드는 데 사용한 [스키마](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=ko-KR)입니다. |
   | **[!UICONTROL 데이터 세트 유형]** | 이 연결에 추가한 각 데이터 세트에 대해 가져오는 데이터를 기반으로 데이터 세트 유형을 Customer Journey Analytics에서 자동으로 설정합니다. 이벤트 데이터, 프로필 데이터 및 조회 데이터의 3가지 데이터 세트 유형이 있습니다. 데이터 세트 유형에 대한 설명은 아래 표를 참조하십시오. |
   | **[!UICONTROL 개인 ID]** | 사용 가능한 ID의 드롭다운 목록에서 개인 ID를 선택합니다. 이러한 ID는 Experience Platform의 데이터 세트 스키마에 정의되어 있습니다. ID 맵을 개인 ID로 사용하는 방법에 대한 자세한 내용은 아래를 참조하십시오.<p>중요: 선택할 개인 ID가 없는 경우, 하나 이상의 개인 ID가 스키마에 정의되어 있지 않음을 의미합니다. [이 비디오](https://www.youtube.com/watch?v=G_ttmGl_LRU)를 보고 Experience Platform에서 ID를 정의하는 방법을 확인하십시오. |
   | **[!UICONTROL 키]** | 조회 데이터 세트(예: _id)에만 해당됩니다. |
   | **[!UICONTROL 일치하는 키]** | 조회 데이터 세트(예: _id)에만 해당됩니다. |
   | **[!UICONTROL 새 데이터 가져오기]** | 켜기 또는 끄기로 설정합니다. |
   | **[!UICONTROL 채우기 데이터]** | 이벤트 타임스탬프를 기반으로 데이터 세트의 데이터 채우기를 요청할 수 있습니다. 예를 들어 지난 7일 동안의 데이터를 채우도록 요청하고, 올바른 개인 ID를 구성하고, 올바른 구성을 위해 연결을 테스트할 수 있습니다. 모두 정상적인 경우 나머지 모든 데이터를 간편하게 다시 채울 수 있습니다.<p>또한 데이터 세트별로 새 데이터 가져오기를 활성화할 수 있습니다. 예를 들어 조회 데이터에 대해서만 새 데이터 가져오기를 활성화할 수 있습니다. |
   | **[!UICONTROL 채우기 상태]** | 데이터 채우기가 처리 중인지 여부를 나타냅니다. |

   {style="table-layout:auto"}

## 데이터 세트 추가 및 구성 {#add-dataset}

새 워크플로를 사용하면 연결을 만들 때 Experience Platform 데이터 세트를 추가할 수 있습니다.

1. 연결 설정 대화 상자에서 **[!UICONTROL 데이터 세트 추가]**&#x200B;를 클릭합니다.

2. 하나 이상의 데이터 세트를 선택하고 **[!UICONTROL 다음]**&#x200B;을 클릭합니다. 하나 이상의 이벤트 데이터 세트가 연결의 일부가 되어야 합니다.

3. 이제 데이터 세트를 하나씩 구성합니다.

   ![데이터 세트 구성](assets/add-dataset.png)

   | 설정 | 설명 |
   | --- | --- |
   | **[!UICONTROL 개인 ID]** | 사용 가능한 ID의 드롭다운 목록에서 개인 ID를 선택합니다. 이러한 ID는 Experience Platform의 데이터 세트 스키마에 정의되어 있습니다. ID 맵을 개인 ID로 사용하는 방법에 대한 자세한 내용은 아래를 참조하십시오.<p>선택할 개인 ID가 없는 경우, 하나 이상의 개인 ID가 스키마에 정의되어 있지 않음을 의미합니다. 이 비디오를 보고 Experience Platform에서 ID를 정의하는 방법을 확인하십시오. |
   | **[!UICONTROL 타임스탬프]** | 이벤트 데이터 세트의 경우에만 이 설정이 Experience Platform의 이벤트 기반 스키마에서 기본 타임스탬프 필드로 자동 설정됩니다. |
   | **[!UICONTROL 데이터 소스 유형]** | 데이터 소스 유형을 선택합니다. <br/>데이터 소스 유형에는 다음이 포함됩니다. <ul><li>[!UICONTROL 웹 데이터]</li><li>[!UICONTROL 모바일 앱 데이터]</li><li>[!UICONTROL POS 데이터]</li><li>[!UICONTROL CRM 데이터]</li><li>[!UICONTROL 설문 조사 데이터]</li><li>[!UICONTROL 콜 센터 데이터]</li><li>[!UICONTROL 제품 데이터]</li><li> [!UICONTROL 계정 데이터]</li><li> [!UICONTROL 트랜잭션 데이터]</li><li>[!UICONTROL 고객 피드백 데이터]</li><li> [!UICONTROL 기타]</li></ul>이 필드를 사용하여 사용 중인 데이터 소스 유형을 조사합니다. |
   | **[!UICONTROL 새 데이터 가져오기]** | 이 연결의 데이터 세트에 추가되는 모든 새 데이터 배치가 자동으로 작업 영역으로 연결되도록 지속적인 연결을 설정하려면 이 옵션을 선택합니다. [!UICONTROL 켜기] 또는 [!UICONTROL 끄기]로 설정할 수 있습니다. |
   | **[!UICONTROL 데이터 세트 채우기]** | 내역 데이터를 채우려면 **[!UICONTROL 채우기 요청]**&#x200B;을 선택합니다.<ul><li>각 데이터 세트를 개별적으로 채울 수 있습니다.</li><li>연결하는 데이터 세트에 추가된 새 데이터에 우선 순위를 두므로 이 새 데이터의 지연 시간이 가장 짧습니다.</li><li>모든 채우기 (이전) 데이터는 더 느린 속도로 가져옵니다. 지연은 보유하고 있는 내역 데이터의 양에 따라 달라집니다.</li><li>Analytics 소스 커넥터는 프로덕션 샌드박스에 대해 최대 13개월의 데이터(크기에 상관없이)를 가져옵니다. 비프로덕션 샌드박스의 채우기는 3개월로 제한됩니다.</li></ul> |
   | **[!UICONTROL 채우기 상태]** | 가능한 상태 표시기는 다음과 같습니다.<ul><li>성공</li><li>X 채우기 처리</li><li>꺼짐</li></ul> |
   | **[!UICONTROL 데이터 세트 ID]** | 이 ID는 자동으로 생성됩니다. |
   | **[!UICONTROL 설명]** | 이 데이터 세트가 생성될 때 제공된 설명입니다. |
   | **[!UICONTROL 데이터 세트 크기]** | 데이터 세트 크기입니다. |
   | **[!UICONTROL 스키마]** | Adobe Experience Platform에서 데이터 세트를 만드는 데 사용한 스키마입니다. |
   | **[!UICONTROL 데이터 세트]** | 데이터 세트의 이름입니다. |
   | **[!UICONTROL 미리보기]**: `<dataset name>` | 날짜, 내 ID 및 식별자 열을 사용하여 데이터 세트를 미리 봅니다. |
   | **[!UICONTROL 제거]** | 전체 연결을 삭제하지 않고 데이터 세트를 삭제하거나 제거하고 개인 ID를 변경할 수 있습니다. 삭제 또는 제거하게 되면 데이터 수집과 관련된 비용과 전체 연결 및 관련 데이터 보기를 다시 만드는 번거로운 프로세스를 줄일 수 있습니다. |

   {style="table-layout:auto"}

## 연결 미리보기 {#preview}

생성한 연결을 미리 보려면 연결 설정 대화 상자에서 **[!UICONTROL 연결 미리보기]**&#x200B;를 클릭합니다.

![연결 미리보기](assets/create-conn4.png)

이 미리보기에는 연결 구성을 나열하는 열이 일부 있습니다. 표시되는 열 유형은 개별 데이터 세트에 따라 다릅니다.

## 데이터 세트 유형 {#dataset-types}

이 연결에 추가한 각 데이터 세트에 대해 가져오는 데이터를 기반으로 데이터 세트 유형을 [!UICONTROL Customer Journey Analytics]에서 자동으로 설정합니다.

>[!IMPORTANT]
>
>연결의 일부로 하나 이상의 이벤트 데이터 세트를 추가해야 합니다.

[!UICONTROL 이벤트] 데이터, [!UICONTROL 프로필] 데이터 및 [!UICONTROL 조회] 데이터의 세 가지 데이터 세트 유형이 있습니다.

| 데이터 세트 유형 | 설명 | 타임스탬프 | 스키마 | 개인 ID |
|---|---|---|---|---|
| **[!UICONTROL 이벤트]** | 시간으로 이벤트를 나타내는 데이터(예: 웹 방문, 상호 작용, 거래, POS 데이터, 설문 조사 데이터, 광고 노출 데이터 등). 예를 들어 이 데이터는 고객 ID 또는 쿠키 ID와 타임스탬프가 있는 일반적인 클릭스트림 데이터일 수 있습니다. 이벤트 데이터를 사용하면 개인 ID로 사용할 ID를 유연하게 선택할 수 있습니다. | [!UICONTROL Experience Platform]의 이벤트 기반 스키마에서 기본 타임스탬프 필드로 자동 설정됩니다. | 시간 일련 동작 있는 XDM 클래스를 기반으로 하는 모든 빌트인 또는 스키마 또는 사용자 정의 스키마. 예를 들면 “XDM 경험 이벤트” 또는 “XDM 결정 이벤트”가 해당됩니다. | 포함할 개인 ID를 선택할 수 있습니다. Experience Platform에 정의된 각 데이터 세트 스키마에는 1개 이상의 ID가 ID 네임스페이스로 정의되고 연결된 고유한 ID 세트가 있을 수 있습니다. 이들 ID 중 원하는 ID를 개인 ID로 사용할 수 있습니다. 예를 들면 쿠키 ID, 결합된 ID, 사용자 ID, 추적 코드 등이 있습니다. |
| **[!UICONTROL 조회]** | 이제 프로필, 조회 및 이벤트 데이터 세트(후자의 경우 항상 지원됨) 등 모든 데이터 세트 유형 내의 필드 조회로 데이터세트를 추가할 수 있습니다. 이 추가 기능은 B2B CDP 등 복잡한 데이터 모델을 지원하는 CJA의 기능을 확장합니다. 이 데이터는 이벤트, 프로필 또는 조회 데이터에 있는 값이나 키를 찾는 데 사용됩니다. 최대 2개 조회 수준을 추가할 수 있습니다. (참고: [파생 필드](/help/data-views/derived-fields/derived-fields.md)는 연결 내 조회에 일치하는 키로 사용할 수 없습니다.) 예를 들어 이벤트 데이터의 숫자 ID를 제품 이름에 매핑하는 조회 데이터를 업로드할 수 있습니다. 예제는 [B2B 사용 사례](/help/use-cases/b2b/b2b.md)를 참고하십시오. | 해당 사항 없음 | XDM 개별 프로필 클래스를 제외하고, “기록” 동작이 있는 XDM 클래스를 기반으로 한 모든 빌트인 스키마 또는 사용자 정의 스키마. | 해당 사항 없음 |
| **[!UICONTROL 프로필]** | [!UICONTROL 이벤트] 데이터에서 개인, 사용자 또는 고객에 적용되는 데이터. 예를 들어 고객에 대한 CRM 데이터를 업로드할 수 있습니다. | 해당 사항 없음 | XDM 개인 프로필 클래스를 기반으로 하는 모든 빌트인 또는 사용자 정의 스키마. | 포함할 개인 ID를 선택할 수 있습니다. [!DNL Experience Platform]에 정의된 각 데이터 세트에는 개인 ID(예: 쿠키 ID, 결합된 ID, 사용자 ID, 추적 코드 등)가 하나 이상 정의된 고유한 ID 세트가 있습니다.<br>![개인 ID ](assets/person-id.png)**참고**: ID가 다른 데이터 세트가 포함된 연결을 만들면 이러한 내용이 보고에 반영됩니다. 데이터 세트를 실제로 병합하려면 동일한 개인 ID를 사용해야 합니다. |

{style="table-layout:auto"}

## 숫자 필드를 조회 키 및 조회 값으로 사용 {#numeric}

이 조회 기능은 비용 또는 이윤과 같은 숫자 필드를 문자열 기반 키 필드에 추가할 때 유용합니다. 숫자 값을 키 또는 값으로 조회에 포함할 수 있습니다. 조회 스키마에서는 제품 이름, COGS, 캠페인 마케팅 비용 또는 이윤과 같은 숫자 값을 연결할 수 있습니다. 다음은 Adobe Experience Platform의 조회 스키마 예제입니다.

![조회 스키마](assets/schema.png)

이제 이러한 값을 Customer Journey Analytics 보고에 지표 또는 차원으로 가져오도록 지원합니다. 연결을 설정하고 조회 데이터 세트를 가져올 때 데이터 세트를 편집하여 [!UICONTROL 키] 및 [!UICONTROL 일치하는 키]를 선택할 수 있습니다.

![데이터 세트 편집](assets/lookup-dataset.png)

이 연결을 기준으로 데이터 보기를 설정할 때 숫자 값을 데이터 보기에 구성 요소로 추가합니다. 이 데이터 보기를 기반으로 하는 프로젝트는 이러한 숫자 값을 보고할 수 있습니다.

## ID 맵을 개인 ID로 사용 {#id-map}

Customer Journey Analytics에서는 개인 ID로 ID 맵을 사용하는 기능을 지원합니다. ID 맵은 사용자의 키 -> 값 쌍 업로드를 허용하는 맵 데이터 구조입니다. 키는 ID 네임스페이스이며, 값은 ID 값을 가지는 구조입니다. ID 맵은 업로드된 각 행/이벤트에 있으며 해당 행에 맞게 작성됩니다.

ID 맵은 [ExperienceEvent XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ko-KR) 클래스 기반의 스키마를 사용하는 데이터 세트에 사용 가능합니다. Customer Journey Analytics 연결에 이러한 데이터 세트를 포함하도록 선택하는 경우, 필드를 기본 ID나 ID 맵으로 선택하는 옵션이 제공됩니다.

![](assets/idmap1.png)

ID 맵을 선택하면 두 가지 추가 구성 옵션이 제공됩니다.

| 옵션 | 설명 |
|---|---|
| **[!UICONTROL 기본 ID 네임스페이스 사용]** | 이 옵션을 통해 Customer Journey Analytics는 ID 맵에서 행마다 primary=true 속성으로 표시된 ID를 찾아 해당 행의 개인 ID로 사용합니다. 이 ID는 Experience Platform에서 파티셔닝에 사용하는 기본 키입니다. 또한 이 ID는 Customer Journey Analytics 개인 ID로 사용하기에 가장 적합한 후보입니다(Customer Journey Analytics 연결에 데이터 세트가 구성되는 방법에 따라 다름). |
| **[!UICONTROL 네임스페이스]** | (이 옵션은 기본 ID 네임스페이스를 사용하지 않는 경우에만 사용할 수 있습니다.) ID 네임스페이스는 [Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ko-KR)의 구성 요소이며 ID가 연관되는 컨텍스트의 지표 역할을 합니다. 네임스페이스를 지정하면 Customer Journey Analytics에서 각 행의 ID 맵을 검색하여 이 네임스페이스 키를 찾고 해당 네임스페이스 아래의 ID를 해당 행의 개인 ID로 사용합니다. Customer Journey Analytics에서는 사용 중인 네임스페이스가 무엇인지 확인하기 위해서 모든 행의 전체 데이터 세트를 스캔할 수 없으므로 가능한 모든 네임스페이스가 드롭다운 목록에 표시됩니다. 데이터에 지정된 네임스페이스를 알아야 하지만 해당 네임스페이스는 자동으로 검색되지 않습니다. |

{style="table-layout:auto"}

### ID 맵의 극단적 사례 {#id-map-edge}

이 표에서는 극단적 사례가 있을 때 이 사례들이 처리되는 방식을 두 가지 구성 옵션으로 보여 줍니다.

| 옵션 | ID가 ID 맵에 없음 | 여러 ID가 기본 ID로 표시되지 않음 | 여러 ID가 기본 ID로 표시됨 | 단일 ID가 기본 ID로 표시되거나 표시되지 않음 | 기본 ID로 표시된 ID의 네임스페이스가 잘못됨 |
|---|---|---|---|---|---|
| **[!UICONTROL 기본 ID 네임스페이스 사용]이 선택됨** | 행이 Customer Journey Analytics에서 삭제됩니다. | 기본 ID가 지정되지 않아서 행이 Customer Journey Analytics에서 삭제됩니다. | 모든 네임스페이스에서 기본 ID로 표시된 모든 ID가 목록으로 추출됩니다. 그런 다음 알파벳순으로 정렬됩니다. 이렇게 정렬되면 첫 번째 ID가 있는 첫 번째 네임스페이스가 개인 ID로 사용됩니다. | 단일 ID가 개인 ID로 사용됩니다. | 네임스페이스가 유효하지 않을 수 있지만(Adobe Experience Platform에 없음) Customer Journey Analytics는 해당 네임스페이스 아래의 기본 ID를 개인 ID로 사용합니다. |
| **[!UICONTROL 특정 ID 맵 네임스페이스]가 선택됨** | 행이 Customer Journey Analytics에서 삭제됩니다. | 선택한 네임스페이스 아래의 모든 ID가 목록으로 추출되며 첫 번째 ID를 개인 ID로 사용합니다. | 선택한 네임스페이스 아래의 모든 ID가 목록으로 추출되며 첫 번째 ID를 개인 ID로 사용합니다. | 선택한 네임스페이스 아래의 모든 ID가 목록으로 추출되며 첫 번째 ID를 개인 ID로 사용합니다. | 선택한 네임스페이스 아래의 모든 ID가 목록으로 추출되며 첫 번째 ID를 개인 ID로 사용합니다. (연결 생성 시 올바른 네임스페이스만 선택할 수 있으므로 잘못된 네임스페이스/ID를 개인 ID로 사용할 수 없습니다.) |

{style="table-layout:auto"}

## 일일 평균 이벤트 수 계산 {#average-number}

이 계산은 연결의 모든 데이터 세트에 대해 수행됩니다.

1. [Adobe Experience Platform 쿼리 서비스](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ko-KR)로 이동하여 쿼리를 만듭니다.

   이 쿼리의 형태는 다음과 같습니다.

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   이 예에서 “analytics_demo_data”는 데이터 세트의 이름입니다.

2. Adobe Experience Platform에 있는 모든 데이터 세트를 표시하려면 `Show Tables` 쿼리를 수행하십시오.
