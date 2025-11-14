---
title: 대상자 생성 및 게시
description: Customer Journey Analytics에서 대상자를 게시하는 방법 알아보기
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
feature: Audiences
role: User
source-git-commit: 4717a85b9a3c7dc2cbdd8c625ebb5862cbfccd58
workflow-type: tm+mt
source-wordcount: '2391'
ht-degree: 99%

---

# 대상자 생성 및 게시 {#create-and-publish-audiences}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_refreshfrequency"
>title="새로 고침 빈도"
>abstract="대상자의 멤버십을 재평가할 빈도를 확인합니다.<br/>일회성 대상자는 한 번만 평가됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_audiences_audiencelimit"
>title="대상자 제한"
>abstract="새로 고치는 대상자는 새로 고침 빈도에 따라 제한됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_refreshlookbackwindow"
>title="전환 확인 기간 새로 고침"
>abstract="대상자 평가의 시점인 오늘부터 전환 확인 일수를 정의하십시오."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_audiencesizelimit"
>title="대상자 크기 제한"
>abstract="대상자는 멤버 수 2천만 명을 초과할 수 없습니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_audiences_namespacesincluded"
>title="네임스페이스 포함됨"
>abstract="이 대상자의 ID는 아래 네임스페이스로 구성됩니다."

<!-- markdownlint-enable MD034 -->




이 항목에서는 고객 타기팅 및 맞춤화를 위해 Customer Journey Analytics에서 식별된 대상자를 Adobe Experience Platform의 [실시간 고객 프로필](https://experienceleague.adobe.com/ko/docs/experience-platform/profile/home)을 만들어 게시하는 방법에 대해 설명합니다.

이 [개요](/help/components/audiences/audiences-overview.md)를 읽고 Customer Journey Analytics 대상자의 개념을 숙지하십시오.

## 대상자 만들기 및 게시 {#create}

1. 대상자를 만들고 게시하려면 다음 중 하나를 수행합니다.

   | 만들기 방법 | 세부 사항 |
   | --- | --- |
   | **[!UICONTROL 게시된 대상자]** 인터페이스 내에서 | 기본 Customer Journey Analytics 메뉴에서 **[!UICONTROL 구성 요소]** > **[!UICONTROL 게시된 대상]**&#x200B;을 선택합니다. 대상자 인터페이스가 표시됩니다. **[!UICONTROL 대상자 만들기]**&#x200B;를 선택하면 [!UICONTROL 대상자 빌더]가 열립니다. |
   | Analysis Workspace의 시각화에서 | Analysis Workspace의 많은 시각화 기능을 사용하면 컨텍스트 메뉴를 사용하여 대상자를 만들 수 있습니다. 예를 들어 [자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)의 항목 또는 [여정 캔버스](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)의 노드 컨텍스트 메뉴에서 **[!UICONTROL 대상자 만들기]**&#x200B;를 선택합니다.<p>이 방법을 사용하면 선택한 차원 또는 차원 항목으로 대상자 빌더의 세그먼트가 미리 채워집니다.</p><p>다음 시각화를 사용하면 마우스 오른쪽 클릭 메뉴를 사용하여 대상자를 만들 수 있습니다.</p><ul><li>[코호트 테이블](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)</li><li>[폴아웃](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)</li><li>[플로우](/help/analysis-workspace/visualizations/c-flow/flow.md)</li><li>[자유 형식 테이블](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)</li><li>[여정 캔버스](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)</li><li>[맵&#x200B;](/help/analysis-workspace/visualizations/map.md#create-an-audience-from-the-map-visualization)<br/>**참고:** 이 시각화는 릴리스의 제한된 테스트 단계에 있으며 사용자 환경에서 아직 사용하지 못할 수 있습니다.</li><li>[벤](/help/analysis-workspace/visualizations/venn.md)</li></ul><p>**참고:** 계산된 지표는 대상자에 포함될 수 없습니다. 계산된 지표가 포함된 대상자를 만들려고 하면 계산된 지표가 대상자 정의에 포함되지 않습니다.</p> |
   | 세그먼트 생성/편집 UI에서 | **[!UICONTROL 이 세그먼트에서 대상자 만들기]** 확인란을 선택합니다. 이 방법을 사용하면 세그먼트가 미리 채워집니다. 자세한 내용은 [세그먼트 만들기](/help/components/segments/seg-create.md)를 참조하십시오. |

   {style="table-layout:auto"}

1. [대상자 빌더](#audience-builder)를 사용하여 대상자를 빌드합니다.

1. [&#x200B; 날짜 미리보기](#data-preview) 패널을 사용하여 데이터를 해석합니다.

1. 이 대상자의 ID 샘플을 보려면 **[!UICONTROL [!UICONTROL 샘플 ID 보기]]**&#x200B;를 선택합니다. **[!UICONTROL 샘플 ID]** 대화 상자에서 샘플 ID를 검색하기 위해 ![검색](/help/assets/icons/Search.svg) [!UICONTROL *샘플 ID 검색*]&#x200B;을 사용할 수 있습니다.

1. 대상자 구성을 다시 한 번 확인하고 **[!UICONTROL 게시]**&#x200B;를 선택합니다.
대상자가 게시되었다는 확인 메시지를 받게 됩니다. 이 대상자가 Experience Platform에 나타나는 데는 불과 1~2분밖에 소요되지 않습니다.

1. 동일한 메시지 내에서 **[!UICONTROL AEP의 대상자 보기]**&#x200B;를 선택하면 Adobe Experience Platform의 [Segment UI](https://experienceleague.adobe.com/ko/docs/experience-platform/segmentation/ui/overview)로 이동합니다. 자세한 내용은 아래를 참조하십시오.

## 대상자 빌더

이러한 설정을 구성하여 대상자를 정의하거나 업데이트합니다.

![다음 섹션에 설명된 설정을 보여 주는 대상자 만들기의 스크린샷.](assets/create-audience.png)

| 설정 | 설명 |
| --- | --- |
| ![데이터](/help/assets/icons/Data.svg) | 대상자 생성에 사용할 데이터 보기를 선택합니다. |
| **[!UICONTROL 이름]** | 대상자의 이름. 예: `Really Interested in Potential Car Buyers` |
| **[!UICONTROL 태그]** | 조직용으로 대상자에 할당하고자 하는 모든 태그. 하나 이상의 기존 태그를 선택하거나 새 태그를 입력할 수 있습니다. |
| **[!UICONTROL 설명]** | 해당 대상자를 다른 대상자와 구별하기 위해 대상자에 대한 설명. 예: `Build an audience of really interested potential car buyers` |
| **[!UICONTROL 새로 고침 빈도]** | 대상자를 새로 고침하는 빈도입니다.<p/>다음 중에 선택할 수 있습니다. <ul><li>**[!UICONTROL 일회성]** 대상자: 새로 고침이 필요 없는 대상자(기본값). 이 옵션은 예를 들어 특정 일회성 캠페인에 유용합니다.<br/>**[!UICONTROL 일회성 날짜 범위]**&#x200B;를 지정해야 합니다. 날짜 범위를 입력하려면 ![캘린더](/help/assets/icons/Calendar.svg)를 사용합니다.</li><li>새로 고침 대상자. 다음 옵션 중에서 선택할 수 있습니다.<ul><li>**[!UICONTROL 4시간마다]**: 4시간마다 새로 고침하는 대상자.</li><li>**[!UICONTROL 일별]**: 매일 새로 고침하는 대상자</li><li>**[!UICONTROL 주별]**: 매주 새로 고침하는 대상자.</li><li>**[!UICONTROL 월별]**: 매달 새로 고침하는 대상자</li></ul></li>새로 고침 대상자의 경우 다음을 지정해야 합니다.<ul><li>**[!UICONTROL 전환 확인 기간 새로 고침]**. 대상자 평가의 시점인 오늘부터 전환 확인 일수를 정의합니다. 옵션에서 선택하거나 사용자 정의 시간을 정의할 수 있습니다. 최대값은 90일입니다.</li><li>**[!UICONTROL 만료 날짜]**: 대상자가 새로 고침을 멈추는 시점을 정의합니다. ![캘린더](/help/assets/icons/Calendar.svg)를 사용해 날짜를 선택할 수 있습니다. 기본 설정은 생성일로부터 1년이 되는 날입니다. 만료되는 대상자는 만료 예정인 예약된 보고서와 유사하게 처리됩니다. 관리자는 대상자가 만료되기 한 달 전에 이메일을 받습니다.</li></ul> Customer Journey Analytics 권한에 따라 최대 75~150회로 대상자 새로 고침이 제한됩니다.</li></ul> |
| **[!UICONTROL 필터]** | 필터는 대상자의 주요 입력입니다. 왼쪽 ![세분화](/help/assets/icons/Segmentation.svg) **[!UICONTROL 세그먼트]** 패널에서 세그먼트 영역으로 하나 이상의 세그먼트를 끌어다 놓습니다. 세그먼트를 검색하기 위해 ![검색](/help/assets/icons/Search.svg) [!UICONTROL *세그먼트 검색*]&#x200B;을 사용할 수 있습니다. 최대 20개의 세그먼트를 추가할 수 있습니다. 세그먼트는 **[!UICONTROL And]** 또는 **[!UICONTROL Or]** 연산자와 결합할 수 있습니다.<p>Analysis Workspace(예: 자유 형식 테이블 또는 여정 캔버스)의 시각화에서 대상자를 만들 때 패널이나 열에 적용된 세그먼트는 그대로 유지됩니다. 자동으로 적용된 모든 세그먼트를 제거할 수 있습니다.</p> |
| **[!UICONTROL 데이터 미리보기]** | 선택된 날짜 범위에 대해 [데이터 미리보기](#data-preview)를 표시하거나 숨기려면 ![정보](/help/assets/icons/Info.svg)를 선택합니다. |

## 데이터 미리보기

데이터 미리보기 패널은 다음 정보를 제공합니다.

| 요소 | 설명 |
| --- | --- |
| **[!UICONTROL 총 인원]** | 이 대상자의 총 인원수에 대한 요약 숫자입니다. 최대 크기는 2천만 명입니다. 대상자가 2천만 명을 초과하는 경우 대상자의 크기를 줄여야 게시할 수 있습니다. |
| **[!UICONTROL 대상자 크기 제한]** | 대상자가 2천만 명 한도에서 얼마나 멀리 떨어져 있는지 보여 주는 시각화. |
| **[!UICONTROL 예상 대상자 반환]** | 이 값을 사용하여 사이트, 모바일 앱 또는 다른 채널로 돌아오는 이 대상자의 사람들을 다시 타기팅할 수 있습니다.<p>돌아올 수 있는 예상 고객 수에 대한 시간대(**[!UICONTROL 다음 7일]**, **[!UICONTROL 다음 2주]** 또는 **[!UICONTROL 다음 달]**)를 선택할 수 있습니다. |
| **[!UICONTROL 예상 반환]** | 이 숫자는 선택한 시간대 동안 돌아오는 예상 고객 수를 알려 줍니다. 이 숫자를 예측하기 위해 이 대상자의 과거 이탈률을 사용합니다. |
| **[!UICONTROL 지표 미리보기]** | 특정 지표를 선택하면 해당 지표의 데이터가 정의한 대상자를 기반으로 어떻게 이루어지는지 확인할 수 있습니다. 각 미리보기 지표는 대상자를 기준으로 지표의 합계를 표시합니다. 데이터 보기에서 정의된 전체 지표 중 대상자 기반 지표의 비율. 예를 들어 381명(선택한 지표)은 데이터 보기에서 사용할 수 있는 전체 인원의 5%에 해당하는 대상자 정의의 결과입니다. 데이터 보기에서 사용할 수 있는 지표를 선택할 수 있습니다. |
| **[!UICONTROL 네임스페이스 포함됨]** | 대상자의 인원과 연결된 특정 네임스페이스입니다. 예를 들어 ECID, CRM ID, 이메일 주소 등이 있습니다. |
| **[!UICONTROL 샌드박스]** | 이 대상자가 있는 [Experience Platform 샌드박스](https://experienceleague.adobe.com/ko/docs/experience-platform/sandbox/home)입니다. 이 대상자를 Platform에 게시할 때 이 샌드박스의 범위 내에서만 작업할 수 있습니다. |

{style="table-layout:auto"}

## 대상자가 만들고 게시한 후 진행되는 상황? {#after-audience-created}

Customer Journey Analytics에서 대상자를 생성하고 게시한 후에는 해당 대상자는 Experience Platform에서 사용할 수 있으며 [대상자 포털](https://experienceleague.adobe.com/ko/docs/experience-platform/segmentation/ui/audience-portal)에서 확인할 수 있습니다. Experience Platform에서 제공되는 대상자는 Adobe Journey Optimizer와 같은 다른 Experience Platform 애플리케이션에서 사용할 수 있습니다.

Adobe Experience Platform 스트리밍 세그먼트는 조직이 스트리밍 세그먼테이션에 대해 설정된 경우에만 생성됩니다.

Customer Journey Analytics에서 Experience Platform으로 게시된 대상자로 작업할 때 다음 사항을 고려하십시오.

* Experience Platform의 대상자는 Customer Journey Analytics 대상자와 동일한 이름과 설명을 공유합니다. 이 이름에는 Customer Journey Analytics 대상자 ID가 추가되어 대상자의 고유성을 보장합니다.
* Customer Journey Analytics에서 대상자의 이름이나 설명을 변경하면 Experience Platform에 반영됩니다.
* Customer Journey Analytics에서 대상자가 삭제된 경우, 해당 대상자의 프로필 멤버십이 만료될 때까지 Experience Platform에서 계속 이용할 수 있습니다. 프로필 멤버십은 일회성 대상자의 경우 420일 후에 만료되고, 반복적 대상자의 경우 16일 후에 만료됩니다.

## 지연 고려 사항 {#latency}

대상자를 게시하기 전, 도중 및 이후에 여러 지점에서 지연이 발생할 수 있습니다. 가능한 지연에 대한 개요는 다음과 같습니다.

![이 섹션에 설명된 대상자 게시의 지연.](assets/latency-diagram.svg)

|  | 지연 지점 | 지연 기간 |
| --- | --- | --- |
| 표시 안 됨 | Adobe Analytics와 Analytics 소스 커넥터 (A4T) | 최대 30분 |
| 1 | 데이터 레이크로 데이터 수집 (Analytics 소스 커넥터 또는 기타 소스에서) | 최대 90분 |
| 2 | Experience Platform 데이터 레이크에서 Customer Journey Analytics로 데이터 수집 | 최대 90분 |
| 3 | 스트리밍 세그먼트의 자동 생성을 포함하여 실시간 고객 프로필에 대상자를 게시하고 세그먼트가 데이터를 수신할 수 있도록 합니다. | 몇 초 |
| 4 | 대상자에 대한 새로 고침 빈도 | <ul><li>일회성 새로 고침 (지연 시간 5분 미만)</li><li>4시간마다, 매일, 매주, 매월 새로 고침(지연 시간은 새로 고침 빈도와 밀접한 관련이 있음) |
| 5 | Adobe Experience Platform에서 대상 생성: 새 세그먼트 활성화 | 1~2시간 |

{style="table-layout:auto"}

## Experience Platform에서 Customer Journey Analytics 대상자 사용 {#audiences-aep}

Customer Journey Analytics은 게시된 대상자에서 모든 네임스페이스와 ID 조합을 가져와 Real-Time Customer Data Platform으로 스트리밍합니다. Customer Journey Analytics는 연결이 구성될 때 [!UICONTROL 개인 ID]로 선택된 항목에 따라 기본 ID가 설정된 Experience Platform으로 대상자를 보냅니다.

그런 다음 Real-Time Customer Data Platform은 각 네임스페이스/ID 조합을 검사하고 해당 조합이 속할 수 있는 프로필을 찾습니다. 프로필은 기본적으로 연결된 네임스페이스, ID 및 디바이스의 클러스터입니다. 프로필을 찾으면 네임스페이스와 ID를 이 프로필의 다른 ID에 세그먼트 멤버십 속성으로 추가합니다. 예를 들어 <user@adobe.com>은 모든 디바이스와 채널을 타깃으로 지정할 수 있습니다. 프로필을 찾을 수 없으면 새 프로필이 만들어집니다.

Platform에서 Customer Journey Analytics 대상자를 보는 방법:

1. 왼쪽 패널에서 **[!UICONTROL 고객]**&#x200B;을 확장한 다음 **[!UICONTROL 대상자]**&#x200B;를 선택합니다. <!-- is there a folder called "Customer Journey Analytics? -->

1. **[!UICONTROL 브라우저]** 탭을 선택합니다.

1. Customer Journey Analytics에서 게시한 대상자를 찾으려면 다음 중 하나를 수행합니다.

   ![왼쪽 패널의 대상자 옵션](assets/aep-audiences.png)

   * **[!UICONTROL 원본]** 열을 기준으로 테이블을 정렬하려면 [!UICONTROL **Customer Journey Analytics**]&#x200B;을 원본으로 표시하는 대상자를 확인합니다.

   * **[!UICONTROL 원본]**&#x200B;에 대해 ![필터](/help/assets/icons/Filter.svg)를 필터링하고 **[!UICONTROL Customer Journey Analytics]**&#x200B;를 선택합니다.

   * ![검색](/help/assets/icons/Search.svg) 검색 필드를 사용합니다.

Platform에서 대상자를 사용하는 방법에 대한 자세한 내용은 Experience Platform 설명서의 [세그먼트 빌더 UI 안내서](https://experienceleague.adobe.com/ko/docs/experience-platform/segmentation/ui/segment-builder)의 [대상자](https://experienceleague.adobe.com/ko/docs/experience-platform/segmentation/ui/segment-builder) 섹션을 참조하십시오.

### 대상자 수의 불일치 이해

Customer Journey Analytics과 Real-Time Customer Data Platform 간에는 대상자 수에 불일치가 발생할 수 있습니다.

<!--
![Infographic on audience differences between Customer Journey Analytics and Real-Time CDP.](/help/components/audiences/assets/infographic-cja-rtcdp.png)
-->

#### 추정 카운트와 확정적 카운트

두 앱의 대상자 멤버십 수를 계산하는 방법은 아래에 설명된 대로 서로 다릅니다.

* **Customer Journey Analytics**: Customer Journey Analytics의 **[!UICONTROL 총 인원]** 지표는 추정값입니다. 즉, 해당 수치는 대상자의 규칙에 따른 추정치이며 새로 고침 간격에 따라 변경될 수 있습니다.
* **Real-Time Customer Data Platform**: Real-Time Customer Data Platform의 카운트는 일일 평가 작업을 기반으로 하여 확정적이며, 대상자가 대상자 포털에 게시를 완료하는 시점에 고정됩니다.

#### 게시 간격 및 속도

대상자는 초당 1,500개의 레코드(RPS)의 속도로 Real-Time Customer Data Platform에 게시합니다. 예를 들어 2,000만 명의 멤버를 보유한 대상자가 완전히 게시하는 데는 약 3.7시간이 소요됩니다(2,000만/1,500RPS/시간당 3,600초). 이 기간 동안 두 앱 간의 대상자 멤버십에는 차이가 있을 가능성이 높습니다.

#### 프로필 단편화

Customer Journey Analytics에서 가져온 프로필이 Real-Time Customer Data Platform에 이미 존재하는 경우, 해당 프로필은 새 프로필로 계산되지 않습니다. 이로 인해 Real-Time Customer Data Platform의 프로필 수가 예상보다 낮아질 수 있습니다.

#### 배치 대상자와 스트리밍 대상자

Customer Journey Analytics 대상자는 일일 배치 평가 작업에 포함되지 않으며, 다음 게시 주기까지 고정된 상태로 유지됩니다. 이와 대조적으로 Real-Time Customer Data Platform의 다른 배치 대상자는 24시간마다 다시 평가됩니다.

### 기억해야 할 주요 사항

* **Customer Journey Analytics의 추정 카운트**: Customer Journey Analytics의 **[!UICONTROL 총 인원]** 수는 추정치이며 스트리밍 데이터와 ID 동작에 따라 달라질 수 있습니다.
* **Real-Time Customer Data Platform의 확정적 카운트**: Real-Time Customer Data Platform의 수는 고정되어 있으며 다음 게시 간격까지 변경되지 않습니다.
* **프로필 단편화**: Customer Journey Analytics에서 프로필을 가져올 때 Real-Time Customer Data Platform의 기존 프로필은 새 프로필 수에 반영되지 않을 수 있습니다.

이러한 측면을 명확하게 구분함으로써 Customer Journey Analytics 및 Real-Time Customer Data Platform 전반에서 대상자 데이터를 더 잘 이해하고 관리할 수 있습니다.--->

## FAQ {#faq}

대상자 게시에 대해 자주 묻는 질문.

+++**사용자가 더 이상 Customer Journey Analytics에서 대상자의 멤버가 아닌 경우 어떻게 됩니까?**

이 경우 종료 이벤트가 Customer Journey Analytics에서 Experience Platform으로 전송됩니다.

+++

+++**Customer Journey Analytics에서 대상자를 삭제하면 어떻게 됩니까?**

Customer Journey Analytics 대상자가 삭제되면 해당 대상자가 더 이상 Experience Platform UI에 표시되지 않습니다. 단, 해당 대상자와 관련된 프로필은 실제 Experience Platform에서 삭제되지 않습니다.

+++

+++**Real-Time Customer Data Platform에 해당 프로필이 없는 경우 새 프로필이 생성됩니까?**

네. 그렇습니다.

+++

+++**Customer Journey Analytics는 파이프라인 이벤트 또는 데이터 레이크로 이동하는 플랫 파일로 대상자 데이터를 전송합니까?**

Customer Journey Analytics는 파이프라인을 통해 데이터를 Real-Time Customer Data Platform으로 스트리밍하고, 이 데이터는 데이터 레이크의 시스템 데이터 세트에도 수집됩니다.

+++

+++**Customer Journey Analytics는 어떤 신원을 전송합니까?**

[연결 설정](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-connections/create-connection)에 지정된 모든 ID/네임스페이스 쌍입니다. 이는 특히 사용자가 개인 ID로 사용할 필드를 선택하는 단계입니다.

+++

+++**기본 ID로 어떤 ID를 선택합니까?**

위를 참조하십시오. Customer Journey Analytics 개인당 하나의 ID만 전송됩니다.

+++

+++**Real-Time Customer Data Platform은 Customer Journey Analytics 메시지도 처리합니까? Customer Journey Analytics는 대상자 공유를 통해 ID를 프로필 아이덴티티 그래프에 추가할 수 있습니까?**

아니요. 개인당 하나의 ID만 전송되므로 Real-Time Customer Data Platform에서 사용할 그래프 에지가 없습니다.

+++

+++**일별, 주별, 월별 새로 고침은 하루 중 어느 시간에 이루어집니까? 주별 새로 고침은 어느 요일에 이루어집니까?**

새로 고침의 시기는 원래 대상자가 게시된 시점과 해당 시간(및 요일 또는 월)에 맞춰 결정됩니다.

+++

+++**일별, 주별, 월별 새로 고침 시간을 구성할 수 있습니까?**

아니요, 사용자는 새로 고침 시간을 구성할 수 없습니다.

+++


## 다음 단계

* 이 대상자를 관리하려면 [관리 UI](/help/components/audiences/manage.md)로 이동하십시오.
