---
title: 데이터 피드 만들기
description: 데이터 피드를 만드는 방법과 Adobe에 제공할 파일 정보에 대해 알아봅니다.
hide: true
feature: Components
autotag-review: '2026-05-19T08:45:44.870Z'
TQID: 'https://experienceleague.adobe.com/QgBD7vCkw4YA568XOLlwTnw8eZVZybXr3DFbM1ZKYDw'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: b31ae6194d30115f4d653addaf5efff5790e987c
workflow-type: tm+mt
source-wordcount: 2675
ht-degree: 29%

---

# 데이터 피드 만들기

데이터 피드를 만들 때 Adobe에 다음 기능을 제공합니다.

* 원시 데이터 파일을 전송할 대상에 대한 정보

* 각 파일에 포함할 데이터

* 데이터가 전송되는 빈도(늦게 도착하는 히트를 캡처하는 처리 지연 포함)

데이터 피드를 만들기 전에 데이터 피드에 대해 기본적으로 이해하고 모든 전제 조건을 충족하는지 확인하는 것이 중요합니다. 자세한 내용은 [데이터 피드 개요](data-feed-overview.md)를 참조하십시오.

## 데이터 피드 만들기 및 구성 {#create-and-configure-data-feed}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_export_file"
>title="매니페스트"
>abstract="각 데이터 피드 게재에 매니페스트 파일을 포함할지 여부를 선택합니다. 매니페스트 파일에는 데이터 피드에 포함된 각 파일에 대한 정보가 있습니다. 데이터 피드 데이터를 하나의 패키지로 보낼 때, 완료한 파일을 포함하도록 선택할 수도 있지만, 매니페스트 파일이 권장됩니다. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_notify"
>title="완료되면 알림"
>abstract="데이터 피드가 전송된 후 알림을 게재해야 하는 이메일 주소를 하나 이상 지정합니다. 여러 이메일 주소는 쉼표로 구분해야 합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_lookback_date_range"
>title="전환 확인 날짜 범위"
>abstract="데이터 피드 게재를 처리할 때 Customer Journey Analytics에서 얼마나 지난 날짜까지 조회할지를 제어합니다.<br/>이 설정은 빈도 기간(시간 또는 날)을 변경하지 않습니다. 그러나 전환 확인 날짜 범위는 게재되는 데이터에 영향을 줄 수 있습니다. 세그먼트 선별, 세션 계산, 일부 파생 필드 변환 및 차원 지속성은 모두 전환 확인 날짜 범위의 영향을 받습니다."

<!-- markdownlint-enable MD034 -->

1. Adobe ID 자격 증명을 사용하여 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)에 로그인합니다.

1. 인터페이스 오른쪽 상단에 있는 앱 전환기 ![App](/help/assets/icons/Apps.svg)에서 [!UICONTROL **Customer Journey Analytics**]&#x200B;를 선택합니다.

1. 위쪽 탐색 모음에서 [!UICONTROL **구성 요소**] > [!UICONTROL **데이터 피드**](으)로 이동합니다.

1. 화면 오른쪽 상단에서 [!UICONTROL **만들기**]&#x200B;를 선택합니다.

   또는 이전에 만든 데이터 피드가 없으면 빈 테이블에서 [!UICONTROL **데이터 피드 만들기**]&#x200B;를 선택하십시오.

   [!UICONTROL **세부 정보**], [!UICONTROL **데이터 구조**] 및 [!UICONTROL **게재**] 탭으로 페이지가 표시됩니다.

   ![새 데이터 피드 페이지](assets/data-feed-new.png)

1. [!UICONTROL **세부 정보**] 탭에서 다음 필드를 작성합니다.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **이름**] | 데이터 피드의 이름. 이름은 선택한 데이터 보기 내에서 고유해야 하며 최대 255자까지 사용할 수 있습니다. <!--[Learn more](/help/export/analytics-data-feed/df-faq.md#must-feed-names-be-unique)--> |
   | [!UICONTROL **태그**] | 쉽게 분류할 수 있도록 데이터 피드에 태그를 적용합니다. <!--You can filter on tags as described in [Filter and search the list of data feeds](/help/export/analytics-data-feed/df-manage-feeds.md#filter-and-search-the-list-of-data-feeds) in [Manage data feeds](/help/export/analytics-data-feed/df-manage-feeds.md).--> |
   | [!UICONTROL **설명**] | 데이터 피드에 대한 설명을 지정합니다. 추가한 설명은 데이터 피드를 편집할 때 표시됩니다. |
   | [!UICONTROL **데이터 보기**] | 내보낼 데이터가 포함된 데이터 보기를 선택합니다.<p>데이터 보기를 선택할 때는 다음 사항을 고려하십시오.</p> <ul><li>동일한 데이터 보기에 대해 여러 데이터 피드가 만들어지는 경우 각 데이터 피드의 열 정의는 서로 달라야 합니다.</li><li>사용 가능한 열 목록은 선택한 데이터 보기가 속한 로그인 회사에 따라 다릅니다. 데이터 보기를 변경하면 사용 가능한 열 목록이 변경될 수 있습니다. </li></ul> |

1. [!UICONTROL **다음**]&#x200B;을 선택합니다.

1. [!UICONTROL **데이터 구조**] 탭에서 **[!UICONTROL 데이터 보기]** 필드에 올바른 데이터 보기가 선택되어 있는지 확인하십시오.

1. [!UICONTROL **세그먼트**] 드롭다운 메뉴에서 피드에 포함된 데이터를 필터링할 세그먼트를 검색하고 선택합니다.

   여러 세그먼트를 적용하면 AND 연산자와 함께 결합됩니다. (세그먼트를 OR 연산자로 조인하려면 먼저 세그먼트 빌더에서 새 세그먼트를 만든 다음 데이터 피드에 새 세그먼트를 적용해야 합니다.)

1. 데이터 피드 구성에 구성 요소를 추가합니다. 왼쪽 레일에서 포함할 구성 요소를 찾은 다음 캔버스로 드래그하여 데이터 구조를 만듭니다. **[!UICONTROL Shift 키]**&#x200B;를 누르거나 **[!UICONTROL Command]**(macOS) 또는 **[!UICONTROL Ctrl]**(Windows) 키를 누른 상태에서 여러 구성 요소를 선택할 수 있습니다.

   다음 정보를 사용하여 항상 포함되는 차원, 포함할 수 없는 차원 및 대체해야 하는 지표를 이해합니다.

   +++ 데이터 피드에 항상 포함되는 차원

   다음 차원은 기본적으로 모든 데이터 피드에 포함되며 제거할 수 없습니다.

   | 차원 이름 | 참고 | 데이터 피드 | 기타 보고 |
   |---|---|---|---|
   | 타임스탬프 | 이벤트 기간의 타임스탬프. 마이크로초 세부 기간. UTC로 표시됩니다. | 필수 | 사용할 수 없음 |
   | 행 ID | 고유 행 식별자 | 필수 | 사용할 수 없음 |
   | 세션 ID | 각 세션에 대한 고유 식별자 | 필수 | 사용할 수 없음 |
   | 개인 ID | 데이터 보기 및 연결에 대한 개인 식별자 | 필수 | 선택 사항 표준 |
   | 계정 ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 계정 컨테이너를 사용할 때의 계정 ID | 필수 | 선택 사항 표준 |

   +++

   +++ 데이터 피드에 포함할 수 없는 차원

   Customer Journey Analytics 표준 차원은 데이터 피드에 포함할 수 없습니다. 다음 표에는 이러한 차원이 나열되어 있습니다.

   | 차원 이름 | 참고 | 데이터 피드 |
   |---|---|---|
   | 5분 | 이벤트가 발생한 5분 간격(내림) | 사용할 수 없음 |
   | 15분 | 이벤트 발생 시 15분 간격(내림) | 사용할 수 없음 |
   | 30분 | 이벤트 발생 시 30분 간격(내림) | 사용할 수 없음 |
   | 일 | 이벤트 발생 일 | 사용할 수 없음 |
   | 요일 | 이벤트가 발생한 요일 | 사용할 수 없음 |
   | 날짜 (월 기준) | 이벤트가 발생한 날짜 | 사용할 수 없음 |
   | 시간 | 이벤트 발생 시간(내림) | 사용할 수 없음 |
   | 시간 | 이벤트가 발생한 시간(내림) | 사용할 수 없음 |
   | 분 | 이벤트 발생 시간(분)(내림) | 사용할 수 없음 |
   | 분/시간 | 이벤트가 발생한 시간(분)(내림) | 사용할 수 없음 |
   | 월 | 이벤트 발생 월 | 사용할 수 없음 |
   | 월(연 기준) | 이벤트가 발생한 월의 월 | 사용할 수 없음 |
   | 분기 | 이벤트 발생 분기 | 사용할 수 없음 |
   | 사분기 | 이벤트가 발생한 사분기 | 사용할 수 없음 |
   | Second | 이벤트가 발생한 두 번째 시간(내림) | 사용할 수 없음 |
   | 주 | 이벤트 발생 주 | 사용할 수 없음 |
   | 주(한 해 기준) | 이벤트가 발생한 주 | 사용할 수 없음 |
   | 년 | 이벤트 발생 연도 | 사용할 수 없음 |

   +++

   +++ 데이터 피드에서 대체해야 하는 지표

   다음 Customer Journey Analytics 지표를 대체해야 합니다.

   | 지표 이름 | 참고 | 데이터 피드 |
   |---|---|---|
   | 계정 ([!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}) | 연결에 지정된 계정 ID를 기반으로 함 | 사용할 수 없음. 계정 ID 고유 개수 사용. |
   | 구매 그룹 [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 연결의 구매 그룹 ID를 기반으로 하는 구매 그룹 | 사용할 수 없음. 구매 그룹 ID의 고유 개수를 사용합니다. |
   | 이벤트 | 연결의 모든 이벤트 데이터 세트의 행 수 | 사용할 수 없음. 행 ID의 고유 개수 사용. |
   | 글로벌 계정 ([!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}) | 연결의 글로벌 계정 ID 기반 | 사용할 수 없음. 글로벌 계정 ID의 고유 개수를 사용합니다. |
   | 기회 ([!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}) | 연결의 영업 기회 ID를 기반으로 하는 영업 기회 | 사용할 수 없음. 영업 기회 ID 고유 개수 사용. |
   | 사람 | 연결에 지정된 개인 ID 기반 | 사용할 수 없음. 개인 ID 고유 개수 사용. |
   | 대화 | 대화 수 | 사용할 수 없음. 대화 ID 고유 개수 사용. |
   | 세션 종료 | 세션의 마지막 이벤트였던 이벤트 수 | 사용할 수 없음 |
   | 세션 시작 | 세션의 첫 번째 이벤트였던 이벤트 수 | 사용할 수 없음 |
   | 세션 | 데이터 보기의 세션 설정을 기반으로 합니다. | 사용할 수 없음. 세션 ID의 고유 개수 사용. |
   | 체류 시간 (초) | 서로 다른 두 차원 값 사이의 시간을 합합니다. | 사용할 수 없음 |

   +++

   +++ 선택 사항 표준 구성 요소

   | 구성 요소 이름 | 유형 | 참고 | 데이터 피드 |
   |---|---|---|---|
   | 오전/오후 | 차원 시간 분할 | 오전 또는 오후 | 사용할 수 없음 |
   | 배치 ID | 차원 | Experience Platform 배치용 식별자 | 사용 가능 |
   | 데이터 세트 ID | 차원 | Experience Platform 데이터 세트에 대한 식별자 | 사용 가능 |
   | 날짜 (월 기준) | 차원 시간 분할 | 1-31 | 사용할 수 없음 |
   | 요일 | 차원 시간 분할 | 월요일부터 일요일까지 | 사용할 수 없음 |
   | 일(한 해 기준) | 차원 시간 분할 | 1-366 | 사용할 수 없음 |
   | 이벤트 심도 | 치수 | 순차적 숫자 값(1, 2, 3 등) 세션 내의 각 이벤트 상호 작용에 할당됨<p>각 새 세션이 시작될 때 재설정</p> | 사용 가능 |
   | 시간 | 차원 시간 분할 | 0-23 | 사용할 수 없음 |
   | 월(연 기준) | 차원 시간 분할 | 1월-12월 | 사용할 수 없음 |
   | 최초 세션 | 지표 | 보고 기간 내에 개인의 첫 번째 정의된 세션 | 사용할 수 없음 |
   | 재방문 세션 | 지표 | 개인의 첫 번째 세션이 아닌 세션 | 사용할 수 없음 |
   | 개인 ID 네임스페이스 | 차원 | 개인 ID가 구성하는 ID 유형(예: 이메일 또는 쿠키 ID) | 사용 가능 |
   | 글로벌 계정 ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 차원 | 글로벌 계정 컨테이너를 사용할 때의 글로벌 계정 ID | 사용 가능 |
   | 영업 기회 ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 차원 | 영업 기회 컨테이너를 사용할 때의 영업 기회 ID | 사용 가능 |
   | 구매 그룹 ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 차원 | 구매 그룹 컨테이너를 사용할 때 구매 그룹 ID | 사용 가능 |
   | 사분기 | 차원 시간 분할 | Q1, Q2, Q3, Q4 | 사용할 수 없음 |
   | 세션 반복 | 지표 | 개인의 첫 번째 세션이 아닌 세션 | 사용할 수 없음 |
   | 세션 유형 | 차원 | 두 가지 값: 최초 또는 재방문 | 사용할 수 없음 |
   | 이벤트당 소비한 시간 | 차원 | 소비한 시간 지표를 이벤트 버킷에 버킷팅합니다 | 사용할 수 없음 |
   | 세션당 소비한 시간 | 차원 | 소비한 시간 지표를 세션 버킷에 버킷팅합니다 | 사용할 수 없음 |
   | 사용자당 소비한 시간 | 차원 | 소비한 시간 지표를 사용자 버킷에 버킷팅합니다 | 사용할 수 없음 |
   | 주말/평일 | 차원 시간 분할 | 주말 또는 평일 | 사용할 수 없음 |

   +++


1. [!UICONTROL **배달**] 탭에서 다음 정보를 지정하십시오.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **피드 유형**] | 만들려는 피드 유형을 선택합니다.<ul><li>[!UICONTROL **라이브 피드**]: 현재 및 향후 데이터를 내보냅니다.</li><li>[!UICONTROL **피드 채우기**]: 두 개의 지난 날짜 사이의 이전 데이터를 내보냅니다.</li></ul> |
   | [!UICONTROL **시작 날짜**] | 데이터 피드를 시작할 날짜를 지정합니다. 내역 데이터에 대한 데이터 피드 처리를 즉시 시작하려면 [!UICONTROL **피드 채우기**]&#x200B;가 선택되어 있는지 확인한 다음 이 날짜를 데이터가 수집되는 과거의 날짜로 설정하십시오. 시작 날짜는 데이터 보기의 시간대를 기반으로 합니다. |
   | [!UICONTROL **종료 날짜**] | 데이터 피드를 종료할 날짜를 지정합니다. 종료 날짜는 데이터 보기의 시간대를 기반으로 합니다. |
   | [!UICONTROL **빈도**] | 데이터 피드를 전송해야 하는 빈도를 선택합니다. 빈도 창에 속하는 타임스탬프가 있는 이벤트는 데이터 피드 배달에 포함됩니다. [!UICONTROL **전환 확인 날짜 범위**] 및 [!UICONTROL **처리 지연**] 필드는 선택한 게재 빈도의 데이터에 포함된 이벤트에도 영향을 줄 수 있습니다.<p>라이브 피드의 경우 1시간의 데이터 또는 1일의 데이터를 포함하도록 선택합니다. 채우기 피드는 일별이어야 합니다.</p><ul><li>**일별**: 피드에 데이터 보기의 시간대에 자정부터 자정까지 하루 분량의 데이터가 포함됩니다. 피드 채우기 또는 라이브 피드에 이 옵션을 사용합니다.</li><li>**시간별**: 피드에는 1시간 동안의 데이터가 포함됩니다. 라이브 피드에 이 옵션을 사용합니다.</li></ul> |
   | [!UICONTROL **전환 확인 날짜 범위**] | 데이터 피드 게재를 처리할 때 Customer Journey Analytics에서 얼마나 지난 날짜까지 조회할지를 제어합니다. <p>이 설정은 데이터 피드 출력에 포함할 이벤트의 시간 프레임을 정의하는 빈도 창(시간 또는 일)을 변경하지 않습니다. 그러나 전환 확인 날짜 범위는 다음과 같은 방법으로 전달되는 데이터에 영향을 줄 수 있습니다. </p><ul><li>**세그먼트 자격**: 세그먼트가 데이터 피드 정의에 적용되면 전환 확인 날짜 범위 내의 모든 이벤트에 따라 개인의 자격 여부가 결정됩니다. 세그먼트의 컨테이너 설정에 따라 범위가 결정됩니다. (가능한 컨테이너는 개인, 세션 또는 이벤트입니다.) B2B에는 다음과 같은 추가 컨테이너가 있습니다. Global 계정, 계정, 기회, 구매 그룹.)  <p>예를 들어 개인 컨테이너가 사용되고 개인이 전환 확인 날짜 범위 동안 자격을 얻으면 빈도 창 동안 해당 개인의 모든 이벤트도 자격을 얻습니다.</p></li><li>**세션 계산**: 세션 경계는 전환 확인 날짜 범위 내의 데이터를 사용하여 계산됩니다.</li><li>**파생 필드 변환**: 컨테이너를 참조하는 파생 필드 함수는 데이터 피드 내보내기에서 전환 확인 날짜 범위를 사용합니다.</li><li>**Dimension 지속성**: 개별 차원에 대한 지속성 설정을 선택하는 경우 만료를 선택하여 설정된 이벤트에서 벗어난 차원 항목의 지속 기간도 결정합니다. <p>데이터 보기에서 다음 옵션 중 하나로 만료를 설정하면 전환 확인 날짜 범위가 차원 지속성에 영향을 줍니다.</p><ul><li>[!UICONTROL **보고 기간**]&#x200B;을 만료로 사용하는 데이터 피드 정의의 각 차원에 대해 전환 확인 날짜 범위가 새 보고 기간이 됩니다.</li><li>[!UICONTROL **사용자 지정 시간**]&#x200B;을(를) 만료로 사용하는 데이터 피드 정의의 각 차원에 대해, 선택한 사용자 지정 시간이 전환 확인 날짜 범위를 벗어나는 경우 사용자 지정 시간은 무시되며 전환 확인 날짜 범위는 차원 만료에 사용됩니다.<p>데이터 보기 내의 차원에 대한 지속성 설정에 대한 자세한 내용은 [지속성 구성 요소 설정](/help/data-views/component-settings/persistence.md)을 참조하십시오.</p></li></ul> |
   | [!UICONTROL **처리 지연**] | 데이터 피드 파일을 처리하기 전에 대기할 시간을 선택합니다. 처리 지연 중에 들어오는 모든 늦게 도착하는 히트는 데이터 피드에 포함됩니다. <p>처리 지연은 모바일 구현에 오프라인 디바이스를 온라인 상태로 전환하여 데이터를 전송할 수 있는 기회를 제공하거나 이전에 처리된 파일을 관리할 때 조직의 서버측 프로세스를 수용하는 등 다양한 이유로 유용합니다. </p><p>피드를 2, 3, 4 또는 8시간 지연시킬 수 있습니다.<p>세션이 포함되려면 처리 지연 컷오프 이후에 시작해야 합니다. 컷오프 전에 시작되고 처리 지연 내에 끝나는 세션은 포함되지 않습니다.</p> |
   | [!UICONTROL **압축 포맷**] | 클라우드 대상에 제공된 Parquet 출력 파일의 압축 형식을 선택합니다. 다음 형식 중에서 선택합니다.<ul><li>[!UICONTROL **Snappy**]: 적절한 파일 크기를 사용하여 빠른 압축 및 압축 풀기 BigQuery, Snowflake 및 Apache Spark와 같은 최신 데이터 플랫폼에서 폭넓게 지원됩니다.</li><li>[!UICONTROL **GZip**]: 기본적으로 Snappy를 지원하지 않는 도구를 포함하여 광범위하게 호환됩니다. 다운스트림 파이프라인에 널리 알려진 압축 표준이 필요한 경우 권장됩니다.</li><li>[!UICONTROL **Z 표준(Zstd)**]: 빠른 압축 풀기 기능으로 압축 효율이 높습니다. 파일 크기를 최소화하는 것이 우선 순위이고 도구가 Zstd를 지원하는 경우 적합합니다.</li></ul> |

1. [!UICONTROL **배달**] 탭의 [!UICONTROL **대상**] 섹션에서 데이터를 전송할 대상을 구성합니다.

   >[!NOTE]
   >
   >보고서 대상 구성 시 다음과 같은 사항을 고려하십시오.
   >
   ><!--* Adobe recommends using a cloud account for your report destination. [Legacy FTP and SFTP accounts](/help/components/locations/configure-import-accounts.md) are available, but are not recommended.-->
   >* 이전에 구성한 모든 클라우드 계정은 데이터 피드에 사용할 수 있습니다. [구성 요소 > 내보내기 > 위치 계정](/help/components/exports/cloud-export-accounts.md)의 위치 관리자에서 클라우드 계정을 구성할 수 있습니다.
   >
   >* 클라우드 계정은 Customer Journey Analytics 사용자 계정과 연결되어 있습니다. 조직의 모든 사용자가 클라우드 계정을 사용할 수 있도록 설정하지 않는 한 사용자가 구성한 클라우드 계정을 다른 사용자가 사용하거나 볼 수 없습니다.
   >
   >* [구성 요소 > 내보내기 > 위치](/help/components/exports/cloud-export-locations.md)의 위치 관리자에서 만드는 모든 위치를 편집할 수 있습니다.

   다음 필드를 완료합니다.

   | 필드 | 함수 |
   |---------|----------|
   | [!UICONTROL **모든 사용자의 대상 보기**] | 시스템 관리자인 경우 이 옵션을 활성화하여 조직의 모든 사용자가 만든 대상을 볼 수 있습니다. 이 옵션이 비활성화되면 사용자가 만든 대상만 표시됩니다. |
   | [!UICONTROL **계정**] | 다음 중 하나를 수행합니다.<ul><li>**기존 계정 사용:** **[!UICONTROL 계정]** 필드 옆에 있는 드롭다운 메뉴를 선택합니다. 또는 계정 이름을 입력한 다음 드롭다운 메뉴에서 선택합니다. <p>계정을 구성했거나 속해 있는 조직과 공유하는 경우에만 계정을 사용할 수 있습니다.</p></li><li>**새 계정 만들기:** **[!UICONTROL 계정]** 드롭다운 메뉴에서 **[!UICONTROL 계정 추가]**&#x200B;를 선택합니다. 계정 구성 방법에 대한 자세한 내용은 [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md)을 참조하십시오.</li></ul> |
   | [!UICONTROL **위치**] | 다음 중 하나를 수행합니다.<ul><li>**기존 위치 사용:** **[!UICONTROL 위치]** 필드 옆에 있는 드롭다운 메뉴를 선택합니다. 또는 위치 이름을 입력한 다음 드롭다운 메뉴에서 선택합니다.</li><li>**새 위치 만들기:** **[!UICONTROL 위치]** 드롭다운 메뉴에서 **[!UICONTROL 위치 추가]**&#x200B;를 선택합니다. 위치를 구성하는 방법에 대한 자세한 내용은 [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md)을 참조하십시오.</li></ul> |
   | [!UICONTROL **완료 시 알림**] | 데이터 피드가 성공적으로 전송되거나 전송이 실패한 후 알림을 배달해야 하는 이메일 주소를 하나 이상 지정합니다. 여러 이메일 주소는 쉼표로 구분해야 합니다. |
   | [!UICONTROL **매니페스트 사용**] | 각 데이터 피드 게재에 매니페스트 파일을 포함할지 여부를 선택합니다. 매니페스트 파일에는 데이터 피드에 포함된 각 파일에 대한 정보가 있습니다. |

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

