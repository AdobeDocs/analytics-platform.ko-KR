---
title: Adobe Analytics 기능 지원을 이해하고 Customer Journey Analytics로 업그레이드하기
description: Adobe Analytics 기능 지원을 이해하고 Customer Journey Analytics로 업그레이드하는 방법에 대해 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 88%

---

# Adobe Analytics 기능 지원을 이해하고 Customer Journey Analytics로 업그레이드하기 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="구성 요소 및 프로젝트"
>abstract="Adobe Analytics의 구성 요소에는 프로젝트(연관된 자유 형식 테이블 및 시각화 포함), 세그먼트, 계산된 지표가 포함됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="활동 맵 오버레이 및 링크 추적"
>abstract="사이트에서 링크 추적 데이터를 오버레이 형태로 확인할 수 있도록 하는 브라우저 확장 기능입니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map-support"
>title="Activity Map 오버레이는 아직 지원되지 않습니다."
>abstract="Customer Journey Analytics에서는 아직 Activity Map 오버레이가 지원되지 않습니다. 향후에 제공될 예정입니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="분류 데이터"
>abstract="데이터를 별도의 차원으로 그룹화하거나 분류합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="마케팅 채널"
>abstract="고객이 사이트에 유입되는 방식을 분류하는 규칙을 생성합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="데이터 피드"
>abstract="외부 도구 및 프로세스에서 사용할 수 있도록 Adobe Analytics의 원시 데이터를 내보냅니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="Adobe Analytics에서 처리된 데이터를 스프레드시트 형식으로 내보냅니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="스트리밍 미디어 데이터"
>abstract="오디오, 비디오 또는 스트리밍 콘텐츠와 같은 미디어의 데이터 수집을 전문으로 수행하는 Adobe Analytics 및 Customer Journey Analytics의 추가 기능입니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="프로젝트 및 구성 요소 마이그레이션"
>abstract="Adobe Analytics 프로젝트 및 관련 모든 구성 요소를 Customer Journey Analytics로 가져옵니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

다음 목록은 Customer Journey Analytics로 업그레이드 프로세스 중에 고려해야 할 Adobe Analytics 기능만 보여 줍니다. Customer Journey Analytics에서 전체적으로 지원되는 Adobe Analytics 기능, 부분적으로 지원되는 기능 또는 지원되지 않는 기능을 보여 주는 포괄적인 목록을 확인하려면 [Customer Journey Analytics 기능 지원](/help/getting-started/aa-vs-cja/cja-aa.md)을 참조하십시오.

Customer Journey Analytics로 업그레이드할 때 계속 사용하고자 하는 Adobe Analytics 기능을 다음 중 고려해야 합니다.

| Adobe Analytics 기능 | Customer Journey Analytics의 해당 기능 |
|---------|----------|
| [Adobe Analytics의 구성 요소 및 프로젝트](https://experienceleague.adobe.com/ko/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [프로젝트와 관련 구성 요소를 Customer Journey Analytics로 마이그레이션](https://experienceleague.adobe.com/ko/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). |
| [활동 맵 오버레이 및 링크 추적](https://experienceleague.adobe.com/ko/docs/analytics/analyze/activity-map/overview) | 아직 사용할 수 없음 |
| [분류 데이터](https://experienceleague.adobe.com/ko/docs/analytics/components/classifications/c-classifications) | 조회 데이터 세트는 Customer Journey Analytics에서 데이터를 분류하는 방법입니다.<p>[분류 데이터를 포함하는 각 차원에 대한 조회 데이터 세트 만들기.](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [마케팅 채널](https://experienceleague.adobe.com/ko/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | 파생 필드는 데이터 보기 내에서 생성됩니다. <p>[마케팅 채널 파생 필드 만들기.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [데이터 피드](https://experienceleague.adobe.com/ko/docs/analytics/export/analytics-data-feed/data-feed-overview) | Experience Platform 및 Customer Journey Analytics은 독립적으로 또는 결합하여 다양한 내보내기 요구 사항을 해결할 수 있는 다양한 기능을 제공합니다. 이러한 기능에는 [Experience Platform 데이터 액세스 API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html), [Experience Platform 대상](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html), [Customer Journey Analytics 전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md) 및 [BI 도구 통합](/help/data-views/bi-extension.md)이 포함됩니다.<p>내보내기 옵션에 대한 자세한 내용은 [데이터 내보내기 사용 사례](/help/use-cases/data-export/overview.md)를 참조하십시오.</p> |
| [Data Warehouse](https://experienceleague.adobe.com/ko/docs/analytics/export/data-warehouse/data-warehouse) | [Customer Journey Analytics 전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md)는 현재 Data Warehouse에서 사용할 수 없지만 자주 요청되는 새로운 기능을 다수 포함하는 Adobe Analytics의 Data Warehouse 보고서에 대한 개선 사항입니다. |
| [스트리밍 미디어 데이터](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-overview) | 스트리밍 미디어 데이터는 Analytics 소스 커넥터를 미디어 동시 시청자 패널 및 Workspace의 미디어 재생 소요 시간 패널의 일부로 사용할 수 있습니다. |
