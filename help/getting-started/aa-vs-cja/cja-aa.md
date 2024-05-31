---
title: Customer Journey Analytics 기능 지원
description: Customer Journey Analytics 기능과 Adobe Analytics 기능 세트를 비교한 것입니다.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 3acf29b703d52145d8679d60ed664cf794b5ee30
workflow-type: tm+mt
source-wordcount: '2255'
ht-degree: 86%

---

# Customer Journey Analytics 기능 지원

다음 표는 Customer Journey Analytics에서 지원되거나, 부분적으로 지원되거나, 지원되지 않는 Adobe Analytics의 기능을 보여 줍니다. 그리고 Customer Journey Analytics의 기능은 Adobe Analytics에서 지원 또는 사용할 수 없습니다. 이러한 기능은 Customer Journey Analytics에 추가되므로 시간이 지남에 따라 위의 표가 변경됩니다.

## 완전히 지원되는 기능/구성 요소 {#full-support}

| Adobe Analytics 기능 | 지원 관련 참고 사항 |
| --- | --- |
| 예외 항목 탐지 | 전체 지원 |
| Attribution IQ | 전체 지원 |
| 봇 탐지 | [전체 지원](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) |
| 계산된 지표 | 전체 지원. 기존 Analysis Workspace의 기존 계산된 지표는 Customer Journey Analytics에 포팅되지 않습니다. |
| 캘린더 이벤트 | 전체 지원. 캘린더 이벤트가 Workspace의 [주석](/help/components/annotations/overview.md)으로 구현되었습니다. |
| CSV 다운로드 | 전체 지원 |
| 사용자 정의 캘린더 | 전체 지원 |
| 날짜 비교 | 전체 지원 |
| 날짜 범위 | 모든 날짜 범위 기능이 지원됩니다. |
| 차원 | 전체 지원. Customer Journey Analytics는 XDM을 사용하며 무제한 차원을 지원합니다. Customer Journey Analytics는 기존 Adobe Analytics의 사용자 정의 eVar 또는 속성에 연결되지 않습니다. |
| GDPR 삭제 | 전체 지원: 이제 [!UICONTROL Adobe Experience Platform]에 GDPR이 적용됩니다. Customer Journey Analytics는 [!UICONTROL Experience Platform]의 기본 데이터 세트에 적용되는 모든 데이터 변경 사항을 상속합니다. |
| 상승도 및 신뢰도 보고 | [실험 패널](/help/analysis-workspace/c-panels/experimentation.md)을 통한 전체 지원 |
| 목록 변수/목록 속성 | 전체 지원. Customer Journey Analytics는 XDM을 사용하며 listVar와 유사하게 사용할 수 있는 무제한 문자열 배열을 지원합니다. |
| 머천다이징 eVar | [바인딩 차원 및 바인딩 지표](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)를 통한 전체 지원 |
| 지표 | 전체 지원: Customer Journey Analytics는 XDM(경험 데이터 모델)을 사용하고 무제한 지표를 지원하며, Adobe Analytics의 사용자 정의 성공 이벤트에 연결되지 않습니다. 일부 표준 지표의 이름은 Adobe Analytics에서 다음과 같이 변경되었습니다. 방문자 = 사람, 방문 횟수 = 세션, 히트 수 = 이벤트 |
| 프로젝트, 필터, 계산된 지표를 Adobe Analytics에서 Customer Journey Analytics로 마이그레이션 | 전체 지원 |
| 모바일 스코어카드/대시보드 | 전체 지원 |
| 패널 | 빈 패널, 기여도 분석, 자유 형식, 빠른 인사이트, 다음 또는 이전 항목과 같은 패널을 전체 지원합니다. |
| PDF 내보내기 | 전체 지원 |
| 프로젝트 큐레이션 | 전체 지원 |
| 프로젝트 연결 | 전체 지원 |
| 보고서 처리 시간 | 전체 지원: Customer Journey Analytics는 보고 시 처리에만 사용합니다. |
| 보고 API 액세스 | 전체 지원: [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/)를 통해 이용 가능합니다. |
| 예약된 보고서/프로젝트 | 전체 지원 |
| 세그먼트 | 전체 지원. 이제 “필터”라고 합니다. 기존 Analysis Workspace의 기존 세그먼트는 Customer Journey Analytics로 포팅되지 않습니다. |
| 가상 보고서 세트 | 전체 지원. 이제 [데이터 보기](/help/data-views/create-dataview.md)라고 합니다. |
| 가상 보고서 세트 구성 요소 큐레이션 | 전체 지원: 이제 데이터 보기의 일부라고 합니다. |
| 디바이스, 브라우저, 레퍼러, 기술 차원 | [Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) 기반의 데이터 세트와 Web SDK에서 생성된 데이터 세트 모두에 대해 지원됩니다. [ADC를 통해 지원되는 Analytics 변수에 대한 설명서](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=ko-KR)를 참조하십시오. Experience Platform Web SDK 데이터 컬렉션을 사용하는 경우 디바이스 조회에 기반한 디바이스 및 차원은 현재 지원되지 않습니다. 향후 지원 계획이 있습니다. Web SDK 데이터스트림에 디바이스 및 브라우저 조회를 추가하려면 [이 설명서](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html)를 참조하십시오. |
| 스트리밍 미디어 Analytics | 미디어 데이터는 Analytics 소스 커넥터를 미디어 동시 뷰어 패널 및 작업 영역의 미디어 재생 소요 시간 패널의 일부로 사용할 수 있습니다. |

{style="table-layout:auto"}

## 새로운 방식으로 지원됨 {#new-support}

| 기능 | 참고 |
| --- | --- |
| Analytics for Target (A4T) | 다음 [Adobe Customer Journey Analytics과 Target 간의 통합](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja/target-reporting-in-cja) 은 최적화 프로그램에 강력한 분석 및 시간 절약 도구를 제공합니다. |
| 대상자 게시 | Adobe의 Customer Data Platform 또는 Journey Optimizer 제품 라이선스가 부여된 경우 지원됩니다. [대상자 게시](/help/components/audiences/audiences-overview.md)는 Experience Platform의 실시간 고객 프로필로 대상자를 보냅니다. |
| 분류 | 이제 “조회 데이터 세트”라고 합니다. Analytics에서 사용되는 분류는 Analytics 분류 소스 커넥터를 사용하여 Experience Platform 및 Customer Journey Analytics로 가져올 수 있습니다. 조회 데이터 세트를 Experience Platform에 직접 업로드하여 Customer Journey Analytics에서 사용할 수도 있습니다. |
| 분류 규칙 빌더 | Customer Journey Analytics에서 [하위 문자열](/help/data-views/component-settings/substring.md)을 사용하여 지원됩니다. 조회 데이터 세트가 아니라 보고서 시간에 문자열 조작을 사용합니다. |
| 사용자 정의 세션 길이 | 세션 길이는 데이터 보기의 [세션 설정](../../data-views/create-dataview.md#session-settings)을 통해 구성할 수 있습니다. 자세한 내용은 [세션 설정](../../data-views/session-settings.md)을 참조하시기 바랍니다. <br/>모바일 배경 이벤트 처리는 Adobe Experience Platform Mobile SDK를 통해 지원됩니다. 자세한 내용은 [Edge Network의 라이프사이클](https://developer.adobe.com/client-sdks/documentation/lifecycle-for-edge-network/)을 참조하십시오. |
| 통화 전환 | 데이터 보기에서 [지표 구성 요소 서식을 지정하는](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html#currency) 일부로 지원됩니다. |
| 머천다이징 변수 지속성 | [바인딩 차원 및 바인딩 지표](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html#binding-dimension)를 통한 전체 지원 |
| 사용자 속성 | 이제 “프로필 데이터 세트”라고 하며, Experience Cloud에서 자동으로 가져오지 않습니다. Customer Journey Analytics에서 사용하려면 Experience Platform으로 업로드해야 합니다. |
| 데이터 피드 | 데이터 세트의 1세대 데이터 내보내기는 [Experience Platform 데이터 액세스 API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html)와 [Experience Platform 대상](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html)을 통해 사용할 수 있습니다. 이러한 옵션은 수집되거나 Experience Platform Data Lake에 수집된 모든 데이터의 이벤트/행 수준 내보내기를 제공합니다. 이후 열은 쿼리 시간에 계산되므로 후 처리 데이터 열을 사용할 수 없습니다. 이후 열 내보내기는 보고를 통해 사용할 수 있습니다. |
| Data Warehouse 보고 | [Customer Journey Analytics 전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md)는 현재 Data Warehouse에서 사용할 수 없지만 자주 요청되는 새로운 기능을 다수 포함하는 Adobe Analytics의 Data Warehouse 보고서에 대한 개선 사항입니다. |
| 시작, 종료, 사용 시간 차원 및 지표 | 지원되며(시작 및 종료는 이제 세션 시작 및 세션 종료라고 함), 약간 다른 방식으로 계산됩니다. |
| eVar 지속성 설정 | eVar는 더 이상 Customer Journey Analytics에 포함되지 않습니다. 하지만 지속성 설정은 이제 데이터 보기에 속하고, 모든 차원에서 사용할 수 있습니다. 지속성은 데이터 수집 처리 시간이 아니라 보고서 처리 시간을 기반으로 한다는 점을 명심하십시오. 데이터 보기 내에서 설정된 차원은 최대 90일로 지속성이 제한되며 무제한 지속성을 지원하지 않습니다. |
| 지리 특성 차원 | [전체 지원](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ko-KR) |
| IP 난독화 | Analytics 소스 커넥터를 사용하여 Adobe Analytics에서 Customer Journey Analytics로 데이터를 가져오는 Customer Journey Analytics 고객의 경우: Adobe Analytics에 적용된 IP 난독화 설정이 Customer Journey Analytics 데이터로 흐릅니다. 필요에 따라 Adobe Analytics에서 이러한 설정을 제어할 수 있습니다.<p>Experience Platform Web SDK를 사용하여 Platform 및 Customer Journey Analytics로 데이터를 직접 가져오는 Customer Journey Analytics 고객의 경우. 데이터 수집을 위한 데이터 준비를 사용하면 회사의 요구 사항에 따라 IP 주소를 난독화하는 규칙을 구성할 수 있습니다. |
| 마케팅 채널 | Analytics 소스 커넥터를 사용하는 경우 마케팅 채널 데이터는 해당 커넥터를 통해 Customer Journey Analytics로 흐릅니다. 마케팅 채널 규칙은 계속 기존의 Adobe Analytics에서 구성되며 일부 규칙은 지원되지 않습니다. 자세한 내용은 [Customer Journey Analytics 마케팅 채널](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html)를 참조하십시오. <br/>Web SDK 구현의 경우 보고 시 마케팅 채널 처리 규칙은 [파생 필드](../../data-views/derived-fields/derived-fields.md)를 통해 지원됩니다. |
| 지표 중복 제거 | 이제 데이터 보기 내의 지표에 대해 구성됩니다. 지표 중복 제거는 데이터 세트, 데이터 보기 또는 연결 수준이 아닌 개인 또는 세션 수준에서 발생합니다. |
| 새 세션 보고와 반복 세션 보고 비교 | 이전에는 방문 수 차원을 사용하여 수행했습니다. 새 세션과 반복 세션은 [13개월 조회 기간](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html)으로 지원됩니다. |
| 처리 규칙, VISTA 규칙, 마케팅 채널 처리 규칙 | Web SDK 기반 데이터 세트와 Analytics 소스 커넥터의 데이터 모두에 대해 Adobe Experience Platform Data Prep 기능과 [파생 필드](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)를 사용하여 지원됩니다. |
| Products 변수 | Experience Platform 내에서 사용자는 데이터 세트 스키마 내의 오브젝트 배열을 사용하여 이 사용 사례를 충족할 수 있습니다. Customer Journey Analytics 내에서 고객은 다양한 제품 변수를 사용할 수 있으며 Adobe Analytics에서처럼 단일 변수로 제한되지 않습니다. |
| 프로젝트 공유 | 프로젝트 공유는 Customer Journey Analytics 사용자 사이에서만 지원됩니다. Customer Journey Analytics와 기존 Analysis Workspace 간에 프로젝트를 공유할 수 없습니다. |
| Report Builder | Excel용 새로운 Office 365 플러그인으로 지원됩니다. |
| 사용자 권한/데이터 액세스 제어 | Customer Journey Analytics는 [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html) 제품 관리자, 제품 프로필 관리자 및 사용자를 구별합니다. 제품 관리자만 다른 사용자가 만든 연결, 프로젝트, 필터 또는 계산된 지표를 생성/업데이트/삭제할 수 있으며, 제품 관리자와 제품 프로필 관리자는 데이터 보기를 편집할 수 있습니다. 계산된 지표, 필터 또는 주석 생성과 같은 작업에 추가적인 사용자 권한을 사용할 수 있습니다. |
| 시각화 | 맵 시각화를 제외한 모든 Workspace 시각화가 지원됩니다. |
| 크로스 디바이스/크로스 채널 결합 | ID 정보를 직접 포함하는 데이터 세트에 대해 지원됩니다(“필드 기반” 스티칭이라고도 함). 그래프 기반 스티칭은 아직 지원되지 않지만 향후 지원될 예정입니다. [결합](../../stitching/overview.md)을 참조하십시오. |

{style="table-layout:auto"}

## 부분 지원 {#partial}

| 기능 | 참고 |
| --- | --- |
| 패널 | 빈 패널, 기여도 분석 패널, 자유 형식 패널 및 빠른 인사이트가 완벽하게 지원됩니다. 세그먼트 비교 및 A4T(Analytics for Target) 패널은 지원되지 않습니다. |

{style="table-layout:auto"}

## 지원되지 않지만, 지원 예정 {#planned}

| 기능 | 참고 |
| --- | --- |
| 경고 | 지원이 예정되어 있습니다. |
| 기여도 분석 | 지원이 예정되어 있습니다. |
| 디바이스 그래프를 사용하여 ID 결합 | 지원이 예정되어 있습니다. |
| 프로젝트 템플릿 | 지원이 예정되어 있습니다. |
| 실시간 보고 | 지원이 예정되어 있습니다. |
| 세그먼트 IQ | 지원이 예정되어 있습니다. |
| 거래 ID 데이터 소스 | 지원이 예정되어 있습니다. |
| 요약 수준 데이터 소스 | 지원이 예정되어 있습니다. |

{style="table-layout:auto"}

## 지원되지 않고, 지원이 아직 예정되지 않음 {#not-planned}

| 기능 | 참고 |
| --- | --- |
| Activity Map | 지원이 아직 예정되지 않음 |
| Advertising Cloud | 지원이 아직 예정되지 않음 |

{style="table-layout:auto"}

## 지원 예정 없음 {#never}

* 크로스 디바이스 조합을 사용하는 사용자 지표

## Adobe Analytics에서 사용할 수 없는 Adobe Customer Journey Analytics 기능 {#cja-not-aa}

다음 표는 Customer Journey Analytics에서 사용할 수 있지만 Adobe Analytics에서 지원되지 않는 기능을 보여 줍니다.

| 기능 | 자세한 내용 |
| --- | --- |
| 데이터 세트(예: Adobe Analytics 보고서 세트) 결합 기능 | Customer Journey Analytics을 사용하면 다음 작업을 수행할 수 있습니다. [데이터 결합](/help/connections/combined-dataset.md) Adobe Analytics의 단일 보고서 세트인 것처럼 여러 보고서 세트에서. |
| 모든 유형의 데이터 수용 | Customer Journey Analytics는 모든 종류의 데이터 스키마와 유형을 보유할 수 있는 Experience Platform의 기능과 결합되어 있습니다. [경험 데이터 모델(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)을 사용하여 데이터를 조합하고 탐색할 수 있도록 균일하게 나타내고 구성할 수 있습니다. Adobe Analytics는 일부 [데이터 가져오기](https://experienceleague.adobe.com/docs/analytics/import/home.html) 기능을 사용하여 주로 웹 및 모바일 분석 데이터에 중점을 둡니다. |
| Cross-Device Analytics | Customer Journey Analytics는 인증되지 않은 세션과 인증된 세션에서 디바이스별 데이터 세트의 원활한 조합을 지원합니다. Customer Journey Analytics는 알려진 디바이스에 내력 데이터 채우기를 제공합니다. Adobe Analytics에서 이 기능은 단일 보고서 세트 및 장치 그래프 사용으로 제한됩니다. |
| 차원 개선 사항 | Customer Journey Analytics는 차원을 사용할 때 더 큰 유연성을 자랑합니다. <ul><li>**사용자 정의 숫자 기반 차원**: [데이터 보기 내에서 숫자 기반 차원을 직접 만듭니다](/help/data-views/create-dataview.md#components).</li><li>**문자열 기반 차원 정렬**: [자유 형식 테이블에서 문자열 기반 차원을 알파벳순으로 정렬합니다.](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md#sort-tables) </li></ul><p>Adobe Analytics에서는 소수의 기본 제공 숫자 차원만 사용할 수 있었으며 문자열 기반 차원별로 정렬하는 것은 불가능했습니다.</p> |
| 파생 필드 | [파생 필드](/help/data-views/derived-fields/derived-fields.md) 데이터에 대한 보고서 시간 변환을 허용합니다. 데이터는 즉시 결합하거나, 수정하거나, 생성할 수 있으며 모든 보고에 소급 적용됩니다. |
| 향상된 보안 및 개인정보 보호 옵션 - HIPAA 지원 | Customer Journey Analytics은 HIPAA 준비 및 오퍼 [추가 보안 옵션](/help/privacy/cmk.md) 규정 준수. Adobe Analytics는 HIPAA를 지원하지 않습니다. |
| 실험 분석 | Customer Journey Analytics 가능 [모든 실험의 상승도 및 신뢰도 평가](/help/analysis-workspace/c-panels/experimentation.md) 연결의 일부로 정의된 모든 데이터 소스. 이 평가를 사용하여 모든 채널에 걸쳐 고객 상호 작용 간의 인과 관계를 이해할 수 있습니다. 분석은 A4T를 통한 실험 분석으로 제한됩니다. |
| 예측 | [예측](/help/analysis-workspace/c-forecast/forecasting.md) 는 Customer Journey Analytics에 이미 존재하는 이전 데이터를 기반으로 시계열 관련 데이터에 대한 통계 예측을 포함하는 AI/ML 기능입니다. 예측은 자유 형식 테이블과 선 그래프 시각화로 표시될 수 있습니다. |
| 안내식 분석 | [안내식 분석](/help/guided-analysis/overview.md) 는 사용자가 데이터 요구 사항을 신속하게 자체 서비스하여 고품질의 인사이트를 신속하게 얻고 데이터 중심의 의사 결정을 내릴 수 있도록 하는 보고 형식입니다. 안내식 분석은 Customer Journey Analytics의 추가 기능인 Adobe Product Analytics의 일부입니다. |
| 지능형 캡션 | 지능형 캡션은 고급 머신 러닝 및 생성형 AI를 사용하여 Workspace 시각화에 대한 유용한 자연어 인사이트를 제공합니다. 초기 릴리스에서는 [라인](/help/analysis-workspace/visualizations/line.md) 시각화에 대한 자동 생성된 인사이트를 제공합니다. |
| 보고 시간 변환 | [데이터 보기](/help/data-views/data-views.md) Customer Journey Analytics에서 연결의 데이터를 추가로 해석할 수 있습니다. 구현을 변경하지 않고도 데이터를 변경 또는 제거할 수 있습니다. 하위 문자열을 사용하여 차원을 조작하고, 모든 값에서 지표를 만들고, 하위 이벤트를 필터링할 수 있습니다. 이러한 변형은 모두 비파괴적인 방식으로 수행됩니다. Adobe Analytics는 가상 보고서 세트와 사용자 정의 세션 길이를 통해 기능이 제한됩니다. |
| BI 확장 | 다음 [BI 확장](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/data-export/bi-extension) cja를 PowerBI 또는 Tableau와 같이 자주 사용하는 BI 시각화 도구에 직접 연결할 수 있습니다. 이 확장을 사용하면 BI 보고서가 Analysis Workspace 및 기타 CJA 보고 인터페이스에 표시되는 항목과 정확하게 일치하도록 할 수 있습니다. 이 방법은 원시 데이터에서 보고서/지표를 다시 생성하지 않고도 CJA용 BI 보고를 더 쉽게 얻을 수 있는 방법입니다. |
| SQL 액세스 | Data Distiller 옵션을 사용하여 Customer Journey Analytics는 Adobe 백엔드 처리 시 수집된 데이터의 제한 사항을 제거할 수 있습니다. SQL로 데이터를 수정하고 비즈니스 고유 값과 데이터 세트를 만들어 계속 탐색할 수 있습니다. Analytics는 해당 데이터에 대한 모든 종류의 SQL 액세스를 지원하지 않습니다. |
| 결합 | [ID 결합](/help/stitching/overview.md) (또는 간단히 말해 결합)은 크로스 채널 분석에 대한 이벤트 데이터 세트의 적합성을 높이는 강력한 기능입니다. 크로스 채널 분석은 Customer Journey Analytics이 처리할 수 있는 주요 사용 사례이며, 이를 통해 공통 식별자(개인 ID)를 기반으로 다른 채널의 여러 데이터 세트에 보고서를 원활하게 결합하고 실행할 수 있습니다. |
| 무제한 고객 차원 및 지표 | Customer Journey Analytics 차원은 무제한이지만 값은 숫자, 텍스트, 오브젝트, 목록 또는 이들의 혼합된 값일 수 있습니다. 차원은 중첩되거나 계층형 차원일 수 있습니다. <p>반대로 Adobe Analytics는 최대 75개의 속성과 250개의 eVar를 지원합니다.</p> |
| 무제한 고유 값 | Customer Journey Analytics는 보고될 수 있는 단일 차원 내의 무제한 고유 값 또는 차원 항목을 지원합니다.<p>[차원에는 카디널리티 제한](/help/components/dimensions/high-cardinality.md)이 없으므로 고유한 값을 표시하고 계산할 수 있습니다.</p><p>이 접근 방식 덕분에 대규모 Adobe Analytics 구현에 존재할 수 있는 보고 및 분석 제한 사항이 사라지므로 [!UICONTROL 낮은 트래픽] 레이블이 가능합니다.</p><p>Customer Journey Analytics에서는 [!UICONTROL 고유 수 초과됨] 레이블을 볼 수 있지만, 이러한 현상은 발생 빈도가 훨씬 낮으며 데이터에 필터나 세그먼트를 적용하여 완화할 수 있습니다.</p> |

{style="table-layout:auto"}
