---
title: Customer Journey Analytics 기능 지원
description: Customer Journey Analytics 기능과 Adobe Analytics 기능 세트를 비교한 것입니다.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
source-git-commit: c23b172fd4dc5d0303723c4e8ccfeaa251257bfd
workflow-type: tm+mt
source-wordcount: '1188'
ht-degree: 68%

---

# Customer Journey Analytics 기능 지원

다음 표는 CJA(Customer Journey Analytics)에서 지원되거나, 부분적으로 지원되거나, 지원되지 않는 Adobe Analytics의 기능을 보여 줍니다. 이들 목록은 CJA에 추가되므로 시간이 지남에 따라 변경됩니다.

## 완전히 지원되는 기능/구성 요소

| Adobe Analytics 기능 | 지원 관련 참고 사항 |
| --- | --- |
| 예외 항목 탐지 | 전체 지원 |
| 기여도 분석 IQ | 전체 지원 |
| 계산된 지표 | 전체 지원 기존 Analysis Workspace에 있는 기존의 계산된 지표는 CJA로 포팅되지 않습니다. |
| 크로스 디바이스/크로스 채널 결합 | 전체 지원 [크로스 채널 분석](/help/connections/cca/overview.md)을 참조하십시오. |
| 날짜 비교 | 전체 지원 |
| 차원 | 전체 지원 CJA는 XDM을 활용하고 무제한 차원을 지원합니다. CJA는 기존 Adobe Analytics의 사용자 지정 eVar 또는 prop에 연결되어 있지 않습니다. |
| 기본 Analysis Workspace 차원(예: 브라우저 유형, 레퍼러 유형, 운영 체제 등) | CJA는 기본 XDM 필드(예: 사용자 에이전트 또는 디바이스 ID)가 추가되면 기본적으로 이러한 차원을 제공합니다. ADC(Analytics Data Connector)를 사용하는 고객의 경우 이러한 차원 중 일부를 사용할 수 있지만 모두 사용할 수는 없습니다. [ADC를 통해 지원되는 Analytics 변수에 대한 설명서](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)를 참조하십시오. |
| GDPR 삭제 | 전체 지원 이제 GDPR이 [!UICONTROL Adobe Experience Platform]과 함께 처리됩니다. CJA는 [!UICONTROL Experience Platform]에서 기본 데이터 세트에 변경한 모든 데이터 변경 사항을 상속합니다. |
| 목록 변수/목록 속성 | 전체 지원 CJA는 XDM을 활용하고 listVars와 유사하게 사용할 수 있는 무제한 문자열 배열을 지원합니다. |
| 지표 | 전체 지원 CJA는 XDM(Experience Data Model)을 활용하고 무제한 지표를 지원하며, 기존 Analytics의 사용자 지정 성공 이벤트와 연결되지 않습니다. 일부 표준 지표의 이름은 기존 Analytics에서 다음과 같이 변경되었습니다. 방문자 = 사람, 방문 횟수 = 세션, 히트 수 = 이벤트 |
| PDF 내보내기 | 전체 지원 |
| 프로젝트 큐레이션 | 전체 지원 |
| 프로젝트 연결 | 전체 지원 |
| 보고서 처리 시간 | 전체 지원 CJA는 보고서 처리 시간에만 사용합니다. |
| 보고 API 액세스 | 전체 지원 [CJA API](https://www.adobe.io/cja-apis/docs/)를 통해 사용할 수 있습니다. |
| 예약된 보고서/프로젝트 | 전체 지원 |
| 세그먼트 | 전체 지원 이제 &quot;필터&quot;라고 합니다. 기존 Analysis Workspace의 기존 세그먼트는 CJA로 포팅되지 않습니다. |
| 사용자 권한/데이터 액세스 제어 | 전체 지원 CJA는 [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=en) 제품 관리자와 사용자를 구별합니다. 제품 관리자만 다음 작업을 수행할 수 있습니다 <ul><li>연결 또는 데이터 보기 만들기/업데이트/삭제</li><li>다른 사용자가 만든 프로젝트, 필터 또는 계산 지표 업데이트/삭제하기</li><li>모든 사용자에게 Workspace 프로젝트 공유.</li></ul> |
| 가상 보고서 세트 | 전체 지원 이제 [데이터 보기](/help/data-views/create-dataview.md)라고 합니다. |
| VRS 구성 요소 큐레이션 | 전체 지원 이제 데이터 보기의 일부입니다. |

## 경고가 지원됨

| 기능 | 참고 |
| --- | --- |
| A4T | 지원은 [Adobe Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en)의 필드를 통해 제공됩니다. |
| 분류 | 이제 &quot;조회 데이터 세트&quot;라고 합니다. Analytics에서 사용되는 분류는 Analytics 분류 데이터 커넥터를 사용하여 Experience Platform 및 CJA로 가져올 수 있습니다. 조회 데이터 세트를 AEP에 직접 업로드하여 CJA에서 사용할 수도 있습니다. |
| 사용자 지정 세션 | 모바일 배경 조회 수를 제외한 모든 사용자 지정 세션 기능을 지원합니다. |
| 사용자 특성 | 이제 &quot;프로필 데이터 세트&quot;라고 하며, Experience Cloud에서 자동으로 가져오지 않습니다. CJA에서 사용하려면 AEP로 업로드해야 합니다. |
| 데이터 범위 | 계획된 사용자 지정 달력 지원을 제외하고 모든 날짜 범위 기능이 지원됩니다. |
| 디바이스, 브라우저, 기술 차원 | 이러한 차원은 AEP 데이터 세트에 특정 XDM 스키마 필드가 포함되고 XDM 경험 이벤트 클래스를 준수하는 경우에 자동으로 포함됩니다. |
| 시작, 종료, 체류 시간 차원 및 지표 | 지원되며(시작 및 종료는 이제 세션 시작 및 세션 종료라고 함)이제 약간 다른 방식으로 계산됩니다. |
| eVar 지속성 설정 | eVar는 더 이상 CJA에 포함되지 않습니다. 하지만 지속성 설정은 이제 데이터 보기에 속하고, 모든 차원에서 사용할 수 있습니다. 지속성은 데이터 수집 처리 시간이 아니라, 보고서 처리 시간을 기반으로 한다는 점을 명심하십시오. 데이터 보기 내에서 설정된 차원은 최대 90일로 지속성이 제한되며 무제한 지속성을 지원하지 않습니다. |
| 지리 특성 차원 | Adobe Analytics에 수집된 모든 지리 특성/지리적 위치는 분석 데이터 커넥터를 통해 CJA로 전송됩니다. 디지털 데이터 수집에 AEP Web SDK를 사용하는 구현과 같이 Analytics Data Connector를 사용하지 않는 구현에서는 자동으로 지리적 조회 기능을 전체 슬레이트로 사용할 수 없습니다(국가와 주가 지원되며, 도시 및 zip은 지원되지 않음). |
| 마케팅 채널 | 마케팅 채널 데이터가 Analytics Data Connector를 통해 CJA로 전송됩니다. 마케팅 채널 규칙은 계속 기존의 Adobe Analytics에서 구성해야 합니다. 일부 규칙은 지원되지 않습니다. 자세한 내용은 [CJA 마케팅 채널 설명서](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=ko#cja-usecases)를 참조하십시오. |
| 제품 변수 | Experience Platform 내에서 사용자는 데이터 세트 스키마 내의 개체 유형 필드 배열을 사용하여 이 사용 사례를 충족할 수 있습니다. CJA 내에서 고객은 다양한 제품 변수를 사용할 수 있으며 Adobe Analytics에서처럼 단일 변수로 제한되지 않습니다. |
| 프로젝트 공유 | 프로젝트 공유는 CJA 사용자 사이에서만 지원됩니다. CJA와 기존 Analysis Workspace 간에 프로젝트를 공유할 수 없습니다. |
| 시각화 | 맵 시각화를 제외한 모든 시각화가 지원됩니다. |

## 부분 지원

| 기능 | 참고 |
| --- | --- |
| 보트 필터링 | ADC(Analytics Data Connector) 기반 데이터 세트의 경우 보트 필터링이 적용됩니다. 다른 데이터 세트에 대한 일반 보트 필터링 논리 기능은 [!UICONTROL Experience Platform] 또는 CJA에서 사용할 수 없습니다. |
| Media Analytics | 미디어 데이터는 Analytics Data Connector의 일부로 사용할 수 있습니다. |
| 머천다이징 eVars | 머천다이징 eVar가 지속성을 사용하도록 설정되지 않은 경우 개체 배열 내의 차원을 사용하여 머천다이징 eVar의 동작을 달성할 수 있습니다. 현재 머천다이징 차원 지속성을 사용할 수 없습니다. |
| 패널 | 빈 패널, 기여도 분석 패널, 자유 형식 패널 및 빠른 인사이트가 완벽하게 지원됩니다. 세그먼트 비교, Analytics for Target(A4T) 및 미디어 동시 뷰어 패널은 지원되지 않습니다. |
| 처리 규칙 | Analytics Data Connector 기반 데이터 세트의 경우 처리 규칙이 여전히 적용됩니다. [Adobe Experience Platform의 데이터 ](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) 준비 기능은 Platform으로 직접 이동하는 데이터의 처리 규칙을 대체용으로 사용할 수도 있습니다. |

## 현재는 지원되지 않지만, 지원 예정

| 기능 | 참고 |
| --- | --- |
| 경고 | 지원이 예정되어 있습니다. |
| 기여도 분석 | 지원이 예정되어 있습니다. |
| CSV 다운로드 | 지원이 예정되어 있습니다. |
| 사용자 지정 달력 | 지원이 예정되어 있습니다. |
| 데이터 웨어하우스 보고 (100% 행 내보내기) | Analysis Workspace 인터페이스에서 지원이 예정되어 있습니다. [!UICONTROL Experience Platform Query Service] 또한 CJA에서의 이러한 사용 사례에 대한 인터페이스를 제공합니다. |
| 디바이스 그래프를 통한 ID 결합 | 지원이 예정되어 있습니다. |
| 지표 중복 제거 | 지원이 예정되어 있습니다. |
| 머천다이징 변수 지속성 | 지원이 예정되어 있습니다. |
| 실시간 보고 | 지원이 예정되어 있습니다. |
| Report Builder(Excel 플러그인) | 지원이 예정되어 있습니다. |
| 세그먼트 IQ | 지원이 예정되어 있습니다. |
| 세그먼트 게시(Analysis Workspace에서 Experience Cloud로 세그먼트 전송) | 지원이 예정되어 있습니다. |

## 지원이 아직 예정되지 않았습니다.

| 기능 | 참고 |
| --- | --- |
| Activity Map | 지원이 아직 예정되지 않음 |
| Advertising Cloud | 지원이 아직 예정되지 않음 |
| 분류 규칙 빌더 | 지원이 아직 예정되지 않음 |
| 데이터 피드 | 지원이 아직 예정되지 않음 |
| 요약 데이터 소스 | 지원이 아직 예정되지 않음 |

## 지원 예정 없음

* 크로스 디바이스 조합을 사용하는 사용자 메트릭
* Reports &amp; Analytics 대시보드
* Reports &amp; Analytics 책갈피
* Reports &amp; Analytics 대상
* Reports &amp; Analytics 달력 이벤트
* 모바일 서비스
