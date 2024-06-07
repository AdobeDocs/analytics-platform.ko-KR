---
title: Customer Journey Analytics 안내서
description: Customer Journey Analytics 랜딩 페이지.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
source-git-commit: 67a249ab291201926eb50df296e031b616de6e6f
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 81%

---

# Customer Journey Analytics 안내서

이 기술 설명서 가이드는 Customer Journey Analytics에 대한 자가 진단 지원을 제공합니다. Customer Journey Analytics를 사용하면 선택한 모든 채널(온라인 및 오프라인)의 고객 데이터를 Adobe Experience Platform으로 가져올 수 있습니다. 그런 다음 현재 Analysis Workspace를 사용하여 기존 디지털 데이터를 분석하는 것처럼 이 데이터를 분석할 수 있습니다.

Customer Journey Analytics를 사용하면 Analysis Workspace에서 임의 일반 고객 ID의 온라인과 오프라인 데이터를 연결하는 방법을 제어할 수 있으며, 이를 통해 고객 데이터 간의 속성, 필터, 플로우, 폴아웃 등을 수행할 수 있습니다.

## 새로운 기능

Customer Journey Analytics 제품 및 설명서의 최신 개선 사항을 살펴보십시오. 기능, 개선 사항, 해결 사항의 종합 목록은 [릴리스 정보](../release-notes/latest.md)에서 자세히 확인할 수 있습니다. 최신 변경 사항을 확인하려면 [설명서 업데이트 페이지](../release-notes/doc-changes.md)를 방문하십시오.

>[!BEGINTABS]

>[!TAB AI Assistant]

AI Assistant는 개념의 이해, 문제 해결 또는 정보 검색 등 실무자가 빠른 속도로 작업을 수행할 수 있는 대화식 경험입니다. 또한 비전문가가 전문가 업무를 수행할 수 있도록 하고 전반적인 업무 품질을 높인다.

[![이미지](assets/learn-more-button.svg)](/help/ai-assistant.md)

>[!TAB B2B 조회]

연결 구성의 일부로, B2B 데이터에 대한 사용자 기반 조회를 더 잘 지원하기 위해 특정 B2B 조회 스키마에 대한 데이터 세트를 변환할 수 있습니다.

[![이미지](assets/learn-more-button.svg)](/help/connections/transform-datasets-b2b-lookups.md)

>[!TAB 파생 필드]

이제 새로운 파생 필드 함수(수학, 다음 또는 이전) 및 추가 함수 템플릿(예: 바운스, 친숙한 데이터 세트 이름, 휴일 시즌, 월별 목표, 단순 보트 탐지 등)을 사용할 수 있습니다.

[![이미지](assets/learn-more-button.svg)](/help/data-views/derived-fields/derived-fields.md)

>[!TAB BI 확장 기능*]

BI 확장 기능을 통해 SQL은 Customer Journey Analytics에서 정의한 데이터 보기에 액세스할 수 있습니다. 이제 Customer Journey Analytics 사용자가 Analysis Workspace 프로젝트에서 사용하는 것과 동일한 데이터 보기를 기반으로 선호하는 BI 도구를 사용하여 보고 및 대시보드를 만들 수 있습니다.

[![이미지](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

<span style="color:gray">*_BI 확장 기능을 사용하려면 Select 패키지 이상이 필요합니다._</span>


<!--
>[!TAB Improved Audience Publising] 

Audiences that are published from Customer Journey Analytics are now available in the new **Audiences** section in Adobe Experience Platform. Audiences are now available in Experience Platform seconds after they are published from Customer Journey Analytics. Improved sorting and filter options in Experience Platform for Customer Journey Analytics audiences. 

[![image](assets/learn-more-button.svg)](/help/components/audiences/publish.md)

-->

>[!TAB 예측]

예측은 지원되는 시간 단위(시간별, 일별, 주별, 월별, 연간)를 사용하여 표준 또는 계산된 지표를 예측하는 Analysis Workspace 기능입니다. 예측은 시계열 관련 데이터에만 사용할 수 있습니다.

[![이미지](assets/learn-more-button.svg)](/help/analysis-workspace/c-forecast/forecasting.md)

>[!TAB 새 설명서]

이제 다음 위치에서 새 설명서 섹션을 사용할 수 있습니다.<ul><li>Adobe Analytics에서 Customer Journey Analytics로 업그레이드하는 방법.</li><li>데이터 내보내기 사용 사례와 필수 Experience Platform 및 Customer Journey 기능. </li></ul>이 내용과 기타 설명서 업데이트 사항을 확인하려면 **[!UICONTROL 자세히 알아보기]**&#x200B;를 선택하십시오.

[![이미지](assets/learn-more-button.svg)](/help/release-notes/doc-changes.md)

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

Customer Journey Analytics와 Adobe Analytics의 비교 내용을 이해합니다. 또한 솔루션에서 데이터를 가져온 다음 해당 데이터와 결과 분석 및 보고서를 준비하고, 보고, 분석하고, 민주화하는 방법을 이해합니다.

<table style="table-layout:fixed">
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
      <strong>데이터 보기</strong><br/><a href="/help/data-views/data-views.md">개요</a> - <a href="/help/data-views/create-dataview.md">생성 또는 편집</a> - <a href="/help/data-views/session-settings.md">세션 설정</a> - <a href="/help/data-views/derived-fields/derived-fields.md">파생 필드</a> - <a href="/help/data-views/component-reference.md">구성 요소 참조</a>
    </td>

</tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Workspace 프로젝트</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">기본 </a> 및 <a href="/help/analysis-workspace/perform-adv-analysis.md">고급 분석</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">프로젝트</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">시각화</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">패널</a>
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
<a href="https://experienceleague.adobe.com/ko/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Tutorials</a> - <a href="https://helpx.adobe.com/kr/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics 제품 설명</a> - <a href="https://helpx.adobe.com/kr/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics(Customer Journey Analytics 추가 기능) 제품 설명</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">CUSTOMER JOURNEY ANALYTICS API</a> - <a href="/help/ai-assistant.md">AI Assistant</a>
</td>
<td><strong>데이터 수집</strong><br/><a href="/help/data-ingestion/data-ingestion.md">개요</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">배치</a> - <a href="/help/data-ingestion/streaming.md">스트리밍</a> - <a href="/help/data-ingestion/sources.md">소스</a> - <a href="/help/data-ingestion/serverapi.md">서버 API</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>최신 정보를 얻고, 커뮤니티에 기여하고, Customer Journey Analytics 경험을 향상시키십시오!</b><br>Adobe Analytics 커뮤니티를 방문하여 동료 실무자들과 기능에 대해 논의해 보십시오. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">지금 커뮤니티에 가입하십시오!</a></td></tr></tbody></table>
