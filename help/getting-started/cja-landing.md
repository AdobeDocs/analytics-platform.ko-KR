---
title: Customer Journey Analytics 안내서
description: Customer Journey Analytics 랜딩 페이지.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 6b5a9050d6c13e3c9d637a3ed992840a46058cee
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 59%

---

# Customer Journey Analytics 안내서

이 기술 설명서 가이드는 Customer Journey Analytics에 대한 자가 진단 지원을 제공합니다. Customer Journey Analytics을 사용하면 선택한 모든 채널(온라인과 오프라인 모두)에서 고객 데이터를 Adobe Experience Platform으로 가져올 수 있습니다. 그런 다음 Analysis Workspace을 사용하여 기존 디지털 데이터를 분석하는 것처럼 이 데이터를 분석합니다.

Customer Journey Analytics을 사용하면 Analysis Workspace에서 임의 일반 고객 ID의 온라인과 오프라인 데이터를 연결하는 방법을 제어하여 속성, 필터, 흐름, 폴아웃 등을 수행할 수 있습니다. 속성, 필터, 플로우, 폴아웃 등을 수행할 수 있습니다.

## 새로운 기능

Customer Journey Analytics 제품 및 설명서의 최신 개선 사항을 살펴보십시오. 기능, 개선 사항, 해결 사항의 종합 목록은 [릴리스 정보](../release-notes/latest.md)에서 자세히 확인할 수 있습니다.  다음 방문: [설명서 업데이트 페이지](../release-notes/doc-changes.md) 최신 변경 사항을 최신 상태로 유지하십시오.

>[!BEGINTABS]

>[!TAB BI 확장*]

BI 확장을 사용하면 Customer Journey Analytics에서 정의한 데이터 보기에 SQL로 액세스할 수 있습니다. 이제 즐겨 찾는 BI 도구를 사용하여 Customer Journey Analytics 사용자가 Analysis Workspace 프로젝트에서 사용하는 것과 동일한 데이터 보기를 기반으로 보고 및 대시보드를 만들 수 있습니다.

[![이미지](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

<span style="color:gray">*_BI 확장을 사용하려면 Select 패키지 이상이 있어야 합니다._</span>


<!--
>[!TAB Improved Audience Publising] 

Audiences that are published from Customer Journey Analytics are now available in the new **Audiences** section in Adobe Experience Platform. Audiences are now available in Experience Platform seconds after they are published from Customer Journey Analytics. Improved sorting and filter options in Experience Platform for Customer Journey Analytics audiences. 

[![image](assets/learn-more-button.svg)](/help/components/audiences/publish.md)

-->


>[!TAB 새 설명서]

이제 다음 위치에서 새 설명서를 사용할 수 있습니다.<ul><li>Adobe Analytics에서 Customer Journey Analytics으로 업그레이드하는 방법</li><li>데이터 내보내기 사용 사례와 필요한 Experience Platform 및 고객 여정 기능. </li></ul>선택 **[!UICONTROL 자세히 알아보기]** 을 참조하십시오.

[![이미지](assets/learn-more-button.svg)](/help/release-notes/doc-changes.md)

>[!TAB 예측]

예측은 지원되는 시간 단위(시간별, 일별, 주별, 월별, 연간)를 사용하여 표준 또는 계산된 지표를 예측하는 Analysis Workspace 기능입니다. 예측은 시계열 관련 데이터에만 사용할 수 있습니다.

[![이미지](assets/learn-more-button.svg)](/help/analysis-workspace/c-forecast/forecasting.md)

>[!TAB 안내식 분석* - 유지율]

원하는 날짜 범위 내에 초기 참여 후 재방문한 사용자의 비율을 표시하는 새로운 보기 유형입니다. 가로축은 사용자가 처음 참여한 이후의 일 수를 나타냅니다. 세로축은 다시 참여하는 사용자의 비율을 나타냅니다.

[![이미지](assets/learn-more-button.svg)](/help/guided-analysis/types/retention-rates.md)

<span style="color:gray">*_안내식 분석은 Customer Journey Analytics의 유료 추가 기능인 Adobe Product Analytics의 일부입니다._</span>


>[!TAB 안내식 분석* - 추세선]

이제 사용량 보기에서 추세선 오버레이를 사용할 수 있어 데이터의 패턴을 더 명확하게 나타내는 데 도움이 됩니다. 사용 가능한 추세선 유형은 선형, 로그 및 이동 평균입니다.

[![이미지](assets/learn-more-button.svg)](/help/guided-analysis/types/usage.md)

<span style="color:gray">*_안내식 분석은 Customer Journey Analytics의 유료 추가 기능인 Adobe Product Analytics의 일부입니다._</span>

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
    <div><strong>데이터 수집 및 사용</strong><br/>데이터를 Analysis Workspace에 수집하여 Experience Platform의 Customer Journey Analytics 및 보고에 사용해야 하는 옵션에 대해 알아봅니다.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>안내식 분석</strong><br/>워크플로를 사용하여 고객의 제품 경험에 대한 데이터와 통찰력을 얻는 방법을 알아봅니다. 안내식 분석을 통한 Product Analytics…
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

Customer Journey Analytics이 Adobe Analytics과 어떻게 비교되는지 이해합니다. 솔루션에서 데이터를 가져온 다음 해당 데이터와 결과 분석 및 보고서를 준비, 조회, 분석 및 대중화하는 방법

<table style="table-layout:auto">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>Adobe Analytics와 비교</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">개요</a> - <a href="/help/getting-started/aa-to-cja.md">발전</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Adobe Analytics 데이터 사용</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">기능 지원</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">용어</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">데이터 처리</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>연결</strong><br/><a href="/help/connections/overview.md">개요</a> - <a href="/help/connections/create-connection.md">생성</a> - <a href="/help/connections/manage-connections.md">관리</a> - <a href="/help/stitching/overview.md">결합</a> - <a href="/help/connections/combined-dataset.md">결합된 이벤트 데이터 세트</a> - <a href="/help/connections/standard-lookups.md">표준 조회</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>데이터 보기</strong><br/><a href="/help/data-views/data-views.md">개요</a> - <a href="/help/data-views/create-dataview.md">만들기 또는 편집</a> - <a href="/help/data-views/session-settings.md">세션 설정</a> - <a href="/help/data-views/derived-fields/derived-fields.md">파생 필드</a> - <a href="/help/data-views/component-reference.md">구성 요소 참조</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>작업 공간 프로젝트</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">기본</a> 및 <a href="/help/analysis-workspace/perform-adv-analysis.md">고급 분석</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">프로젝트</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">시각화</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">패널</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>안내식 분석</strong><br/><a href="/help/guided-analysis/overview.md">개요</a> - <a href="/help/guided-analysis/types/active.md">사용자 증가</a> - <a href="/help/guided-analysis/types/usage.md">트렌드</a> - <a href="/help/guided-analysis/types/friction.md">단계</a> - <a href="/help/guided-analysis/types/release.md">영향</a> - <a href="/help/guided-analysis/industry-use-cases.md">업계 사용 사례</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>공유, 내보내기, 통합</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">프로젝트</a> - <a href="/help/mobile-app/home.md">Analytics 대시보드</a> - <a href="/help/report-builder/report-buider-overview.md">Report Builder</a>  - <a href="/help/integrations/overview.md">통합</a>
    </td>
  </tr>
</table>

## 추가 리소스

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">튜토리얼</a> - <a href="https://helpx.adobe.com/kr/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics 제품 설명</a> - <a href="https://helpx.adobe.com/kr/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics (Customer Journey Analytics 추가 기능) 제품 설명</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics API</a>
</td>
<td><strong>데이터 수집</strong><br/><a href="/help/data-ingestion/data-ingestion.md">개요</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">배치</a> - <a href="/help/data-ingestion/streaming.md">스트리밍</a> - <a href="/help/data-ingestion/sources.md">소스</a> - <a href="/help/data-ingestion/serverapi.md">서버 API</a>
</td>
</tr></table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>최신 정보를 얻고, 커뮤니티에 기여하고, Customer Journey Analytics 경험을 향상시키십시오!</b><br>Adobe Analytics 커뮤니티를 방문하여 동료 실무자와 이 기능에 대해 논의하십시오. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">지금 커뮤니티에 가입하십시오!</a></td></tr></tbody></table>
