---
description: Analysis Workspace에서 내보내는 데 사용할 수 있는 방법을 알아봅니다.
keywords: Analysis Workspace
title: 프로젝트 데이터를 내보내는 방법
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '304'
ht-degree: 100%

---

# 내보내기 개요

Analysis Workspace에서 Customer Journey Analytics 보고서를 내보낼 수 있습니다. 서드파티 도구를 활용하거나 외부 데이터와 결합하는 등 다양한 이유로 Customer Journey Analytics 보고서를 내보내고 싶을 수 있습니다.

다음 섹션에서는 지원되는 파일 유형, 사용 가능한 다양한 내보내기 방법, 각 방법의 장점에 대해 설명합니다.

## 지원되는 파일 유형

Customer Journey Analytics 보고서를 PDF, CSV 또는 JSON 파일로 내보낼 수 있습니다.

* **PDF:** 관련자들과 시각적 데이터를 쉽게 공유할 수 있는 방법을 제공합니다. PDF 파일에는 프로젝트에 표시된 (볼 수 있는) 모든 테이블과 시각화가 포함됩니다.

* **CSV:** Excel과 같은 스프레드시트 애플리케이션에서 원시 데이터를 볼 수 있습니다. CSV 파일에는 일반 텍스트 데이터가 포함됩니다.

* **JSON:** 데이터 공유를 위한 개방형 표준 파일 형식입니다.

## 내보내기 방법

Analysis Workspace에서 내보낼 때 다양한 방법을 사용할 수 있습니다. 내보내기 방법을 선택할 때 무엇을 내보내고 싶은지와 누가 접근해야 하는지 고려합니다.

| 내보내기 방법 | 장점 |
|---------|----------|
| [워크스테이션에 다운로드](/help/analysis-workspace/export/download-send.md) | 다음과 같은 경우 이 방법을 사용합니다. <ul><li>개인 워크스테이션에 프로젝트를 다운로드합니다.</li><li>다운로드는 임시로만 가능합니다(예약할 수 없음).</li> <li>총 50,000개의 행을 다운로드합니다.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [다른 사용자에게 보내기](/help/analysis-workspace/export/t-schedule-report.md) | 다음과 같은 경우 이 방법을 사용합니다. <ul><li>내보내기 한 Customer Journey Analytics 데이터를 조직의 다른 사용자에게 이메일로 보냅니다.</li><li>임시적이거나 일정에 따라 이루어질 수 있습니다.</li> <li>총 50,000개의 행을 포함합니다.</li> <!--true?--> |
| [클라우드 애플리케이션으로 보내기](/help/analysis-workspace/export/export-cloud.md) | 다음과 같은 경우 이 방법을 사용합니다. <ul><li>Adobe Experience Platform 데이터 랜딩 영역, Google Cloud Platform, Microsoft Azure, Amazon S3 또는 Snowflake와 같은 공유 위치로 내보냅니다.</li><li>임시적이거나 일정에 따라 이루어질 수 있습니다.</li><li>더 많은 양의 Customer Journey Analytics 데이터를 저장합니다.</li><li>수천 또는 수백만 개의 행이 포함된 전체 테이블을 내보냅니다.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
