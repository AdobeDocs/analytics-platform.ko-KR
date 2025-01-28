---
title: Customer Journey Analytics으로 업그레이드할 때 Adobe Analytics 기능 지원 이해
description: Customer Journey Analytics으로 업그레이드할 때 Adobe Analytics 기능 지원에 대해 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 1460cbd05cce793b25d026c413744508ab951147
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 29%

---

# Customer Journey Analytics으로 업그레이드할 때 Adobe Analytics 기능 지원 이해 {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="구성 요소 및 프로젝트"
>abstract="Adobe Analytics의 구성 요소에는 프로젝트(관련 자유 형식 테이블 및 시각화), 세그먼트 및 계산된 지표가 포함됩니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Activity Map 오버레이 및 링크 추적"
>abstract="링크 추적 데이터를 사이트에 오버레이로 표시할 수 있는 브라우저 확장입니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="분류 데이터"
>abstract="데이터를 별도의 차원으로 그룹화하거나 범주화합니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="마케팅 채널"
>abstract="고객이 사이트에 도착하는 방법을 분류하는 규칙을 만듭니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="데이터 피드"
>abstract="외부 도구 및 프로세스에서 사용하기 위해 Adobe Analytics에서 원시 데이터를 내보냅니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="처리된 데이터를 Adobe Analytics에서 스프레드시트 형식으로 내보냅니다."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="스트리밍 미디어 데이터"
>abstract="오디오, 비디오 또는 스트리밍되는 콘텐츠와 같은 미디어의 데이터 수집을 전문으로 하는 Adobe Analytics의 추가 기능입니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>[Customer Journey Analytics 업그레이드 확인 목록](https://gigazelle.github.io/cja-ttv/)의 질문에 답변할 때 이 페이지의 정보를 사용하십시오.

다음 목록은 [Customer Journey Analytics 업그레이드 검사 목록](https://gigazelle.github.io/cja-ttv/)에 포함된 기능만 표시합니다. Customer Journey Analytics에서 지원되거나, 부분적으로 지원되거나, 지원되지 않는 Adobe Analytics 기능을 보여 주는 포괄적인 목록을 보려면 [기능 지원 Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)을 참조하십시오.

Customer Journey Analytics으로 업그레이드할 때 다음 Adobe Analytics 기능 중 계속 사용할 기능을 고려하십시오.

| Adobe Analytics 기능 | Customer Journey Analytics의 해당 기능 |
|---------|----------|
| [Adobe Analytics의 구성 요소 및 프로젝트](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [프로젝트와 관련 구성 요소를 Customer Journey Analytics으로 마이그레이션](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). |
| [Activity Map 오버레이 및 링크 추적](https://experienceleague.adobe.com/en/docs/analytics/analyze/activity-map/overview) | 아직 사용할 수 없음 |
| [분류 데이터](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/c-classifications) | 조회 데이터 세트는 Customer Journey Analytics에서 데이터를 분류하는 방법입니다.<p>[분류 데이터를 포함하는 각 차원에 대한 조회 데이터 집합을 만듭니다.](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p> |
| [마케팅 채널](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | 파생된 필드는 데이터 보기 내에 만들어집니다. <p>[마케팅 채널 파생 필드를 만듭니다.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> |
| [데이터 피드](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | 데이터 세트의 1세대 데이터 내보내기는 [Experience Platform 데이터 액세스 API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html)와 [Experience Platform 대상](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html)을 통해 사용할 수 있습니다. 이러한 옵션은 수집되거나 Experience Platform Data Lake에 수집된 모든 데이터의 이벤트/행 수준 내보내기를 제공합니다. 이후 열은 쿼리 시간에 계산되므로 후 처리 데이터 열을 사용할 수 없습니다. 이후 열 내보내기는 보고를 통해 사용할 수 있습니다. |
| [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | [Customer Journey Analytics 전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md)는 현재 Data Warehouse에서 사용할 수 없지만 자주 요청되는 새로운 기능을 다수 포함하는 Adobe Analytics의 Data Warehouse 보고서에 대한 개선 사항입니다. |
| [스트리밍 미디어 데이터](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-overview) | 스트리밍 미디어 데이터는 Analytics 소스 커넥터를 미디어 동시 뷰어 패널 및 작업 영역의 미디어 재생 소요 시간 패널의 일부로 사용할 수 있습니다. |

