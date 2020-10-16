---
title: Customer Journey Analytics 기능 지원
description: Customer Journey Analytics 기능과 Adobe Analytics 기능 세트를 비교한 것입니다.
translation-type: ht
source-git-commit: b0b8d62eaa7ca539b04677c308fbb33345e110fe
workflow-type: ht
source-wordcount: '890'
ht-degree: 100%

---


# Customer Journey Analytics 기능 지원

다음 표는 CJA(Customer Journey Analytics)에서 지원되거나, 부분적으로 지원되거나, 지원되지 않는 Adobe Analytics의 기능을 보여줍니다. 이러한 기능은 CJA에 추가되므로 시간이 지남에 따라 위의 표가 변경됩니다.

## 완전히 지원되는 기능/구성 요소

| 기능 | 참고 |
| --- | --- |
| 지표 | CJA는 XDM(Experience Data Model)을 활용하고 무제한 지표를 지원하며, 기존 Analytics의 사용자 지정 성공 이벤트와 연결되지 않습니다. 일부 표준 지표의 이름은 기존 Analytics에서 다음과 같이 변경되었습니다. 방문자 = 사람, 방문 횟수 = 세션, 히트 수 = 이벤트. |
| 차원 | CJA는 XDM을 활용하고 무제한 차원을 지원하며, 기존 Analytics의 사용자 지정 성공 이벤트와 연결되지 않습니다. |
| 목록 변수/목록 속성 | CJA는 XDM을 활용하고 무제한 목록 변수를 지원합니다. |
| 데이터 범위 | 사용자 지정 달력 지원이 예정되어 있습니다. |
| 계산된 지표 | 기존 Analysis Workspace의 기존 계산 지표가 CJA에 포팅되지 않습니다. |
| 세그먼트 | 이제 &quot;필터&quot;라고 합니다. 기존 Analysis Workspace의 기존 세그먼트는 CJA로 포팅되지 않습니다. |
| 예외 항목 탐지 | 모든 지원 |
| 기여도 분석 IQ | 전체 지원 |
| 프로젝트 큐레이션 | 전체 지원 |
| 프로젝트 연결 | 전체 지원 |
| 날짜 비교 | 전체 지원 |
| 가상 보고서 세트 | 이제 [데이터 보기](/help/data-views/create-dataview.md)라고 합니다. |
| VRS 구성 요소 큐레이션 | 이제 데이터 보기의 일부입니다. |
| 보고서 처리 시간 | CJA는 보고서 처리 시간에만 사용합니다. |
| GDPR 삭제 | 이제 [!UICONTROL Experience Platform]에 GDPR이 적용되면서 CJA에서 [!UICONTROL Experience Platform]의 기본 데이터 세트에 변경된 모든 데이터 변경 사항을 이어받습니다. |
| 사용자 권한/데이터 액세스 제어 | CJA는 Adobe Admin Console 제품 관리자와 사용자를 구별합니다. 제품 관리자만 1) 연결 또는 데이터 보기 생성/업데이트/삭제하고, 2) 다른 사용자가 만든 프로젝트, 필터 또는 계산 지표를 업데이트/삭제하고, 3) Analysis Workspace 프로젝트를 모든 사용자에게 공유할 수 있습니다 |

## 경고가 지원됨

| 기능 | 참고 |
| --- | --- |
| 제품 변수 | 제품 변수는 현재 경험 이벤트 스키마(구체적으로 productListItems 개체 사용)를 따르는 데이터에 대한 보고에 사용할 수 있습니다. |
| 시각화 | 맵 시각화를 제외한 모든 시각화가 지원됩니다. |
| AAM 대상 | 고객이 [!UICONTROL Analytics 데이터 커넥터] 데이터 세트를 사용 중인 경우 이 데이터는 ADC 데이터에 포함됩니다. |
| 프로젝트 공유 | 프로젝트 공유는 CJA 사용자 사이에서만 지원됩니다. CJA와 기존 Analysis Workspace 간에 프로젝트를 공유할 수 없습니다. |
| 사용자 지정 세션 | 모바일 배경 조회 수를 제외한 모든 사용자 지정 세션 기능을 지원합니다. |
| eVar 지속성 설정 | eVar는 더 이상 CJA에 포함되지 않습니다. 하지만 지속성 설정은 이제 데이터 보기에 속하고, 모든 차원에서 사용할 수 있습니다. 지속성은 데이터 수집 처리 시간이 아니라, 보고서 처리 시간을 기반으로 한다는 점을 명심하십시오. 즉, 모든 지속성은 데이터 전체가 아니라 보고 날짜 범위를 기반으로 합니다. |
| 분류 | 이제 &quot;조회 데이터 세트&quot;라고 하며, 기존 Analytics에서 자동으로 가져오지 않습니다. CJA에서 사용하려면 AEP로 업로드해야 합니다. |
| 사용자 특성 | 이제 &quot;프로필 데이터 세트&quot;라고 하며, Experience Cloud에서 자동으로 가져오지 않습니다. CJA에서 사용하려면 AEP로 업로드해야 합니다. |

## 부분 지원

| 기능 | 참고 |
| --- | --- |
| 즉시 사용 가능한 Analysis Workspace 차원(예: 브라우저 유형, 레퍼러 유형, 마케팅 채널, 방문 횟수 등) | CJA는 기본적으로 이러한 차원을 제공하지 않습니다. ADC(Analytics Data Connector)를 사용하는 고객의 경우 이러한 차원 중 일부를 사용할 수 있지만 모두 사용할 수는 없습니다. [ADC를 통해 지원되는 Analytics 변수에 대한 설명서](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)를 참조하십시오. |
| 패널 | 빈 패널, 기여도 분석 패널, 자유 형식 패널 및 빠른 인사이트가 완벽하게 지원됩니다. 세그먼트 비교, Analytics for Target(A4T) 및 미디어 동시 뷰어 패널은 지원되지 않습니다. |
| 머천다이징 eVars | 머천다이징 eVar는 동일한 XDM 스키마(위의 제품 목록 제한 사항과 유사)를 엄격하게 따르지 않는 경우 ADC 기반 데이터 세트에서만 작동합니다. |
| 보트 필터링 | ADC(Analytics Data Connector) 기반 데이터 세트의 경우 보트 필터링이 적용됩니다. 다른 데이터 세트에 대한 일반 보트 필터링 논리 기능은 [!UICONTROL Experience Platform] 또는 CJA에서 사용할 수 없습니다. |
| 처리 규칙 | ADC 기반 데이터 세트의 경우 처리 규칙이 계속 적용됩니다. |
| 교차 장치 ID 결합 | 고객은 Query Service를 통한 데이터 결합을 &quot;1회&quot;만 할 수 있습니다. 또는 현재 이 논리를 데이터에 적용한 후에 [!UICONTROL Experience Platform] 데이터를 수집해야 합니다. |

## 현재는 지원되지 않지만, 지원 예정

| 기능 | 참고 |
| --- | --- |
| 기여도 분석 | 지원이 예정되어 있습니다. |
| 세그먼트 IQ | 지원이 예정되어 있습니다. |
| 세그먼트 게시(Analysis Workspace에서 Experience Cloud로 세그먼트 전송) | 지원이 예정되어 있습니다. |
| CSV 다운로드 | 지원이 예정되어 있습니다. |
| 예약된 보고서/프로젝트 | 지원이 예정되어 있습니다. |
| 경고 | 지원이 예정되어 있습니다. |
| 사용자 지정 달력 | 지원이 예정되어 있습니다. |
| 마케팅 채널 | 지원이 예정되어 있습니다. |
| PDF 내보내기 | 지원이 예정되어 있습니다. |
| 보고 API 액세스 | 지원이 예정되어 있습니다. API 2.0에서만 사용할 수 있습니다. |
| 장치 그래프를 통한 ID 결합 | 지원이 예정되어 있습니다. |

## 지원이 아직 예정되지 않았습니다.

| 기능 | 참고 |
| --- | --- |
| A4T | 지원이 아직 예정되지 않았습니다. |
| Media Analytics | 지원이 아직 예정되지 않았습니다. |
| Advertising Cloud | 지원이 아직 예정되지 않았습니다. |
| Report Builder(Excel 플러그인) | 지원이 아직 예정되지 않았습니다. |
| Activity Map | 지원이 아직 예정되지 않았습니다. |
| 분류 규칙 빌더 | 지원이 아직 예정되지 않았습니다. |
| 요약 데이터 소스 | 지원이 아직 예정되지 않았습니다. |
| 실시간 보고 | 지원이 아직 예정되지 않았습니다. |

## 지원 예정이 없습니다.

* 교차 장치 조합을 사용하는 사람 지표
* Reports &amp; Analytics 대시보드
* Reports &amp; Analytics 책갈피
* Reports &amp; Analytics 대상
* Reports &amp; Analytics 달력 이벤트
* Ad Hoc Analysis
* Data Warehouse 보고 - [!UICONTROL Experience Platform 쿼리 서비스]는 CJA의 이러한 사용 사례를 위한 새로운 인터페이스입니다.
* Mobile Services
* 데이터 피드
