---
title: Customer Journey Analytics 안내서
description: Customer Journey Analytics 랜딩 페이지.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: d8ff5191ea96b8871f6aaba1fc28211c22a13e0d
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 100%

---

# Customer Journey Analytics 안내서

이 기술 설명서 안내서는 Customer Journey Analytics에 대한 자가 진단 지원을 제공합니다. Customer Journey Analytics를 사용하면 선택한 모든 채널(온라인 및 오프라인)의 고객 데이터를 Adobe Experience Platform으로 가져올 수 있습니다. 그런 다음 현재 Analysis Workspace를 사용하여 기존 디지털 데이터를 분석하는 것처럼 이 데이터를 분석할 수 있습니다.

Customer Journey Analytics를 사용하면 Analysis Workspace에서 임의 일반 고객 ID의 온라인과 오프라인 데이터를 연결하는 방법을 제어할 수 있으며, 이를 통해 고객 데이터 간의 속성, 필터, 플로우, 폴아웃 등을 수행할 수 있습니다.

## 새로운 기능

Customer Journey Analytics 제품 및 설명서의 최신 개선 사항을 살펴보십시오. 기능, 개선 사항, 해결 사항의 종합 목록은 [릴리스 정보](../release-notes/latest.md)에서 자세히 확인할 수 있습니다. 최신 설명서 업데이트를 확인하려면 [설명서 업데이트 페이지](../release-notes/doc-changes.md)를 방문하십시오.

>[!BEGINTABS]

>[!TAB 실시간 보고*]

Customer Journey Analytics의 실시간 보고는 Analysis Workspace의 하나 이상의 패널 내에서 데이터와 시각화를 실시간으로 표시하고 업데이트합니다.

[![이미지](assets/learn-more-button.svg)](/help/components/real-time/real-time.md)

*_실시간 보고를 위해서는 Ultimate 패키지가 필요합니다._*

>[!TAB B2B Edition]

Customer Journey Analytics B2B Edition은 매출 성장을 촉진하는 실행 가능한 계정 인사이트를 제공하여 B2B 기업이 마케팅, 영업 및 제품 팀을 조정할 수 있도록 지원합니다. 데이터 모델의 중심에 계정을 두면 모든 분석은 계정 여정에 집중됩니다.

[![이미지](assets/learn-more-button.svg)](/help/getting-started/cja-b2b-edition.md)

>[!TAB 파생 필드 함수]

새로운 파생 필드 함수: [날짜 계산](/help/data-views/derived-fields/derived-fields.md#date-math), [깊이](/help/data-views/derived-fields/derived-fields.md#depth), [타입캐스트](/help/data-views/derived-fields/derived-fields.md#typecast).

[![이미지](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB Content Analytics]

Content Analytics를 사용하면 대량의 콘텐츠 데이터를 쉽고 빠르게 조사하여 트렌드를 파악하고, 예외 항목을 발견하고, 콘텐츠 피로도를 식별하고, 콘텐츠 노출로부터 인사이트를 얻을 수 있습니다.

[![이미지](assets/learn-more-button.svg)](/help/content-analytics/content-analytics.md)

>[!TAB 이벤트 심도]

이벤트 심도는 새로운 표준 차원으로, 고객 세션 내에서 이벤트가 어떻게 배치되어 있는지를 측정하고 더 잘 이해할 수 있는 새로운 방법을 제공합니다. 이벤트 심도 차원을 통해 세션 내 사용자 상호 작용의 순차적인 흐름 속에서 특정 이벤트가 발생한 위치를 보다 세밀하게 추적하고 분석할 수 있습니다.

[![이미지](assets/learn-more-button.svg)](/help/components/dimensions/overview.md#standard-dimensions)


>[!TAB 공유된 지표 및 차원]

공유된 지표와 차원은 여러 데이터 보기에서 사용할 수 있는 차원과 지원을 관리할 수 있는 중심 위치를 제공합니다. 이러한 구성 요소는 여러 데이터 보기를 사용하는 조직에게 특히 유용하며, 이러한 데이터 보기가 공통 구성 요소 설정을 공유하는 경우 더욱 유용합니다.

[![이미지](assets/learn-more-button.svg)](/help/data-views/shared-metrics-dimensions/smd-overview.md)


<!--
>[!TAB AI Assistant] 

AI Assistant is a conversational experience that allows practitioners to perform tasks at a fast pace - whether its understanding concepts, troubleshooting problems, or searching through information. It also allows non-experts to perform expert tasks and increases the overall quality of work.

[![image](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Guided Analysis] 

Guided Analysis is now available directly from within Analysis Workspace, enabling users to create dashboards with comprehensive insights from panels, visualizations, and guided analyses.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)



>[!TAB Intelligent captions v2] 

Intelligent captions are now supported, with additional interface improvements, for [Line](/help/analysis-workspace/visualizations/line.md) (including multi-line), [Bar](/help/analysis-workspace/visualizations/bar.md), [Horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md), [Area](/help/analysis-workspace/visualizations/area.md) (including multiple Area lines), [Donut](/help/analysis-workspace/visualizations/donut.md), [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), and [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md) visualizations.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Alerts] 

Alerts allow you to be notified based on changed percentages or specific data points. You can preview how often an alert will trigger, send alerts by email or SMS, create stacked alerts, and more.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Summary data] 

Allows you to bring in time-series data that does not have a person ID. This time-series data can be used to support various use cases, such as 

- Presenting high-level performance indicators as part of or next to event-level data. 
- Uploading targets or goals at an hourly or daily basis, then positioning these targets or goals against event-level metrics. 

[![image](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

-->

>[!TAB 그래프 기반 스티칭*]

그래프 기반 결합을 통해 Experience Platform ID 서비스의 아이덴티티 그래프를 사용하면 다음 작업을 수행하여 고객 여정을 더 효과적으로 확인할 수 있습니다. <ul><li>추가 데이터를 추출, 변환 및 로드하여 단일 식별자를 반영할 필요 없이 다양한 식별자를 사용하여 데이터 세트를 결합합니다.</li> <li>데이터 세트 전체에서 ID를 공유하여 단일 데이터 세트에 대한 기본 ID 또는 골든 ID의 적용 범위를 개선합니다.</li><li>Real-Time Customer Data Platform 및 Journey Optimizer에서 생성된 프로필을 Customer Journey Analytics의 사람들과 맞춥니다.</li></ul>

[![이미지](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_그래프 기반 스티칭을 위해서는 Prime 패키지가 필요합니다._*

>[!TAB BI 확장 기능*]

BI 확장 기능을 통해 SQL은 Customer Journey Analytics에서 정의한 데이터 보기에 액세스할 수 있습니다. 이제 Power BI Desktop, Tableau Desktop, Looker, Juyter Notebook, RStudio 등 선호하는 BI 도구를 사용하여 Customer Journey Analytics 사용자가 Analysis Workspace 프로젝트에서 사용하는 것과 동일한 데이터 보기를 기반으로 보고서와 대시보드를 만들 수 있습니다. [사용 사례](/help/use-cases/data-views/bi-extension-usecases.md)가 제공됩니다.

[![이미지](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

*_BI 확장 기능을 사용하려면 Select 패키지 이상이 필요합니다._*


>[!ENDTABS]

## 기본 사항부터 시작

먼저 아래 링크의 자료를 통해 Customer Journey Analytics의 다양한 기능을 자세히 살펴보십시오.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>온라인 데이터 그 이상</strong><br/>Customer Journey Analytics가 Adobe Analytics와 어떻게 비교되는지, 어떤 기능이 공유되는지, Analytics 데이터를 어떻게 사용할 수 있는지 알아봅니다.</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>데이터 수집 및 사용</strong><br/>Experience Platform에 데이터를 수집하고 이를 Customer Journey Analytics에서 분석 및 보고하는 데 사용할 수 있는 옵션에 대해 알아봅니다.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>가이드 분석</strong><br/>워크플로를 사용하여 고객의 제품 경험에 대한 데이터와 통찰력을 얻는 방법을 알아봅니다. 가이드 분석을 통한 Product Analytics…
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>Analysis Workspace를 사용하면 속성, 플로우 및 폴아웃 다이어그램, 차원 분석과 같은 기본 및 고급 분석을 수행할 수 있습니다.</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/guided-analysis/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/analysis-workspace/home.md"><img src="./assets/learn-more-button.svg"></a></td>
    </tr>
</table>


## 설명서 살펴보기

Customer Journey Analytics와 Adobe Analytics의 비교 내용을 이해합니다. 또한 솔루션에서 데이터를 가져온 다음 해당 데이터와 결과 분석 및 보고서를 준비하고, 보고, 분석하고, 민주화하는 방법을 이해합니다.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>Adobe Analytics와 비교</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">개요</a> - <a href="/help/getting-started/aa-to-cja.md">발전</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Adobe Analytics 데이터 사용</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">기능 지원</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">용어</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">데이터 처리</a> - <a href="/help/getting-started/cja-b2b-edition.md">Customer Journey Analytics B2B Edition</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>연결</strong><br/><a href="/help/connections/overview.md">개요</a> - <a href="/help/connections/create-connection.md">생성</a> - <a href="/help/connections/manage-connections.md">관리</a> - <a href="/help/stitching/overview.md">결합</a> - <a href="/help/connections/combined-dataset.md">결합된 이벤트 데이터 세트</a> - <a href="/help/connections/standard-lookups.md">표준 조회</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>데이터 보기</strong><br/><a href="/help/data-views/data-views.md">개요</a> - <a href="/help/data-views/create-dataview.md">만들기 또는 편집</a> - <a href="/help/data-views/session-settings.md">세션 설정</a> - <a href="/help/data-views/derived-fields/derived-fields.md">파생 필드</a> - <a href="/help/data-views/summary-data.md">요약 데이터</a> - <a href="/help/data-views/component-reference.md">구성 요소 참조</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Workspace 프로젝트</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">기본 </a> 및 <a href="/help/analysis-workspace/perform-adv-analysis.md">고급 분석</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">프로젝트</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">시각화</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">패널</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>가이드 분석</strong><br/><a href="/help/guided-analysis/overview.md">개요</a> - <a href="/help/guided-analysis/types/active-growth.md">사용자 증가</a> - <a href="/help/guided-analysis/types/trends.md">트렌드</a> - <a href="/help/guided-analysis/types/funnel.md">단계</a> - <a href="/help/guided-analysis/types/release-impact.md">영향</a> - <a href="/help/guided-analysis/industry-use-cases.md">업계 사용 사례</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>공유, 내보내기, 통합</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">프로젝트</a> - <a href="/help/mobile-app/home.md">Analytics 대시보드</a> - <a href="/help/report-builder/rb-overview.md">Report Builder</a>  - <a href="/help/components/exports/manage-exports.md">클라우드 내보내기</a> - <a href="/help/integrations/overview.md">통합</a>
    </td>
  </tr>
</table>

## 추가 리소스

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/ko/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">튜토리얼</a> - <a href="https://helpx.adobe.com/kr/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics 제품 설명</a> - <a href="https://helpx.adobe.com/kr/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics(Customer Journey Analytics 추가 기능) 제품 설명</a> - <a href="https://helpx.adobe.com/kr/legal/product-descriptions/customer-journey-analytics-b2b.html" target="_blank">Customer Journey Analytics B2B Edition 제품 설명</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics API</a> - <a href="/help/ai-assistant.md">AI 어시스턴트</a>
</td>
<td><strong>데이터 수집</strong><br/><a href="/help/data-ingestion/data-ingestion.md">개요</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">배치</a> - <a href="/help/data-ingestion/streaming.md">스트리밍</a> - <a href="/help/data-ingestion/sources.md">소스</a> - <a href="/help/data-ingestion/serverapi.md">서버 API</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>최신 정보를 얻고, 커뮤니티에 기여하고, Customer Journey Analytics 경험을 향상시키십시오!</b><br>Adobe Analytics 커뮤니티를 방문하여 동료 실무자들과 기능에 대해 논의해 보십시오. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community?profile.language=ko">지금 커뮤니티에 가입하십시오!</a></td></tr></tbody></table>
