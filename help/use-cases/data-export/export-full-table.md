---
title: Customer Journey Analytics 내보내기 전체 테이블
description: 전체 표 내보내기 기능을 사용하여 데이터의 유효성을 검사하거나 데이터를 AI/ML에 사용하는 방법에 대해 설명합니다.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: ee004948-3025-434b-a90b-8aa185800820
autotag-review: '2026-05-19T09:39:35.989Z'
TQID: 'https://experienceleague.adobe.com/5lP3PKpCpxkeyH34327gieZ48KFkEai4DF2SC0H4E2U'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: f24857a4-4b64-4b25-b237-d43026362144
    internal-label: BI extension
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 4%
---
# 전체 테이블 내보내기

이 문서에서는 [!DNL Export full table] 기능을 사용하여 다음 [데이터 내보내기 사용 사례](overview.md)를 구현하는 방법에 대해 간략히 설명합니다.

* 데이터 유효성 검사
* AI/ML 준비 완료

## 소개

[!DNL Customer Journey Analytics Full Table Export]을(를) 사용하여 데이터를 내보내면 Customer Journey Analytics Analysis Workspace의 자유 형식 테이블에서 데이터를 내보낼 수 있습니다.

![BI 확장](../assets/export-full-table.png)

## 추가 정보

Analysis Workspace에서 만든 자유 형식 테이블의 전체 컨텐츠를 지정된 클라우드 대상으로 직접 내보내려면 전체 테이블 내보내기 기능을 사용하십시오.

전체 테이블 내보내기는 보고서당 최대 10개의 차원과 10개의 지표를 지원하며 계산된 지표 및 세그멘테이션을 포함합니다. 라이선스 계층에 따라 내보내기당 300만, 3000만, 1억 5000만 또는 3억 개의 행을 내보낼 수 있으며 다른 내보내기 방법의 5만 행 제한을 초과할 수 있습니다. 지원되는 대상에는 Adobe Experience Platform 데이터 랜딩 영역, Google Cloud Platform, Microsoft Azure, Amazon S3 및 Snowflake이 있습니다. 자세한 내용은 [전체 테이블 내보내기의 이점](/help/analysis-workspace/export/export-cloud.md#advantages)을 참조하십시오.

자세한 내용은 [클라우드로 Customer Journey Analytics 보고서 내보내기](/help/analysis-workspace/export/export-cloud.md)에 대한 자세한 설명서를 참조하십시오.
