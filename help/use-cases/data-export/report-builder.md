---
title: Customer Journey Analytics Report Builder
description: Report Builder을 사용하여 반복 보고를 위해 Customer Journey Analytics 데이터를 Excel로 가져오는 방법에 대해 설명합니다.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 2%
---

# Report Builder

이 문서에서는 [!DNL Report Builder]을(를) 사용하여 다음 [데이터 내보내기 사용 사례](overview.md)를 구현하는 방법에 대해 간략히 설명합니다.

* 애드혹 및 반복 보고

## 소개

[!DNL Report Builder] [!DNL Report Builder]은(는) Customer Journey Analytics 데이터를 통합 문서의 데이터 블록으로 가져오는 Microsoft Excel 추가 기능입니다. 이미 Excel에 익숙한 비즈니스 사용자는 Analysis Workspace 또는 SQL을 배우지 않고도 반복 보고서를 작성할 수 있습니다.

## 추가 정보

[!DNL Report Builder]의 각 데이터 블록은 최대 50,000개의 행을 반환합니다. 더 많은 행을 검색하려면 **[!UICONTROL Page]** 및 **[!UICONTROL Rows]** 옵션을 사용하여 50,000행 제한을 초과하여 순차적 페이지에서 데이터를 가져옵니다. 자세한 내용은 [차원 필터링](/help/report-builder/filter-dimensions.md)을 참조하십시오.

통합 문서를 이메일로 전달하도록 예약하거나 Amazon S3, Google Cloud Platform 또는 Azure과 같은 클라우드 대상으로 내보낼 수 있습니다. 자세한 내용은 [이메일을 통해 공유하여 통합 문서 예약](/help/report-builder/schedule-reportbuilder.md) 및 [클라우드 대상으로 내보내 통합 문서 예약](/help/report-builder/report-builder-export.md)을 참조하십시오.

[!DNL Report Builder] 설정 및 사용에 대한 소개는 [Report Builder 개요](/help/report-builder/rb-overview.md)를 참조하십시오.
