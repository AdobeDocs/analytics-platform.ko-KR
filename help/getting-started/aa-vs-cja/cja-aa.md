---
title: Customer Journey Analytics 기능 지원
description: Customer Journey Analytics 기능과 Adobe Analytics 기능 세트를 비교한 것입니다.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 42b3b2e9a2ff8a46fd6c84e2425e19dcbb0d28f0
workflow-type: tm+mt
source-wordcount: '1493'
ht-degree: 91%

---

# Customer Journey Analytics 기능 지원

다음 표는 CJA(Customer Journey Analytics)에서 지원되거나, 부분적으로 지원되거나, 지원되지 않는 Adobe Analytics의 기능을 보여 줍니다. 이들 목록은 CJA에 추가되므로 시간이 지남에 따라 변경됩니다.

## 완전히 지원되는 기능/구성 요소

| Adobe Analytics 기능 | 지원 관련 참고 사항 |
| --- | --- |
| 예외 항목 탐지 | 전체 지원 |
| 기여도 분석 IQ | 전체 지원 |
| 계산된 지표 | 전체 지원: 기존 Analysis Workspace의 기존 계산된 지표는 CJA에 포팅되지 않습니다. |
| 달력 이벤트 | 전체 지원. 달력 이벤트가 [주석](/help/components/annotations/overview.md) 작업 영역. |
| 분류 규칙 빌더 | 전체 지원. 호출됨 [하위 문자열](/help/data-views/component-settings/substring.md) 참조하십시오. 조회 데이터 세트가 아니라 보고서 시간에 문자열 조킹을 사용합니다. |
| 크로스 디바이스/크로스 채널 결합 | 전체 지원: [크로스 채널 Analytics](/help/connections/cca/overview.md)를 참조하십시오. |
| CSV 다운로드 | 전체 지원 |
| 사용자 정의 달력 | 전체 지원 |
| 날짜 비교 | 전체 지원 |
| 날짜 범위 | 모든 날짜 범위 기능이 지원됩니다. |
| 일광 절약 시간제 | 전체 지원 |
| 디바이스, 브라우저, 레퍼러, 기술 차원 | 이러한 차원은 AEP 데이터 세트에 특정 XDM 스키마 필드가 포함되고 XDM 경험 이벤트 클래스를 준수하는 경우에 자동으로 포함됩니다. [ADC를 통해 지원되는 Analytics 변수에 대한 설명서](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=ko-KR?lang=en)를 참조하십시오.<p>Adobe Source Connector를 사용하여 Adobe Analytics의 데이터를 CJA로 채우지 않고 대신 Experience Platform Web SDK 데이터 수집을 사용하는 경우 현재 디바이스 조회를 기반으로 하는 디바이스 및 차원이 지원되지 않습니다. 그러나 조만간 지원될 예정입니다. |
| 차원 | 전체 지원: CJA는 XDM을 활용하며 무제한 차원을 지원합니다. CJA는 기존 Adobe Analytics의 사용자 정의 eVar 또는 속성에 연결되지 않습니다. |
| GDPR 삭제 | 전체 지원: 이제 [!UICONTROL Adobe Experience Platform]에 GDPR이 적용됩니다. CJA는 [!UICONTROL Experience Platform]의 기본 데이터 세트에 적용되는 모든 데이터 변경 사항을 상속합니다. |
| 목록 변수/목록 속성 | 전체 지원: CJA는 XDM을 활용하며 listVar와 유사하게 사용할 수 있는 무제한 문자열 배열을 지원합니다. |
| 머천다이징 변수 지속성 | [바인딩 차원 및 바인딩 지표](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ko-KR#binding-dimension)를 통한 전체 지원 |
| 머천다이징 eVar | [바인딩 차원 및 바인딩 지표](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)를 통한 전체 지원 |
| 지표 | 전체 지원: CJA는 XDM(Experience Data Model)을 활용하고 무제한 지표를 지원하며, 기존 Analytics의 사용자 정의 성공 이벤트에 연결되지 않습니다. 일부 표준 지표의 이름은 기존 Analytics에서 다음과 같이 변경되었습니다. 방문자 = 사람, 방문 횟수 = 세션, 히트 수 = 이벤트 |
| 지표 중복 제거 | 전체 지원 |
| 모바일 스코어카드/대시보드 | 전체 지원 |
| 패널 | 빈 패널, 기여도 분석 패널, 자유 형식 패널 및 빠른 인사이트가 완벽하게 지원됩니다. |
| PDF 내보내기 | 전체 지원 |
| 프로젝트 큐레이션 | 전체 지원 |
| 프로젝트 연결 | 전체 지원 |
| Report Builder (Excel 플러그인) | 전체 지원 |
| 보고서 처리 시간 | 전체 지원: CJA는 보고서 처리 시간에만 사용합니다. |
| 보고 API 액세스 | 전체 지원: [CJA API](https://www.adobe.io/cja-apis/docs/)를 통해 이용 가능합니다. |
| 예약된 보고서/프로젝트 | 전체 지원 |
| 세그먼트 | 전체 지원: 이제 “필터”라고 합니다. 기존 Analysis Workspace의 기존 세그먼트는 CJA로 포팅되지 않습니다. |
| 스트리밍 미디어 분석 | 미디어 데이터는 Workspace의 미디어 동시 뷰어 패널 및 미디어 재생 시간 패널의 일부로 2022년 7월 30일 사용할 수 있습니다. |
| 사용자 권한/데이터 액세스 제어 | 전체 지원: CJA는 [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=ko-KR) 제품 관리자와 사용자를 구별합니다. 제품 관리자만 다음과 같은 작업을 수행할 수 있습니다. <ul><li>연결 또는 데이터 보기 만들기/업데이트/삭제</li><li>다른 사용자가 만든 프로젝트, 필터 또는 계산 지표를 업데이트/삭제</li><li>모든 사용자에게 작업 영역 프로젝트 공유</li></ul> |
| 가상 보고서 세트 | 전체 지원: 이제 [데이터 보기](/help/data-views/create-dataview.md)라고 합니다. |
| VRS 구성 요소 큐레이션 | 전체 지원: 이제 데이터 보기의 일부라고 합니다. |

{style=&quot;table-layout:auto&quot;}

## 경고가 지원됨

| 기능 | 참고 |
| --- | --- |
| A4T | [Adobe Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR)의 필드를 통해 지원이 제공됩니다. |
| 분류 | 이제 &quot;조회 데이터 세트&quot;라고 합니다. Analytics에서 사용되는 분류는 Analytics 분류 소스 커넥터를 사용하여 Experience Platform 및 CJA로 가져올 수 있습니다. 조회 데이터 세트를 AEP에 직접 업로드하여 CJA에서 사용할 수도 있습니다. |
| 사용자 정의 세션 | 모바일 배경 조회수를 제외한 모든 사용자 정의 세션 기능을 지원합니다. |
| 고객 속성 | 이제 “프로필 데이터 세트”라고 하며, Experience Cloud에서 자동으로 가져오지 않습니다. CJA에서 사용하려면 AEP로 업로드해야 합니다. |
| [!UICONTROL 디바이스], [!UICONTROL 브라우저], [!UICONTROL 레퍼러], [!UICONTROL 기술] 차원 | 이러한 차원은 AEP 데이터 세트에 특정 XDM 스키마 필드가 포함되고 XDM 경험 이벤트 클래스를 준수하는 경우에 자동으로 포함됩니다. [Analytics 소스 커넥터를 통해 지원되는 Analytics 변수에 대한 설명서](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=ko-KR)를 참조하십시오. 소스 커넥터를 사용하여 Adobe Analytics의 데이터를 CJA로 채우지 않고 대신 AEP Web SDK 데이터 수집을 사용하는 CJA 고객의 경우, 디바이스 조회를 기반으로 하는 [!UICONTROL 디바이스] 및 차원이 현재 지원되지 않지만 조만간 지원될 예정입니다. |
| 시작, 종료, 사용 시간 차원 및 지표 | 지원되며(시작 및 종료는 이제 세션 시작 및 세션 종료라고 함), 약간 다른 방식으로 계산됩니다. |
| eVar 지속성 설정 | eVar는 더 이상 CJA에 포함되지 않습니다. 하지만 지속성 설정은 이제 데이터 보기에 속하고, 모든 차원에서 사용할 수 있습니다. 지속성은 데이터 수집 처리 시간이 아니라 보고서 처리 시간을 기반으로 한다는 점을 명심하십시오. 데이터 보기 내에서 설정된 차원은 최대 90일로 지속성이 제한되며 무제한 지속성을 지원하지 않습니다. |
| 지리 특성 - 차원 | Adobe Analytics에 수집된 모든 지리 특성/지역은 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)를 통해 CJA로 전송됩니다. 디지털 데이터 수집을 위해 AEP 웹 SDK를 사용하는 구현과 같이 Analytics 소스 커넥터를 사용하지 않는 구현에는 전체 지리적 조회가 자동으로 수행되지 않습니다(국가와 주는 전 세계적으로 지원되며 도시와 우편번호는 지원되지 않음). |
| IP 난독화 | Analytics 소스 커넥터를 사용하여 Adobe Analytics의 데이터를 CJA로 채우는 CJA 고객의 경우: Adobe Analytics에 적용된 IP 난독화 설정은 CJA 데이터로 이동합니다. 필요에 따라 Adobe Analytics에서 이러한 설정을 제어할 수 있습니다.<p>Adobe Experience Platform Web SDK를 사용하여 데이터를 Platform과 CJA에 직접 채우는 CJA 고객의 경우: 플랫폼의 데이터 수집을 위해 데이터 준비 를 사용하여 회사의 요구 사항에 따라 IP 주소를 난독화하는 규칙을 구성할 수 있습니다. |
| 마케팅 채널 | 마케팅 채널 데이터가 Analytics 소스 커넥터를 통해 CJA로 전송됩니다. 마케팅 채널 규칙은 계속 기존의 Adobe Analytics에서 구성해야 합니다. 일부 규칙은 지원되지 않습니다. 자세한 내용은 [CJA 마케팅 채널 설명서](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=ko-KR#cja-usecases)를 참조하십시오. |
| 새 세션 보고와 반복 세션 보고 비교 | 2022년 8월 17일에 지원됨 [13개월 전환 확인 기간 사용](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=en#new-repeat). |
| 제품 변수 | Experience Platform 내에서 사용자는 데이터 세트 스키마 내의 개체 유형 필드 배열을 사용하여 이 사용 사례를 충족할 수 있습니다. CJA 내에서 고객은 다양한 제품 변수를 사용할 수 있으며 Adobe Analytics에서처럼 단일 변수로 제한되지 않습니다. |
| 프로젝트 공유 | 프로젝트 공유는 CJA 사용자 사이에서만 지원됩니다. CJA와 기존 Analysis Workspace 간에 프로젝트를 공유할 수 없습니다. |
| 시각화 | 맵 시각화를 제외한 모든 시각화가 지원됩니다. |

{style=&quot;table-layout:auto&quot;}

## 부분 지원

| 기능 | 참고 |
| --- | --- |
| 보트 필터링 | [Adobe Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) 기반 데이터 세트의 경우 보트 필터링이 적용됩니다. 다른 데이터 세트에 대한 일반 보트 필터링 논리 기능은 [!UICONTROL Experience Platform] 또는 CJA에서 사용할 수 없습니다. |
| 패널 | 빈 패널, 기여도 분석 패널, 자유 형식 패널 및 빠른 인사이트가 완벽하게 지원됩니다. 세그먼트 비교 및 A4T(타겟 분석) 패널은 지원되지 않습니다. |
| 처리 규칙 | Analytics 소스 커넥터 기반 데이터 세트의 경우 처리 규칙이 여전히 적용됩니다. [Adobe Experience Platform의 데이터 준비 기능](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html)을 플랫폼으로 직접 이동되는 데이터에 대한 처리 규칙 대용으로 사용할 수도 있습니다. |

{style=&quot;table-layout:auto&quot;}

## 현재는 지원되지 않지만, 지원 예정

| 기능 | 참고 |
| --- | --- |
| 경고 | 지원이 예정되어 있습니다. |
| 기여도 분석 | 지원이 예정되어 있습니다. |
| 데이터 웨어하우스 보고 (100% 행 내보내기) | Analysis Workspace 인터페이스에서 지원이 예정되어 있습니다. Adobe Experience Platform [[!UICONTROL 쿼리 서비스]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ko-KR) 또한 CJA에서의 이러한 사용 사례에 대한 인터페이스를 제공합니다. |
| 디바이스 그래프를 통한 ID 결합 | 지원이 예정되어 있습니다. |
| 상승도 및 신뢰도 보고 | 지원이 예정되어 있습니다. |
| 처리 규칙, VISTA 규칙, 마케팅 채널 처리 규칙 | 지원이 예정되어 있지만 데이터 수집이 아닌 쿼리 시간에 실행되어 보다 유연하고 소급적이며 비파괴적인 데이터 조작이 가능하게 됩니다. |
| 프로젝트 템플릿 | 지원이 예정되어 있습니다. |
| 실시간 보고 | 지원이 예정되어 있습니다. |
| 세그먼트 IQ | 지원이 예정되어 있습니다. |

{style=&quot;table-layout:auto&quot;}

## 지원이 아직 예정되지 않음

| 기능 | 참고 |
| --- | --- |
| Activity Map | 지원이 아직 예정되지 않음 |
| Advertising Cloud | 지원이 아직 예정되지 않음 |
| 통화 전환 | 지원이 아직 예정되지 않음 |
| 데이터 피드 | 지원이 아직 예정되지 않음 |
| 요약 데이터 소스 | 지원이 아직 예정되지 않음 |
| 거래 ID 데이터 소스 | 지원이 아직 예정되지 않음 |

{style=&quot;table-layout:auto&quot;}

## 지원 예정 없음

* 크로스 디바이스 조합을 사용하는 사용자 지표
* Reports &amp; Analytics 대시보드
* Reports &amp; Analytics 책갈피
* Reports &amp; Analytics 대상
* 모바일 서비스
