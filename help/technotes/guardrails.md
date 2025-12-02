---
title: Customer Journey Analytics 가드 레일
description: Customer Journey Analytics의 보호 기능에 대해 알아보기
solution: Customer Journey Analytics
feature: Administration
role: Admin
exl-id: f093ac54-7d31-449b-a441-a65856a1d535
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '2087'
ht-degree: 7%

---

# Customer Journey Analytics 가드 레일

이 문서에서는 Customer Journey Analytics의 다양한 구성 요소에 대한 제한을 제공합니다. 보호, 범위 매개 변수 및 사용 권한에 대해서는 [Customer Journey Analytics의 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/customer-journey-analytics.html), [Adobe Analytics 추가 기능의 제품 설명: Customer Journey Analytics](https://helpx.adobe.com/kr/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html) 또는 [Customer Journey Analytics B2B edition의 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/customer-journey-analytics-b2b.html)을 참조하세요.

## 제한 유형

이 문서에는 두 가지 유형의 기본 제한이 있습니다.

| 보호 유형 | 설명 |
|----------|---------|
| **성능 보호 기능(소프트 제한)** | 성능 보호는 사용 사례의 범위와 관련된 사용 제한입니다. 성능 가드레일을 초과하면 성능 저하 및 지연이 발생할 수 있습니다. Adobe은 이러한 성능 저하에 대한 책임이 없습니다. 성능 가드레일을 지속적으로 초과하는 고객은 성능 저하를 방지하기 위해 추가 용량의 라이센스를 선택할 수 있습니다. |
| **시스템 적용 보호 기능(하드 제한)** | 시스템에서 적용되는 가드레일은 Customer Journey Analytics UI 또는 API에 의해 적용됩니다. UI 및 API에서 이를 차단하거나 오류를 반환하므로 이를 초과할 수 없는 제한입니다. |

{style="table-layout:auto"}

기능 중 일부 및 기능 제한과 관련된 값은 권한이 부여된 Customer Journey Analytics 패키지에 따라 다릅니다.

>[!NOTE]
>
>이 문서에 설명된 값은 제품의 지속적인 개선에 따라 변경될 수 있습니다. 정기적으로 업데이트를 확인하십시오. 사용자 지정 제한에 대해 알아보려면 고객 지원 센터에 문의하십시오.

## 임시 SQL 쿼리

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 다시 시도 시간 초과 | 90 | 시스템 강제 보호 | 다른 동시 요청으로 인해 요청 결과가 반환되기까지 요청이 너무 오래 소요될 수 있으며 다시 요청할 수 있는 경우 보고 엔진이 응답하기까지의 최대 시간(초)입니다. |
| 다시 시도 안 함 시간 초과 | 600 | 시스템 강제 보호 | Ad Hoc SQL 쿼리가 시간 초과되기 전의 최대 시간(초)입니다. 달리 말하면, 요청이 결과를 반환하는데 너무 오래 걸려 다시 시도해서는 안 된다고 보고 엔진이 보고하기 전의 최대 시간(초)입니다. 백그라운드 프로세스의 문제로 인해 요청이 결과를 반환하지 않을 가능성이 높습니다. |
| 지표 | 150 | 시스템 강제 보호 | 요청의 최대 지표 수입니다. |
| 대화형 쿼리 출력 행 | 50,000 | 시스템 강제 보호 | 달리 지정하지 않는 한 반환되는 기본 행 수입니다. |

{style="table-layout:auto"}

## Analysis Workspace 프로젝트

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 표당 표시 행 수 | 400 | 시스템 강제 보호 | Analysis Workspace 프로젝트의 자유 형식 테이블에 표시되는 최대 행 수입니다. |
| 테이블당 내보낼 수 있는 행 | 50,000 | 시스템 강제 보호 | 단일 차원당 내보낼 수 있는 최대 행 수. |
| 프로젝트당 패널 | 15 | 시스템 강제 보호 | 프로젝트당 최대 [패널](../analysis-workspace/home.md#panels) 수. |
| 패널당 시각화 | 25 | 시스템 강제 보호 | 패널당 최대 [시각화](../analysis-workspace/home.md#visualizations) 수. |
| 자유 형식 테이블당 파생 필드 | 5 | 시스템 강제 보호 | 단일 자유 형식 테이블에 있는 다양한 파생 필드의 최대 수입니다. |
| 프로젝트당 댓글 | 1,000 | 시스템 강제 보호 | 프로젝트당 최대 댓글 수. |
| 프로젝트당 댓글 | 1,000 | 시스템 강제 보호 | 프로젝트당 최대 댓글 수. |
| 댓글당 답글 수 | 100 | 시스템 강제 보호 | 댓글당 최대 회신 수. |
| 댓글당 이미지 수 | 5 | 시스템 강제 보호 | 댓글당 최대 이미지 수. |
| 이미지 크기 | 2 | 시스템 강제 보호 | 이미지당 최대 업로드 크기(MB)입니다. |
| 댓글당 답글 수 | 100 | 시스템 강제 보호 | 댓글당 최대 회신 수. |
| 댓글당 이미지 수 | 5 | 시스템 강제 보호 | 댓글당 최대 이미지 수. |
| 이미지 크기 | 2 | 시스템 강제 보호 | 이미지당 최대 업로드 크기(MB) |

{style="table-layout:auto"}


<!-- at flatview GA, add: - Dimension columns per freeform table - 5 - System-enforced Guardrail - Maximum number of dimensions per freeform table. -->

<!--

## Attribution AI

| Name |  Value | Description | PD? |
|---|--:|---|:---:|
| Attribution AI models | 35 | Maximum number of Attribution AI Model per year to analyze the impact of up to an average of 60 independent touchpoints on a specified conversion event.  | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Region based iterations | 10 | Maximum number of region-based iterations of each Attribution AI model. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg)  |
| Export Insights batches | 12 | Maximum number of export batches times the number of authorized Attribution AI Insights per year. | ![check](https://spectrum.adobe.com/static/icons/ui_18/CheckmarkSize100.svg) |

-->

## 대상자

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 대상 세그먼트 | 20 | 시스템 강제 보호 | 대상당 최대 [세그먼트](../components/segments/seg-overview.md) 수. |
| 대상자 ID 수 | 2,000만 | 시스템 강제 보호 | 대상자당 최대 ID 수. |
| 대상 새로 고침 빈도 | 4 | 시스템 강제 보호 | [대상](../components/audiences/audiences-overview.md)의 최대 빈도를 시간 단위로 새로 고칠 수 있습니다. |
| 대상자 새로 고침 전환 확인 기간 | 90 | 시스템 강제 보호 | 전환 확인 기간 새로 고침의 최대 일 수. |
| 대상자 만료일 새로 고침 | 13 | 시스템 강제 보호 | 대상자가 생성된 날짜부터 새로 고침이 중단되는 최대 기간(월)입니다. 고객은 이 기간을 13개월 더 연장할 수 있습니다. |
| 새로 고치는 대상 수 | 75,150 | 시스템 강제 보호 | 새로 고치는 최대 대상자 수. 값은 Customer Journey Analytics 패키지에 따라 다릅니다(제품 설명 참조). |

{style="table-layout:auto"}

Experience Platform [실시간 고객 데이터 플랫폼 보호](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/guardrails/overview)도 참조하세요.


## 자동화된 데이터 세트 만료

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|:---:|
| 작업 주문 | 20 | 시스템 강제 보호 | 월별 자동화된 데이터 세트 만료 작업 주문의 최대 수입니다. |

{style="table-layout:auto"}



## 연결, 데이터 보기, 프로젝트

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 프로젝트 | 50,000 | 시스템 강제 보호 | 조직의 최대 프로젝트 수. |
| 데이터 보기 | 2,000 | 시스템 강제 보호 | 조직의 최대 [데이터 보기](../data-views/data-views.md) 수입니다. |
| 데이터 보기 | 500-1000 | 시스템 강제 보호 | 연결에 대한 최대 데이터 보기 수. 값은 Customer Journey Analytics 패키지에 따라 다릅니다(제품 설명 참조). |
| 데이터 세트 | 100 | 시스템 강제 보호 | 연결당 최대 [데이터 세트 수](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html). |
| 연결 | 1000년 | 시스템 강제 보호 | 조직의 최대 [연결](../connections/overview.md) 수입니다. |
| 연결 제목 | 500 | 시스템 강제 보호 | 연결 제목의 최대 문자 수입니다. |
| 지표 | 5,000 | 시스템 강제 보호 | 데이터 보기의 최대 지표 수입니다. |
| 차원 | 5,000 | 시스템 강제 보호 | 데이터 보기의 최대 차원 수입니다. |
| 주석 제목 | 100 | 시스템 강제 보호 | 주석 제목의 최대 문자 수입니다. |
| 주석 설명 | 250 | 시스템 강제 보호 | 주석 설명의 최대 문자 수. |
| 스키마 필드 | 10 | 시스템 강제 보호 | [파생 필드](../data-views/derived-fields/derived-fields.md)에 대한 규칙을 정의할 때 표준 필드를 포함하지 않는 최대 스키마 필드 수입니다. |
| 조회/프로필 필드 | 3 | 시스템 강제 보호 | 파생된 필드에 대한 규칙을 정의할 때 최대 스키마 필드 수 내의 최대 조회 또는 프로필 스키마 필드 수(표준 필드 제외). |
| 파생 필드 | 100 - 500 | 시스템 강제 보호 | 연결당 최대 파생 필드 수. 값은 Customer Journey Analytics 패키지에 따라 다릅니다(제품 설명 참조). |

{style="table-layout:auto"}


## 데이터 전송 제한

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 필드 | 10,000 | 시스템 강제 보호 | 데이터 세트의 행당 최대 속성 또는 필드 수. |
| 고유 문자열 | 1,000만 ~ 10억 | 시스템 강제 보호 | 조회 데이터 세트당 최대 고유 키 수. Customer Journey Analytics 패키지에 따라 다릅니다(제품 설명 참조).<ul><li>재단: 천만.</li><li>선택: 1억</li><li>Prime: 5억.</li><li>Ultimate: 10억</li><ul> |
| 사용자당 행 수 | 100만 | 시스템 강제 보호 | 연결 내 지정된 달에 고유 개인 ID당 최대 행 수. |
| 일별 행 | 25억 | 성능 보호 | 연결의 일일 최대 평균 행 수입니다. |
| 행 크기 | 2 | 성능 보호/시스템 적용 보호 | Customer Journey Analytics에 수집된 데이터 행당 평균 크기(KB)(소프트 제한). 행 크기에 대한 정적 제한은 Experience Platform에서 데이터 수집을 위한 가드레일에 의해 결정됩니다. |

{style="table-layout:auto"}

Experience Platform [데이터 수집을 위한 보호 기능](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html)도 참조하세요.


## 대상 데이터 내보내기

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 데이터 내보내기 | 인증된 총 데이터 레이크 스토리지 | 성능 보호 | 고객은 대상 데이터 세트 내보내기 를 사용하여 데이터 레이크에서 인증된 총 데이터 레이크 저장소까지 고객 데이터를 내보낼 수 있습니다. |
| 사용 가능한 데이터 세트 | 프로필 및 이벤트 | 시스템 강제 보호 | 소스, Web SDK, Mobile SDK, Analytics Data Connector 및 Audience Manager을 통해 데이터를 수집하거나 수집한 후 Experience Platform UI에서 생성된 이벤트, 프로필 또는 조회 데이터 세트입니다. |

{style="table-layout:auto"}

Experience Platform [데이터 집합 내보내기 보호](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/guardrails#dataset-exports)도 참조하세요.


## 데이터 랜딩 영역

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 샌드박스당 데이터 랜딩 영역 | 1 | 시스템 강제 보호 | 샌드박스당 최대 데이터 랜딩 영역 수. |
| 데이터 저장소 | 7 | 시스템 강제 보호 | 삭제되기 전에 데이터 랜딩 영역에 저장되는 최대 일 수입니다. |

{style="table-layout:auto"}


## 필드 기반 결합

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 결합된 데이터 세트 | 5 - 50 | 시스템 강제 보호 | 고객당 결합된 최대 데이터 세트 수. 값은 Customer Journey Analytics 패키지에 따라 다릅니다(제품 설명 참조). |
| 채우기 길이 | 6 - 25 | 시스템 강제 보호 | 데이터 채우기의 최대 개월 수. 값은 Customer Journey Analytics 패키지에 따라 다릅니다(제품 설명 참조). |
| 전환 확인 기간/재생 빈도 | 1/1 - 30/7 | 시스템 강제 보호 | 최대 전환 확인 기간(일) / 재생 빈도. 값은 Customer Journey Analytics 패키지에 따라 다릅니다(제품 설명 참조). |

{style="table-layout:auto"}


## 그래프 기반 결합

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 결합된 데이터 세트 | 15 - 50 | 시스템 강제 보호 | 고객당 결합된 최대 데이터 세트 수. 값은 Customer Journey Analytics 패키지에 따라 다릅니다(제품 설명 참조). |
| 채우기 길이 | 6 - 25 | 시스템 강제 보호 | 데이터 채우기의 최대 개월 수. 값은 Customer Journey Analytics 패키지에 따라 다릅니다(제품 설명 참조). |
| 전환 확인 기간/재생 빈도 | 1/1 - 30/7 | 시스템 강제 보호 | 최대 전환 확인 기간(일) / 재생 빈도. 값은 Customer Journey Analytics 패키지에 따라 다릅니다(제품 설명 참조). |


## 세그먼트 및 계산된 지표

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 세그먼트당 컨테이너 | 50 | 시스템 강제 보호 | 세그먼트당 최대 컨테이너 수. |
| 계산된 지표당 지표 | 25 | 시스템 강제 보호 | 계산된 지표당 최대 지표 수. |
| 세그먼트당 지표 및 차원 | 25 | 시스템 강제 보호 | 세그먼트당 고유한 최대 지표 및 차원 수. |
| 세그먼트당 중첩된 컨테이너 | 10 | 시스템 강제 보호 | 세그먼트당 최대 중첩 컨테이너 수. |
| 세그먼트당 규칙 | 100 | 시스템 강제 보호 | 세그먼트당 최대 규칙 수. |
| 세그먼트당 Dimension당 문자열 비교 | 100 | 시스템 강제 보호 | 세그먼트당 차원당 최대 문자열 비교 수. |
| 계산된 지표 | 6,000 | 시스템 강제 보호 | 조직의 최대 계산된 지표 수입니다. |
| 세그먼트 | 50,000 | 시스템 강제 보호 | 조직에 대해 정의할 수 있는 최대 세그먼트 수입니다. |
| API 호출 | 120 | 시스템 강제 보호 | 분당 API 요청(6초마다 12개 요청). |

{style="table-layout:auto"}


## 모바일 애플리케이션

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 타일 | 16 | 시스템 강제 보호 | 스코어카드당 최대 타일 수. |
| 세그먼트 | 10 | 시스템 강제 보호 | 스코어카드당 최대 세그먼트 수. |
| 차원 | 10 | 시스템 강제 보호 | 스코어카드당 최대 차원 수. |

{style="table-layout:auto"}

## Report Builder

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 통합 문서 파일 크기 | 5 | 시스템 강제 보호 | 예약된 통합 문서의 최대 파일 크기(MB)입니다. |
| 데이터 블록 | 1000 | 시스템 강제 보호 | 통합 문서당 최대 [데이터 블록 수](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/manage-reportbuilder.html). |
| 지표 | 20 | 시스템 강제 보호 | 데이터 블록당 최대 지표 수. |
| 날짜 범위 범위 | 13 | 시스템 강제 보호 | 데이터 블록당 날짜 범위가 적용될 수 있는 최대 개월 수입니다. |
| 다른 결과를 표시했던 | 50,000 | 시스템 강제 보호 | 데이터 블록당 최대 행 수. |

{style="table-layout:auto"}


## 전체 테이블 내보내기

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 보고서당 행 수 | 300만~3억 | 시스템 강제 보호 | 보고서당 최대 보고 행 수. 값은 Customer Journey Analytics 패키지에 따라 다릅니다(제품 설명 참조). |
| 테이블당 분류 | 5 | 시스템 강제 보호 | 테이블당 최대 분류 수. |
| 테이블당 지표 | 5 | 시스템 강제 보호 | 테이블당 최대 지표 수. |
| 일정 빈도 | 1 | 시스템 강제 보호 | 내보내기는 하루에 한 번 또는 더 긴 일정으로 예약할 수 있습니다(예: 2일에 한 번 또는 매주). |

{style="table-layout:auto"}


## 공유 지표 및 공유 차원

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 공유 라이브러리 | 1 | 시스템 강제 보호 | 연결에 대한 최대 공유 라이브러리 수. |
| 공유 지표 | 10,000 | 시스템 강제 보호 | 공유 라이브러리당 최대 공유 지표 수입니다. |
| 공유 차원 | 10,000 | 시스템 강제 보호 | 공유 라이브러리당 최대 공유 차원 수입니다. |

{style="table-layout:auto"}


## Data Insights 에이전트

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| 데이터 보기 | 50 | 시스템 강제 보호 | Data Insights Agent에 대해 활성화할 수 있는 최대 데이터 보기 수입니다. 더 많은 데이터 보기가 활성화되면 Data Insights Agent에서는 가장 많이 사용된 데이터 보기만 사용할 수 있습니다. 이 가드레일은 연결 또는 조직 내에서 정의할 수 있는 최대 데이터 보기 수를 정의하는 [가드레일에 영향을 주지 않습니다](#connections-data-views-projects). |


## Customer Journey Analytics B2B Edition

| 이름 | 값 | 제한 유형 | 설명 |
|---|--:|---|---|
| BPP(보고 가능한 사업가 프로필) 보고 가능한 행 | 100만 | 성능 보호 | 1000개의 보고 가능한 비즈니스 사용자 프로필당 평균 보고 가능한 행입니다. |




## 지연

>[!NOTE]
>
>아래의 처리 시간은 계약상의 SLA(서비스 수준 계약)가 아닌 보호입니다. 지연 시간은 고객 구성, 데이터 볼륨 및 소비자 애플리케이션에 따라 다릅니다. 실제 처리 시간이 더 빠른 경우가 많습니다. 구체적인 계약 조건 및 SLA는 Customer Journey Analytics 계약을 참조하십시오. 자세한 내용은 Experience Platform [데이터 수집을 위한 보호](https://experienceleague.adobe.com/docs/experience-platform/ingestion/guardrails.html)를 참조하십시오.

| 데이터 흐름 | 예상 지연 시간 |
|---|---|
| Adobe Analytics to Adobe Analytics Source 커넥터(A4T 활성화됨) | 30분 미만 |
| Adobe Analytics Source Connector-to-Real-time Customer Profile(A4T가 활성화되지 않음) | 2분 미만 |
| Adobe Analytics Source Connector-to-Real-time Customer Profile(A4T 활성화됨) | 30분 미만 |
| Edge Network 또는 스트리밍 수집에서 데이터 레이크로 데이터 수집 | 60분 미만 |
| Adobe Analytics Source 커넥터에서 데이터 레이크로 데이터 수집 | &lt; 2.25시간 |
| 데이터 레이크에서 Customer Journey Analytics으로 데이터 수집 | 90분 미만 |
| 결합(선택적 기능. 자세한 내용은 [결합 개요](../stitching/overview.md)를 참조하십시오.) | 4시간 미만 |
| 100억 개 미만의 이벤트(최대 13개월의 내역 데이터) Adobe Analytics Source 커넥터 채우기 | &lt; 4주 |
| 실시간 고객 프로필에 게시하는 대상(스트리밍 세그먼트의 자동 생성 및 세그먼트의 데이터 수신 준비 허용 포함). | ≈분 |
| 대상의 새로 고침 빈도 | 1회 새로 고침: 지연 시간은 5분 미만입니다.<br/>매일, 매주, 매월 4시간마다 새로 고칩니다. 지연 시간은 새로 고침 빈도와 비슷합니다. |

| 실시간 보고 대기 시간 | 예상 지연 시간 |
|---|---|
| Edge Network에 대한 Edge Network SDK/API | 7분 미만 |
| 스트리밍 커넥터 | &lt; 17분 |
| Adobe Analytics 소스 커넥터 | &lt; 17분 |
| 기타 소스 커넥터(배치 데이터 포함) | &lt; 25시간 |

{style="table-layout:auto"}
