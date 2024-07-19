---
title: Customer Journey Analytics 안내서
description: Customer Journey Analytics 랜딩 페이지.
exl-id: c2d9b758-42a4-4b58-9bab-095518efb86d
solution: Customer Journey Analytics
feature: Basics
role: User, Admin, Developer
hide: true
hidefromtoc: true
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 100%

---

# Customer Journey Analytics 안내서

이 기술 설명서 가이드는 Customer Journey Analytics에 대한 자가 진단 지원을 제공합니다. Customer Journey Analytics를 사용하면 온라인과 오프라인을 막론하고 선택한 모든 채널에서 고객 데이터를 Adobe Experience Platform으로 가져온 다음 Analysis Workspace를 사용하여 기존 디지털 데이터를 분석하는 것처럼 이 데이터를 분석할 수 있습니다.

Customer Journey Analytics를 사용하면 Analysis Workspace에서 임의 일반 고객 ID의 온라인과 오프라인 데이터를 연결하는 방법을 제어할 수 있으며, 이를 통해 최종적으로 Customer Journey Analytics의 전체 고객 데이터 세트 전반에서 속성, 필터, 흐름, 폴아웃 등을 수행할 수 있습니다.

<table frame="none"> 
 <tbody> 
  <tr> 
   <td colname="col1" colsep="0" rowsep="0" valign="top"> <p class="head"> <b>새 항목 또는 중요 항목</b> </p> <p> 
     <ul>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/stitching/overview.html"> 교차 채널 분석(Customer Journey Analytics에서의 ID 결합) </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html">Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 활용 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html"> 보고서 세트를 다른 스키마와 결합 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html"> 처리 규칙, VISTA 및 분류 대 데이터 준비 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html"> Adobe Analytics 및 Customer Journey Analytics 보고 기능 간의 데이터 처리 비교 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html"> 가상 보고서 세트, 데이터 보기, Adobe Experience Platform 샌드박스 및 Analytics 소스 커넥터 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=ko-KR"> Adobe Analytics에서 Customer Journey Analytics로의 진화 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja-user.html?lang=ko-KR"> Adobe Analytics 사용자를 위한 Customer Journey Analytics 사용 안내서 </a> </li>
     <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=ko-KR#connection-detail"> 강화된 연결 관리 기능 사용 </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=ko-KR#cja-dataviews"> 강화된 데이터 보기 기능 사용 </a> </li>
   <td colname="col2" valign="top"><p class="head"> <b>시작하기</b> </p> 
      <ul> 
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=ko-KR"> Customer Journey Analytics 시작하기 </a> </li> 
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=ko-KR"> 자주 묻는 질문</a> </li> 
   </ul> <p class="head"><b>릴리스 정보</b> </p> 
     <li>새로운 기능 및 수정 사항에 대해서는 최신 <a href="https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=ko-KR" format="https" scope="external"> Customer Journey Analytics 릴리스 정보</a>를 참조하십시오. </li>
    <td colname="col3" valign="top"> <p class="head"><b>Customer Journey Analytics API</b> </p> 
    <ul> 
     <li>모든 <a href="https://developer.adobe.com/cja-apis/docs/" format="https" scope="external">Customer Journey Analytics API</a>를 살펴보십시오. </li>
      <li>최신 <a href="https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API" format="https" scope="external">Customer Journey Analytics Reporting API</a>를 살펴보십시오. </li>
    </ul> <p class="head"> <b>Adobe Experience Platform 리소스</b> </p> 
    <ul> 
     <li><a href="https://www.adobe.com/kr/experience-platform.html" format="http" scope="external"> Adobe Experience Platform</a> </li> 
     <li> <a href="https://experienceleague.adobe.com/docs/platform-learn/tutorials/overview.html?lang=ko-KR" format="https" scope="external">Adobe Experience Platform 튜토리얼</a> </li> 
     <li><a href="https://www.adobe.io/apis/experienceplatform/home/api-reference.html" format="https" scope="external"> API 참조</a> </li> 
     <li><a href="https://www.adobe.com/kr/experience-platform/documentation-and-developer-resources.html" format="https" scope="external"> 설명서 및 개발자 리소스</a> </li>
     <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=ko-KR" format="https" scope="external"> 기존 Adobe Analytics에서 데이터를 수집하고 사용하는 방법에 대한 빠른 시작 안내서
     <li><a href="https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR" format="https" scope="external"> 보고서 세트 데이터용 Adobe Analytics 소스 커넥터</a> </li>
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
