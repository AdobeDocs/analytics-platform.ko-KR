---
description: Analysis Workspace에서 내보내기에 사용할 수 있는 다양한 방법을 이해합니다.
keywords: Analysis Workspace
title: 프로젝트 데이터 내보내기 개요
feature: Curate and Share
hide: true
hidefromtoc: true
source-git-commit: eb7ba8dd7809164bdcddb0d484754376d5b7ca9e
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# 내보내기 개요

Analysis Workspace에서 Customer Journey Analytics 보고서를 내보낼 수 있습니다. 타사 도구에서 을 활용하거나 외부 데이터와 결합하는 것과 같은 여러 가지 이유로 Customer Journey Analytics 보고서를 내보낼 수 있습니다.

다음 섹션에서는 지원되는 파일 유형, 내보내기에 사용할 수 있는 다양한 방법 및 각 방법의 장점에 대해 설명합니다.

## 지원되는 파일 유형

Customer Journey Analytics 보고서를 PDF, CSV 또는 JSON 파일로 내보낼 수 있습니다.

* **PDF:** 이해 당사자와 시각적 데이터를 쉽게 공유할 수 있는 방법을 제공합니다. PDF 파일에는 프로젝트에 표시된 (볼 수 있는) 모든 테이블과 시각화가 포함되어 있습니다.

* **CSV:** Excel과 같은 스프레드시트 애플리케이션에서 원시 데이터를 볼 수 있습니다. CSV 파일에는 일반 텍스트 데이터가 포함되어 있습니다.

* **JSON:** 데이터 공유를 위한 개방형 표준 파일 형식을 제공합니다.

## 내보내기 방법

Analysis Workspace에서 내보낼 때 사용할 수 있는 메서드는 다양합니다. 내보내기 방법을 선택할 때는 내보낼 항목과 해당 방법에 액세스해야 하는 사용자를 고려하십시오.

| 내보내기 방법 | 장점 |
|---------|----------|
| [워크스테이션에 다운로드](/help/analysis-workspace/export/download-send.md) | 다음 작업을 수행하려면 이 메서드를 사용하십시오. <ul><li>개인 워크스테이션에 프로젝트를 다운로드합니다.</li><li>다운로드는 애드혹 전용(예약할 수 없음)</li> <li>총 50,000개의 행을 다운로드합니다.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [다른 사용자에게 보내기](/help/analysis-workspace/export/t-schedule-report.md) | 다음 작업을 수행하려면 이 메서드를 사용하십시오. <ul><li>이메일이 조직의 다른 사용자에게 내보낸 Customer Journey Analytics 데이터입니다.</li><li>애드혹 또는 일정에 포함될 수 있습니다.</li> <li>총 50,000개의 행을 포함합니다.</li> <!--true?--> |
| [클라우드 애플리케이션으로 보내기](/help/analysis-workspace/export/export-cloud.md) | 다음 작업을 수행하려면 이 메서드를 사용하십시오. <ul><li>Adobe Experience Platform 데이터 랜딩 영역, Google Cloud Platform, Microsoft Azure, Amazon S3 또는 Snowflake과 같은 공유 위치로 내보냅니다.</li><li>애드혹 또는 일정에 포함될 수 있습니다.</li><li>더 많은 양의 Customer Journey Analytics 데이터를 저장합니다.</li><li>수천 또는 수백만 개의 행이 포함된 전체 테이블을 내보냅니다.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}

