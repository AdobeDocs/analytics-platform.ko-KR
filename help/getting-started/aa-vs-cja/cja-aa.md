---
title: Customer Journey Analytics 기능 지원
description: Customer Journey Analytics 기능과 Adobe Analytics 기능 세트를 비교한 것입니다.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '2053'
ht-degree: 37%

---

# Adobe Customer Journey Analytics 기능 지원

다음 표에는 Adobe Analytics에서 지원되거나, 부분적으로 지원되거나, Customer Journey Analytics에서 지원되지 않는 기능과, Adobe Analytics에서 지원되거나 사용할 수 없는 Customer Journey Analytics 기능이 나열되어 있습니다. 이러한 목록은 Customer Journey Analytics에 추가되므로 시간이 지남에 따라 변경됩니다.

## 완전히 지원되는 기능/구성 요소 {#full-support}

| Adobe Analytics 기능 | 지원 관련 참고 사항 |
| --- | --- |
| 예외 항목 탐지 | 전체 지원 |
| Attribution IQ | 전체 지원 |
| 계산된 지표 | 전체 지원. 기존 Analysis Workspace의 기존 계산된 지표는 Customer Journey Analytics으로 포팅되지 않습니다. |
| 달력 이벤트 | 전체 지원. 달력 이벤트가 [주석](/help/components/annotations/overview.md) 작업 영역. |
| CSV 다운로드 | 전체 지원 |
| 사용자 정의 달력 | 전체 지원 |
| 날짜 비교 | 전체 지원 |
| 날짜 범위 | 모든 날짜 범위 기능이 지원됩니다. |
| 차원 | 전체 지원. Customer Journey Analytics은 XDM을 사용하며 무제한 차원을 지원합니다. Customer Journey Analytics은 기존 Adobe Analytics의 사용자 지정 eVar 또는 속성에 연결되지 않습니다. |
| GDPR 삭제 | 전체 지원: 이제 [!UICONTROL Adobe Experience Platform]에 GDPR이 적용됩니다. Customer Journey Analytics은 데이터 변경 사항을 상속합니다 [!UICONTROL Experience Platform] 을 기본 데이터 세트에 생성합니다. |
| 상승도 및 신뢰도 보고 | [실험 패널](/help/analysis-workspace/c-panels/experimentation.md)을 통한 전체 지원 |
| 목록 변수/목록 속성 | 전체 지원. Customer Journey Analytics은 XDM을 사용하며 listVars와 유사하게 사용할 수 있는 무제한 문자열 배열을 지원합니다. |
| 머천다이징 eVar | [바인딩 차원 및 바인딩 지표](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)를 통한 전체 지원 |
| 지표 | 전체 지원: Customer Journey Analytics은 XDM(Experience Data Model)을 사용하며, 무제한 지표를 지원하며, Adobe Analytics의 사용자 지정 성공 이벤트에 연결되지 않습니다. 일부 표준 지표의 이름은 Adobe Analytics에서 다음과 같이 변경되었습니다. 방문자 = 사람, 방문 횟수 = 세션, 히트 수 = 이벤트 |
| 모바일 스코어카드/대시보드 | 전체 지원 |
| 패널 | 빈 패널, 기여도 분석 패널, 자유 형식 패널 및 빠른 인사이트가 완벽하게 지원됩니다. |
| PDF 내보내기 | 전체 지원 |
| 프로젝트 큐레이션 | 전체 지원 |
| 프로젝트 연결 | 전체 지원 |
| 보고서 처리 시간 | 전체 지원: Customer Journey Analytics은 보고서 처리 시간에만 사용합니다. |
| 보고 API 액세스 | 전체 지원: [CUSTOMER JOURNEY ANALYTICS API](https://developer.adobe.com/cja-apis/docs/). |
| 예약된 보고서/프로젝트 | 전체 지원 |
| 세그먼트 | 전체 지원. 이제 &quot;필터&quot;라고 합니다. 기존 Analysis Workspace의 기존 세그먼트는 Customer Journey Analytics으로 포팅되지 않습니다. |
| 가상 보고서 세트 | 전체 지원. 지금 호출됨 [데이터 보기](/help/data-views/create-dataview.md). |
| 가상 보고서 세트 구성 요소 큐레이션 | 전체 지원. 이제 데이터 보기의 일부입니다. |
| 스트리밍 Media Analytics | 미디어 데이터는 Analytics 소스 커넥터를 미디어 동시 뷰어 패널 및 작업 영역의 미디어 재생 소요 시간 패널의 일부로 사용할 수 있습니다. |

{style="table-layout:auto"}

## 새로운 방식으로 지원됨 {#new-support}

| 기능 | 참고 |
| --- | --- |
| 대상자 게시 (세그먼트 퍼블리싱) | Adobe의 Customer Data Platform 또는 Journey Optimizer 제품 라이선스가 부여된 경우 지원됩니다. [대상자 게시](/help/components/audiences/audiences-overview.md)는 Experience Platform의 실시간 고객 프로필로 대상자를 보냅니다. |
| 분류 | 이제 “조회 데이터 세트”라고 합니다. Analytics에서 사용되는 분류는 Analytics 분류 소스 커넥터를 사용하여 Experience Platform 및 Customer Journey Analytics으로 가져올 수 있습니다. 조회 데이터 세트를 Experience Platform에 직접 업로드하여 Customer Journey Analytics에서 사용할 수도 있습니다. |
| 분류 규칙 빌더 | 다음을 사용하여 지원됨 [하위 문자열](/help/data-views/component-settings/substring.md) Customer Journey Analytics. 조회 데이터 세트가 아니라 보고서 시간에 문자열 조작을 사용합니다. |
| 사용자 정의 세션 | 모바일 배경 이벤트를 제외한 모든 사용자 정의 세션 기능을 지원합니다. |
| 통화 전환 | 의 일부로 지원됨 [지표 구성 요소 서식 지정](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=en#currency) 데이터 보기에서 다음을 수행합니다. |
| 머천다이징 변수 지속성 | [바인딩 차원 및 바인딩 지표](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)를 통한 전체 지원 |
| 고객 속성 | Experience Cloud 이제 &quot;프로필 데이터 세트&quot;라고 하며, 프로필에서 자동으로 가져오지 않습니다. Customer Journey Analytics에서 사용하려면 Experience Platform에 업로드해야 합니다. |
| 데이터 피드 | 데이터 세트의 1세대 데이터 내보내기는 [Experience Platform 데이터 액세스 API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) 및 [Experience Platform 대상](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=en). 이러한 옵션은 Experience Platform 데이터 레이크로 수집되거나 수집된 모든 데이터의 이벤트/행 수준 내보내기를 제공합니다. 쿼리 시간에 사후 열이 계산되므로 사후 프로세스 데이터 열을 사용할 수 없습니다. 보고를 통해 이후 열의 내보내기를 사용할 수 있습니다. |
| 지표 중복 제거 | 이제 데이터 보기 내의 지표에 대해 구성됩니다. 지표 중복 제거는 데이터 세트, 데이터 보기 또는 연결 수준이 아닌 개인 또는 세션 수준에서 발생합니다. |
| 시작, 종료, 사용 시간 차원 및 지표 | 지원되며(시작 및 종료는 이제 세션 시작 및 세션 종료라고 함), 약간 다른 방식으로 계산됩니다. |
| eVar 지속성 설정 | eVar는 더 이상 Customer Journey Analytics의 일부가 아닙니다. 하지만 지속성 설정은 이제 데이터 보기에 속하고, 모든 차원에서 사용할 수 있습니다. 지속성은 데이터 수집 처리 시간이 아니라 보고서 처리 시간을 기반으로 한다는 점을 명심하십시오. 데이터 보기 내에 설정된 Dimension은 90일 최대 지속성으로 제한되며 무제한 지속성을 지원하지 않습니다. |
| IP 난독화 | Analytics 소스 커넥터를 사용하여 Adobe Analytics의 데이터를 Customer Journey Analytics으로 채우는 Customer Journey Analytics 고객의 경우: Adobe Analytics에 적용된 IP 난독화 설정이 Customer Journey Analytics 데이터로 흐릅니다. 필요에 따라 Adobe Analytics에서 이러한 설정을 제어할 수 있습니다.<p>Experience Platform Web SDK를 사용하여 데이터를 플랫폼에 채우고 Customer Journey Analytics을 직접 사용하는 Customer Journey Analytics 고객의 경우 플랫폼에서 데이터 수집을 위한 데이터 준비를 사용하여 회사의 요구 사항에 따라 IP 주소를 난독화하는 규칙을 구성할 수 있습니다. |
| 새 세션 보고와 반복 세션 보고 비교 | 이전에는 방문 수 차원을 사용하여 수행했습니다. 새 세션과 반복 세션은 [13개월 조회 기간](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=ko)으로 지원됩니다. |
| 제품 변수 | Experience Platform 내에서 사용자는 데이터 세트 스키마 내의 오브젝트 유형 필드 배열을 사용하여 이 사용 사례를 충족할 수 있습니다. Customer Journey Analytics 내에서 고객은 다양한 제품 변수를 사용할 수 있으며 Adobe Analytics에서와 같이 단일 변수로 제한되지 않습니다. |
| 프로젝트 공유 | 프로젝트 공유는 Customer Journey Analytics 사용자 사이에서만 지원됩니다. Customer Journey Analytics과 기존 Analysis Workspace 간에는 프로젝트 공유가 되지 않습니다. |
| 시각화 | 맵 시각화를 제외한 모든 시각화가 지원됩니다. |
| Report Builder (Excel 플러그인) | Excel용 새로운 Office 365 플러그인으로 지원됩니다. |
| 사용자 권한/데이터 액세스 제어 | Customer Journey Analytics은 다음을 구별합니다. [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=ko-KR) 제품 관리자, 제품 프로필 관리자 및 사용자. 제품 관리자만 다른 사용자가 만든 연결, 프로젝트, 필터 또는 계산된 지표를 생성/업데이트/삭제할 수 있으며, 제품 관리자와 제품 프로필 관리자는 데이터 보기를 편집할 수 있습니다. 계산된 지표, 필터 또는 주석 생성과 같은 작업에 추가적인 사용자 권한을 사용할 수 있습니다. |
| 처리 규칙, VISTA 규칙, 마케팅 채널 처리 규칙 | Web SDK 기반 데이터 세트와 Analytics 소스 커넥터의 데이터 모두에 대해 Adobe Experience Platform 데이터 준비 기능을 사용하여 지원됩니다. |
| 마케팅 채널 | Analytics 소스 커넥터를 사용하면 마케팅 채널 데이터가 해당 커넥터를 통해 Customer Journey Analytics으로 전송됩니다. 마케팅 채널 규칙은 기존 Adobe Analytics에서 구성되며 일부 규칙은 지원되지 않습니다. 자세한 내용은 다음을 참조하십시오. [Customer Journey Analytics 마케팅 채널 설명서](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html). <br/>WebSDK 구현의 경우 다음을 통해 보고서 시간 마케팅 채널 처리 규칙이 지원됩니다. [파생 필드](../../data-views/derived-fields/derived-fields.md). |

{style="table-layout:auto"}

## 부분 지원 {#partial}

| 기능 | 참고 |
| --- | --- |
| 크로스 디바이스/크로스 채널 결합 | ID 정보를 직접 포함하는 데이터 세트에 대해 지원됩니다(“필드 기반” 스티칭이라고도 함). 그래프 기반 스티칭은 아직 지원되지 않지만 향후 지원될 예정입니다. 다음을 참조하십시오 [결합](../../stitching/overview.md). |
| 보트 필터링 | 대상 [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR)데이터 세트 기반, 보트 필터링이 적용됩니다. 다른 데이터 세트에 대한 일반 보트 필터링 논리는 [!UICONTROL Experience Platform] 또는 Customer Journey Analytics. |
| 디바이스, 브라우저, 레퍼러, 기술 차원 | 지원 대상: [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR)기반 데이터 세트. 을(를) 참조하십시오 [adc를 통해 지원되는 Analytics 변수에 대한 설명서](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=ko).<p>Experience Platform 웹 SDK 데이터 수집을 사용하는 경우 디바이스 조회를 기반으로 하는 디바이스 및 차원이 현재 지원되지 않습니다. 향후 지원 계획이 있습니다. |
| 지리 특성 - 차원 | Adobe Analytics에 수집된 모든 지리 특성/지역은 를 통해 Customer Journey Analytics으로 전송됩니다. [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR). Analytics 소스 커넥터를 사용하지 않지만, 디지털 데이터 수집을 위해 Experience Platform Web SDK를 사용하는 구현에서는 [Experience Edge 지역 조회 서비스](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ko-KR). |
| 패널 | 빈 패널, 기여도 분석 패널, 자유 형식 패널 및 빠른 인사이트가 완벽하게 지원됩니다. 세그먼트 비교 및 A4T(타겟 분석) 패널은 지원되지 않습니다. |
| 처리 규칙 | Analytics 소스 커넥터 기반 데이터 세트의 경우 처리 규칙이 여전히 적용됩니다. [Adobe Experience Platform의 데이터 준비 기능](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ko-KR)을 플랫폼으로 직접 이동되는 데이터에 대한 처리 규칙 대용으로 사용할 수도 있습니다. |
| A4T | 의 필드를 통해 부분 지원이 제공됩니다. [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR). 대상 활동 및 경험에 대한 A4T에 친숙한 이름 지원이 계획되어 있습니다. |

{style="table-layout:auto"}

## 지원 없음, 계획됨 {#planned}

| 기능 | 참고 |
| --- | --- |
| 경고 | 지원이 예정되어 있습니다. |
| 기여도 분석 | 지원이 예정되어 있습니다. |
| Data Warehouse 보고 | Analysis Workspace 인터페이스에서 지원이 예정되어 있습니다. Adobe Experience Platform [[!UICONTROL 쿼리 서비스]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ko-KR>) 는 Customer Journey Analytics에서의 이러한 사용 사례에 대한 인터페이스도 제공합니다. |
| 디바이스 그래프를 통한 ID 결합 | 지원이 예정되어 있습니다. |
| 프로젝트 템플릿 | 지원이 예정되어 있습니다. |
| 실시간 보고 | 지원이 예정되어 있습니다. |
| 세그먼트 IQ | 지원이 예정되어 있습니다. |
| 거래 ID 데이터 소스 | 지원이 예정되어 있습니다. |
| 프로젝트/필터/계산된 지표를 Adobe Analytics에서 Customer Journey Analytics으로 마이그레이션 | 지원이 예정되어 있습니다. |
| 요약 수준 데이터 소스 | 지원이 예정되어 있습니다. |

{style="table-layout:auto"}

## 지원 없음, 아직 예정되지 않음 {#not-planned}

| 기능 | 참고 |
| --- | --- |
| Activity Map | 지원이 아직 예정되지 않음 |
| Advertising Cloud | 지원이 아직 예정되지 않음 |

{style="table-layout:auto"}

## 지원되지 않음 {#never}

* 크로스 디바이스 조합을 사용하는 사용자 지표
* Reports &amp; Analytics 대시보드
* Reports &amp; Analytics 책갈피
* Reports &amp; Analytics 대상

## Adobe Analytics에서 사용할 수 없는 Adobe Customer Journey Analytics 기능 {#cja-not-aa}

다음 표에는 Customer Journey Analytics에서 사용할 수 있지만 Adobe Analytics에서는 지원되지 않는 기능이 나와 있습니다.

| 기능 | 더 자세히 |
| --- | --- |
| 모든 종류의 데이터 수용 | Customer Journey Analytics은 모든 종류의 데이터 스키마 및 유형을 보유할 수 있는 Experience Platform의 기능과 결합됩니다. 사용 [경험 데이터 모델(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ko-KR), 데이터를 조합하고 탐색할 수 있도록 균일하게 나타내고 구성할 수 있습니다. Adobe Analytics은 주로 다음과 같은 몇 가지 기능을 갖춘 웹 및 모바일 분석 데이터에 주력하고 있습니다. [데이터 가져오기](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=ko-KR). |
| 무제한 고객 Dimension 및 지표 | Customer Journey Analytics 차원은 제한이 없습니다. 값은 숫자, 텍스트, 개체, 목록 또는 이들의 조합일 수 있습니다. Dimension은 중첩되거나 계층화될 수 있습니다. Analytics는 최대 75개의 prop 및 250개의 eVar를 지원합니다. |
| 무제한 카디널리티/고유 값 | Customer Journey Analytics은 단일 차원 내에서 보고할 수 있는 고유 값 또는 차원 항목을 무제한으로 지원합니다. Adobe Analytics은 500.000개의 고유 값으로 제한됩니다. 무제한 고유 값 또는 차원은 현재 대규모 Analytics 구현과 함께 존재하는 보고 및 분석 제한 사항을 제거합니다. |
| 보고서 시간 변환 | Customer Journey Analytics의 보고서 시간 변환(데이터 보기)을 사용하면 연결에서 데이터를 추가로 해석할 수 있습니다. 재구현 없이 데이터를 변경하거나 제거할 수 있습니다. 하위 문자열을 사용하여 차원을 조작하고, 모든 값에서 지표를 만들고, 하위 이벤트를 필터링할 수 있습니다. 그리고 변환은 모두 비파괴적으로 이루어집니다. Adobe Analytics은 가상 보고서 세트 및 세션화를 통해 제한된 기능을 제공합니다. |
| 실험 분석 | Customer Journey Analytics은 연결의 일부로 정의된 모든 데이터 소스에서 실험의 상승도와 신뢰도를 평가할 수 있습니다. 이 평가를 통해 모든 채널에 걸친 고객 상호 작용 간의 인과 관계를 이해할 수 있습니다. Analytics는 A4T(Target 분석) 통합을 통한 실험 분석으로 제한됩니다. |
| Cross-Device Analytics | Customer Journey Analytics은 인증되지 않은 세션과 인증된 세션의 장치별 데이터 세트의 원활한 결합을 지원합니다. Customer Journey Analytics은 내역 데이터를 알려진 장치로 채우기 위한 오퍼입니다. Analytics에서 이 기능은 단일 보고서 세트 및 장치 그래프 사용으로 제한됩니다. |
| SQL 액세스 | Customer Journey Analytics은 데이터 Distiller 옵션을 사용하여 Adobe의 백엔드 처리에 수집된 데이터의 제한을 제거할 수 있습니다. SQL을 사용하여 데이터를 수정하고, 비즈니스에 고유한 값과 데이터 세트를 만들고, 탐색을 계속할 수 있습니다. Analytics는 해당 데이터에 대한 어떤 종류의 SQL 액세스도 지원하지 않습니다. |
| 향상된 보안 및 개인 정보 보호 옵션 - HIPAA 준비 | Customer Journey Analytics은 HIPAA 지원 이며 규정 준수를 위한 추가 보안 옵션을 제공합니다. Adobe Analytics은 HIPAA가 준비되지 않았습니다. |

{style="table-layout:auto"}
