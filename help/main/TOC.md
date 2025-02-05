---
git-repo: https://github.com/AdobeDocs/analytics-platform.ko-KR
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Customer Journey Analytics 안내서
user-guide-description: Adobe Customer Journey Analytics란 무엇이며 Experience Platform의 데이터와 함께 Analysis Workspace를 사용하는 방법에 대해 알아봅니다.
breadcrumb-title: Customer Journey Analytics 안내서
source-git-commit: 0c4741a003954a739c4ce85cf04badeeb502193c
workflow-type: tm+mt
source-wordcount: '1120'
ht-degree: 99%

---

# Adobe Customer Journey Analytics 안내서 {#using}

+ [Adobe Customer Journey Analytics 안내서](../getting-started/cja-landing.md)
+ [Adobe Customer Journey Analytics용 AI 어시스턴트](../ai-assistant.md)
+ [Customer Journey Analytics용 데이터 분석 AI 어시스턴트](../data-analysis-ai.md)

+ 릴리스 정보 {#releases}
   + [최신 릴리스](../release-notes/latest.md)
   + [2024년 릴리스](../release-notes/2024.md)
   + [2023년 릴리스](../release-notes/2023.md)
   + [2022년 릴리스](../release-notes/2022.md)
   + [2021년 릴리스](../release-notes/2021.md)
   + [2020년 릴리스](../release-notes/2020.md)
   + [기능 릴리스 전략](../release-notes/releases.md)
   + [설명서 업데이트](../release-notes/doc-changes.md)

+ 시작하기 {#cja-overview}
   + [Customer Journey Analytics 개요](../getting-started/cja-overview.md)
   + [빠른 시작 안내서](../getting-started/cja-getting-started.md)
   + [랜딩 페이지](../getting-started/landing.md)
   + [랜딩 페이지 (이전)](../getting-started/cja-landing-old.md)
   + [자주 묻는 질문](../getting-started/cja-faq.md)
   + [Customer Journey Analytics와 BI 솔루션 비교](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics와 Adobe Analytics 비교 {#compare-aa-cja}
   + Customer Journey Analytics로 업그레이드 {#upgrade-to-cja}
      + [시작](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
      + [업그레이드 경로 선택](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
      + [Platform으로 데이터 전송](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
      + [내역 데이터 유지](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
      + [추천 프로세스](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)
      + [Analytics 구현 이해](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md)
      + [분류를 위한 조회 데이터 세트 만들기](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)
      + [데이터 세트 수집 모니터링](/help/getting-started/cja-upgrade/cja-upgrade-dataset-ingestion.md)
      + [마케팅 채널 파생 필드 만들기](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)
      + [Web SDK 확장 기능용 로더 태그 구현](/help/getting-started/cja-upgrade/cja-upgrade-tag-loader.md)
      + [속성용 태그 만들기](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md)
      + [태그에 Web SDK 확장 기능 추가](/help/getting-started/cja-upgrade/cja-upgrade-tag-extension.md)
      + [태그에 XDM 데이터 수집 논리 추가](/help/getting-started/cja-upgrade/cja-upgrade-tag-xdm.md)
      + [스키마 설계](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)
      + [스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)
      + [기존 스키마 사용](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)
      + [데이터 세트 만들기](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)
      + [datastream 만들기](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)
      + [서비스로 플랫폼 추가](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)
      + [연결 만들기](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)
      + [데이터 보기 만들기](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)
      + [데이터 흐름 유효성 검사](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)
      + [업그레이드 단축키: Web SDK로 마이그레이션](/help/getting-started/cja-upgrade/cja-upgrade-shortcut-websdk.md)
      + [Analytics 소스 커넥터용 XDM 스키마 만들기](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)
      + [Analytics 소스 커넥터 및 맵 필드 만들기](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)
      + [연결에 Analytics 소스 커넥터 데이터 세트 추가](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md)
      + [Analytics 소스 커넥터만 사용](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md)
      + [Analytics 소스 커넥터에서 Web SDK로 이동](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)
      + [AppMeasurement 데이터 수집 비활성화](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md)
      + [서드파티 분석 솔루션에서 업그레이드](/help/getting-started/cja-upgrade/cja-upgrade-third-party-solution.md)
      + [업그레이드 시 Adobe Analytics 기능 지원](/help/getting-started/cja-upgrade/cja-upgrade-adobe-analytics-features.md)
   + Adobe Analytics와의 비교 {#cja-aa-comparison}
      + [개요](../getting-started/aa-vs-cja/overview.md)
      + [Adobe Analytics 데이터 사용](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [기능 지원](../getting-started/aa-vs-cja/cja-aa.md)
      + [용어 비교](../getting-started/aa-vs-cja/terminology.md)
      + [데이터 처리 비교](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [환경](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [Analytics 처리와 데이터 준비 비교](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [Analytics ID](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
   + [Adobe Analytics의 발전](../getting-started/aa-to-cja.md)
   + [Adobe Analytics 사용자를 위한 사용 안내서](../getting-started/aa-to-cja-user.md)

+ 데이터 수집 {#cja-data-ingestion}
   + [데이터 수집 개요](../data-ingestion/data-ingestion.md)
   + 빠른 시작 안내서 수집 및 사용{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + Experience Platform Edge Network {#edge-network}
         + [Web SDK](../data-ingestion/aepwebsdk.md)
         + [Mobile SDK](../data-ingestion/aepmobilesdk.md)
         + [서버 API](../data-ingestion/serverapi.md)
      + [배치 데이터](../data-ingestion/batch.md)
      + [스트리밍 데이터](../data-ingestion/streaming.md)
      + [소스 커넥터](../data-ingestion/sources.md)

+ 연결 {#cja-connections}
   + [연결 개요](../connections/overview.md)
   + [연결 만들기 또는 편집](../connections/create-connection.md)
   + [연결 관리](../connections/manage-connections.md)
   + [결합된 이벤트 데이터 세트](../connections/combined-dataset.md)
   + [표준 조회](../connections/standard-lookups.md)
   + [B2B 조회](../connections/transform-datasets-b2b-lookups.md)

+ 데이터 보기 {#cja-dataviews}
   + [데이터 보기 개요](../data-views/data-views.md)
   + [데이터 보기 만들기 또는 편집](../data-views/create-dataview.md)
   + [세션 설정](../data-views/session-settings.md)
   + 구성 요소 설정 {#component-settings}
      + [구성 요소 설정 개요](../data-views/component-settings/overview.md)
      + [속성](../data-views/component-settings/attribution.md)
      + [비헤이비어](../data-views/component-settings/behavior.md)
      + [포맷](../data-views/component-settings/format.md)
      + [포함/제외 값](../data-views/component-settings/include-exclude-values.md)
      + [지표 중복 제거](../data-views/component-settings/metric-deduplication.md)
      + [값 옵션 없음](../data-views/component-settings/no-value-options.md)
      + [지속성](../data-views/component-settings/persistence.md)
      + [하위 문자열](../data-views/component-settings/substring.md)
      + [요약 데이터 그룹](../data-views/component-settings/summary-data-group.md)
      + [값 버킷팅](../data-views/component-settings/value-bucketing.md)
   + [표준 구성 요소 참조](../data-views/component-reference.md)
   + [BI 확장 기능](../data-views/bi-extension.md)
   + [파생 필드](../data-views/derived-fields/derived-fields.md)
   + [요약 데이터](../data-views/summary-data.md)
   + [레이블 및 정책](../data-views/data-governance.md)

+ 도구 {#tools}
   + 자산 이전 {#asset-transfer}
      + [자산 전송](../tools/asset-transfer/transfer-assets.md)
   + 제품 사용 {#product-usage}
      + [개요](../tools/product-usage/usage-overview.md)
      + [데이터 설정](../tools/product-usage/data-settings.md)
      + [옵트아웃 설정](../tools/product-usage/opt-out-settings.md)

+ 작업 영역 프로젝트 {#cja-workspace}
   + [Analysis Workspace 개요](../analysis-workspace/home.md)
   + [기본 분석 수행](../analysis-workspace/perform-basic-analysis.md)
   + [고급 분석 수행](../analysis-workspace/perform-adv-analysis.md)
   + 프로젝트 {#build-workspace-project}
      + [개요](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [프로젝트 만들기](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [프로젝트 열기](/help/analysis-workspace/build-workspace-project/open-projects.md)
      + [프로젝트 저장](../analysis-workspace/build-workspace-project/save-projects.md)
      + 작업 영역의 폴더 {#workspace-folders}
         + [폴더 정보](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [폴더 및 하위 폴더 만들기](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [폴더 관리](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
         + [프로젝트를 추가하거나 폴더로 이동](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
      + [핫키 (단축키)](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [색상 팔레트](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [보기 밀도](../analysis-workspace/build-workspace-project/view-density.md)
   + 템플릿 {#templates}
      + [템플릿 사용](../analysis-workspace/templates/use-templates.md)
      + [템플릿 만들기 및 관리](../analysis-workspace/templates/create-templates.md)
   + 시각화 {#visualizations}
      + [개요](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [데이터 소스 관리](../analysis-workspace/visualizations/t-sync-visualization.md)
      + [인텔리전트 캡션](../analysis-workspace/visualizations/intelligent-captions.md)
      + 자유 형식 테이블 {#freeform-table}
         + [개요](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + [하이퍼링크 만들기](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
         + 열 및 행 설정 {#column-row-settings}
            + [열 설정](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [행 설정](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [동적 및 정적 항목](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [테이블 필터링 및 정렬](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
         + [작업 영역 합계](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + 코호트 테이블 {#cohort-table}
         + [개요](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [구성](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [사용 사례](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + 폴아웃 {#fallout}
         + [개요](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [구성](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [차원 간 폴아웃](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [필터 적용](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + 흐름 {#flow}
         + [개요](../analysis-workspace/visualizations/c-flow/flow.md)
         + [구성](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [차원 간 흐름](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + 여정 캔버스 {#journey-canvas}
         + [개요](../analysis-workspace/visualizations/journey-canvas/journey-canvas.md)
         + [구성](../analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)
         + [문제 해결](../analysis-workspace/visualizations/journey-canvas/journey-canvas-troubleshooting.md)
      + [영역 (누적)](../analysis-workspace/visualizations/area.md)
      + [막대 (누적)](../analysis-workspace/visualizations/bar.md)
      + [글머리 기호](../analysis-workspace/visualizations/bullet-graph.md)
      + [콤보](../analysis-workspace/visualizations/combo-charts.md)
      + [도넛](../analysis-workspace/visualizations/donut.md)
      + [히스토그램](../analysis-workspace/visualizations/histogram.md)
      + [가로 막대 (누적)](../analysis-workspace/visualizations/horizontal-bar.md)
      + [주요 지표 요약](../analysis-workspace/visualizations/key-metric.md)
      + [라인](../analysis-workspace/visualizations/line.md)
      + [맵](/help/analysis-workspace/visualizations/map.md)
      + [분산](../analysis-workspace/visualizations/scatterplot.md)
      + [섹션 헤더](/help/analysis-workspace/visualizations/section-header.md)
      + [요약 번호 및 변경 사항](../analysis-workspace/visualizations/summary-number-change.md)
      + [텍스트](../analysis-workspace/visualizations/text.md)
      + [트리 맵](../analysis-workspace/visualizations/treemap.md)
      + [벤](../analysis-workspace/visualizations/venn.md)
   + 패널 {#panels}
      + [개요](../analysis-workspace/c-panels/panels.md)
      + [빈 패널](../analysis-workspace/c-panels/blank-panel.md)
      + [속성](../analysis-workspace/c-panels/attribution.md)
      + [실험](../analysis-workspace/c-panels/experimentation.md)
      + [자유 형식](../analysis-workspace/c-panels/freeform-panel.md)
      + [미디어 평균 분당 시청 대상자](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
      + [미디어 동시 뷰어](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + [미디어 재생 체류 시간](../analysis-workspace/c-panels/media-playback-time-spent.md)
      + [다음 또는 이전 항목](../analysis-workspace/c-panels/next-previous.md)
      + [빠른 인사이트](../analysis-workspace/c-panels/quickinsight.md)
   + 프로젝트 구성, 공유 및 예약 {#curate-share}
      + [개요](../analysis-workspace/curate-share/send-schedule-files.md)
      + [프로젝트 구성](../analysis-workspace/curate-share/curate.md)
      + [프로젝트 공유](../analysis-workspace/curate-share/share-projects.md)
      + [공유 가능한 링크 만들기](../analysis-workspace/curate-share/shareable-links.md)
      + [보기 전용 프로젝트](../analysis-workspace/curate-share/view-only-projects.md)
   + 내보내기 {#export}
      + [개요](../analysis-workspace/export/export-project-overview.md)
      + [다운로드](../analysis-workspace/export/download-send.md)
      + [다른 사람에게 보내기](../analysis-workspace/export/t-schedule-report.md)
      + [클라우드로 내보내기](../analysis-workspace/export/export-cloud.md)
   + 예외 항목 탐지 {#anomaly-detection}
      + [개요](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
      + [예외 항목 보기](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
      + [통계 기법](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
   + 예측 {#forecasting}
      + [개요](../analysis-workspace/c-forecast/forecasting.md)
      + [예측 보기](../analysis-workspace/c-forecast/view-forecasts.md)
      + [통계 기법](../analysis-workspace/c-forecast/statistics-forecasting.md)
   + [목차](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
   + [사용자 환경 설정](../analysis-workspace/user-preferences.md)
   + Workspace FAQ 및 기타 {#workspace-faq}
      + [자주 묻는 질문](../analysis-workspace/workspace-faq/faq.md)
      + [오류 메시지](../analysis-workspace/workspace-faq/error-messages.md)
      + [제한 사항](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [관리 요구 사항](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [접근성](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ 콘텐츠 분석 {#content-analytics}
   + [개요](/help/content-analytics/content-analytics.md)
   + 구성 {#configuration}
      + [개요](/help/content-analytics/config/configuration.md)
      + [안내식 구성](/help/content-analytics/config/guided.md)
      + [수동 구성](/help/content-analytics/config/manual.md)

+ Analytics 대시보드 {#cja-dashboards}
   + [개요](../mobile-app/home.md)
   + [큐레이터 작업](../mobile-app/curator.md)
   + [모바일 스코어카드 만들기](../mobile-app/create-scorecard.md)
   + [모바일 스코어카드 관리](../mobile-app/manage-scorecard.md)
   + [경영진이 대시보드를 사용할 수 있도록 설정](../mobile-app/set-up-execs.md)
   + [경영진 빠른 시작 안내서](../mobile-app/executive.md)

+ 가이드 분석 {#guided-analysis}
   + [개요](../guided-analysis/overview.md)
   + [활성 증가](../guided-analysis/types/active-growth.md)
   + [전환 트렌드](../guided-analysis/types/conversion-trends.md)
   + [참여](../guided-analysis/types/engagement.md)
   + [최초 사용 영향](../guided-analysis/types/first-use-impact.md)
   + [빈도](../guided-analysis/types/frequency.md)
   + [단계](../guided-analysis/types/funnel.md)
   + [순성장](../guided-analysis/types/net-growth.md)
   + [릴리스 영향](../guided-analysis/types/release-impact.md)
   + [유지](../guided-analysis/types/retention.md)
   + [타임라인](../guided-analysis/types/timeline.md)
   + [트렌드](../guided-analysis/types/trends.md)
   + [업계 사용 사례](../guided-analysis/industry-use-cases.md)
   + [FAQ](../guided-analysis/faq.md)

+ 구성 요소 {#cja-components}
   + [개요](../components/overview.md)
   + [Analysis Workspace의 구성 요소 사용](../components/use-components-in-workspace.md)
   + [구성 요소 설명 추가](../components/add-component-descriptions.md)
   + 주석 {#annotations}
      + [주석 개요](../components/annotations/overview.md)
      + [주석 만들기](../components/annotations/create-annotations.md)
      + [주석 관리](../components/annotations/manage-annotations.md)
      + [주석 보기](../components/annotations/view-annotations.md)
      + [모바일 주석](../components/annotations/mobile-annotations.md)
   + [예약된 프로젝트](../components/scheduled-projects-manager.md)
   + 대상자 {#audiences}
      + [대상자 개요](../components/audiences/audiences-overview.md)
      + [대상자 생성 및 게시](../components/audiences/publish.md)
      + [대상자 관리](../components/audiences/manage.md)
   + 차원 {#dimensions}
      + [차원 개요](../components/dimensions/overview.md)
      + [차원 미리보기](../components/dimensions/view-dimensions.md)
      + [차원 분류](../components/dimensions/t-breakdown-fa.md)
      + [차원 시간 분할](../components/dimensions/time-parting-dimensions.md)
      + [높은 카디널리티 차원](../components/dimensions/high-cardinality.md)
   + [지표](../components/apply-create-metrics.md)
   + 필터 {#cja-filters}
      + [개요](../components/filters/filters-overview.md)
      + [필터 만들기](../components/filters/create-filters.md)
      + [필터 빌드](../components/filters/filter-builder.md)
      + [빠른 필터](../components/filters/quick-filters.md)
      + [순차적 필터](../components/filters/seg-sequential-build.md)
      + [필터 공유](../components/filters/filters-share.md)
      + [필터 태그 지정](../components/filters/filters-tag.md)
      + [필터 목록 필터링](../components/filters/filters-filter.md)
      + [필터를 즐겨찾기로 표시](../components/filters/filters-favorite.md)
      + [필터 승인](../components/filters/filters-approve.md)
      + [필터 복사](../components/filters/filters-copy.md)
      + [필터 관리](../components/filters/manage-filters.md)
      + [연산자](../components/filters/operators.md)
   + 계산된 지표 {#cja-calcmetrics}
      + [개요](../components/calc-metrics/calc-metr-overview.md)
      + 계산된 지표 워크플로 {#cm-workflow}
         + [계산된 지표 만들기](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [계산된 지표 작성](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [지표 찾기](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [지표 유형 및 속성](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [참여도 지표 빌드](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [필터링된 지표](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [필터 스택 및 바꾸기](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [계산된 지표 필터링](../components/calc-metrics/cm-workflow/cm-filter.md)
         + [계산된 지표를 즐겨찾기로 표시](../components/calc-metrics/cm-workflow/cm-favorite.md)
         + [계산된 지표 복사](../components/calc-metrics/cm-workflow/cm-copy.md)
         + [함수 사용](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [계산된 지표 태그 지정](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [계산된 지표 승인](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [계산된 지표 공유](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [계산된 지표 관리](../components/calc-metrics/cm-workflow/cm-manager.md)
         + [예](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
      + [계산된 지표 템플릿](../components/calc-metrics/default-calcmetrics.md)
      + [기본 함수](../components/calc-metrics/cm-functions.md)
      + [고급 함수](../components/calc-metrics/cm-adv-functions.md)
   + 날짜 범위 {#cja-date-ranges}
      + [개요](../components/date-ranges/overview.md)
      + [날짜 범위 만들기](../components/date-ranges/create.md)
      + [날짜 범위 관리](../components/date-ranges/manage.md)
      + [날짜 비교](../components/date-ranges/time-comparison.md)
      + [예](../components/date-ranges/custom-date-ranges.md)
   + 경고 {#alerts}
      + [개요](/help/components/c-intelligent-alerts/intelligent-alerts.md)
      + [경고 만들기](/help/components/c-intelligent-alerts/alert-builder.md)
      + [경고 관리](/help/components/c-intelligent-alerts/alert-manager.md)
      + [기능 비교](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)
      + [사용 사례](/help/components/c-intelligent-alerts/alerts-use-cases.md)
   + 내보내기 {#exports}
      + [클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md)
      + [클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md)
      + [클라우드 내보내기 위치 관리](/help/components/exports/manage-export-locations.md)
      + [내보내기 관리](/help/components/exports/manage-exports.md)
      + [내보내기 로그 관리](/help/components/exports/manage-export-logs.md)
      + [내보내기 문제 해결](/help/components/exports/troubleshoot-exports.md)
   + 데이터 사전 {#data-dictionary}
      + [개요](../components/data-dictionary/data-dictionary-overview.md)
      + [데이터 사전의 구성 요소 정보 보기](../components/data-dictionary/view-data-dictionary.md)
      + [데이터 사전의 구성 요소 항목 편집](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [데이터 사전 상태 모니터링](../components/data-dictionary/monitor-data-dictionary-health.md)

+ Report Builder {#cja-reportbuilder}
   + [개요](../report-builder/report-buider-overview.md)
   + [Report Builder 설치](../report-builder/report-builder-setup.md)
   + [데이터 블록 만들기](../report-builder/create-a-data-block.md)
   + [Report Builder 허브](../report-builder/report-builder-hub.md)
   + [데이터 보기 선택](../report-builder/select-data-view.md)
   + [날짜 범위 선택](../report-builder/select-date-range.md)
   + [필터 작업](../report-builder/work-with-filters.md)
   + [차원 필터링](../report-builder/filter-dimensions.md)
   + [데이터 블록 관리](../report-builder/manage-reportbuilder.md)
   + [통합 문서 예약](../report-builder/schedule-reportbuilder.md)
   + [제한된 레이블](../report-builder/restricted-labels.md)
   + [Report Builder 설정](../report-builder/report-builder-settings.md)

+ 보고 활동 관리자 {#reporting-activity-manager}
   + [개요](../reporting-activity-manager/reporting-activity-overview.md)
   + [보고 활동 보기](../reporting-activity-manager/reporting-activity.md)
   + [보고 요청 취소](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ 결합 {#stitching}
   + [개요](/help/stitching/overview.md)
   + [필드 기반 스티칭](/help/stitching/fbs.md)
   + [그래프 기반 스티칭](/help/stitching/gbs.md)
   + [스티칭 사용](/help/stitching/use-stitching.md)
   + [결합된 데이터 세트 생성 및 관리](/help/stitching/stitching-ui.md)
   + [자주 묻는 질문](/help/stitching/faq.md)

+ Adobe 통합 {#integrations}
   + [개요](/help/integrations/overview.md)
   + [Adobe Analytics 통합](/help/integrations/aa.md)
   + [Target 통합](/help/integrations/at.md)
   + [Journey Optimizer 데이터 통합](/help/integrations/ajo.md)
   + [의사 결정 관리 데이터 통합](/help/integrations/ajo-od.md)
   + [고객 AI 통합](/help/integrations/customer-ai.md)

+ 데이터 거버넌스 {#cja-privacy}
   + [데이터 거버넌스](../privacy/privacy-overview.md)
   + [감사 로그](../privacy/audit-log.md)
   + [고객 관리 키](../privacy/cmk.md)

+ 사용 사례 {#cja-usecases}
   + [Customer Journey Analytics 사용 사례](../use-cases/cja-usecases.md)
   + Google Analytics 데이터 {#ga}
      + [Google Analytics에서 데이터 마이그레이션](../use-cases/ga/overview.md)
      + [Google Analytics 내역 데이터 수집](../use-cases/ga/backfill.md)
      + [스트리밍 Google Analytics 데이터 구성](../use-cases/ga/streaming.md)
      + [Google Analytics 데이터에 대한 보고](../use-cases/ga/report.md)
   + 데이터 수집 {#data-ingestion}
      + [Marketo Engage 데이터 수집 및 사용](../use-cases/data-ingestion/marketo.md)
      + [Experience Platform 대상자 수집 및 활용](../use-cases/data-ingestion/ingest-aep-segments.md)
   + 데이터 보기 {#data-views}
      + [데이터 보기 사용 사례](/help/use-cases/data-views/data-views-usecases.md)
      + [바인딩 차원 및 지표 사용](/help/use-cases/data-views/binding-dimensions-metrics.md)
      + [요약 데이터 사용](/help/use-cases/data-views/summary-data.md)
      + [BI 확장 기능 사용 사례](/help/use-cases/data-views/bi-extension-usecases.md)
   + 데이터 내보내기 {#data-export}
      + [개요](../use-cases/data-export/overview.md)
      + [BI 확장 기능](../use-cases/data-export/bi-extension.md)
      + [데이터 세트 내보내기](../use-cases/data-export/export-datasets.md)
      + [전체 테이블 내보내기](../use-cases/data-export/export-full-table.md)
      + [쿼리 서비스 및 데이터 세트 내보내기](../use-cases/data-export/queryservice-export-datasets.md)
   + B2B {#b2b}
      + [B2B 프로젝트 예시](../use-cases/b2b/example.md)
   + 크로스 채널 데이터 {#cross-channel}
      + [채널 간 데이터 분석](../use-cases/cross-channel/cross-channel.md)
      + [콜센터 및 웹 데이터 가져오기](../use-cases/cross-channel/call-center.md)
   + Adobe Analytics 데이터 {#aa-data}
      + [마케팅 채널 차원 사용](../use-cases/aa-data/marketing-channels.md)
      + [보고서 세트를 다른 스키마와 결합](../use-cases/aa-data/combine-report-suites.md)
   + 복잡한 데이터 {#complex-data}
      + [오브젝트 배열 사용](../use-cases/object-arrays.md)
   + 결합 {#stitching}
      + [공유 디바이스](/help/use-cases/stitching/shared-devices.md)
   + 파생 필드 {#derived-fields}
      + [목표 보고서](../use-cases/goals-using-derived-fields.md)

+ Labs {#labs}
   + [Labs 사용 안내서](../labs/labs.md)

+ 문제 해결 {#troubleshooting}
   + [데이터 비교](../troubleshooting/compare.md)
   + [지표 및 대상자의 일관성](../troubleshooting/consistency-rcdp-cja.md)
   + [권한 부족](../troubleshooting/lack-of-permissions.md)

+ 기술 노트 {#technotes}
   + [액세스 제어](../technotes/access-control.md)
   + [데이터 센터](../technotes/data-centers.md)
   + [삭제 영향](../technotes/deletion.md)
   + [도메인](../technotes/domains.md)
   + [용어 설명](../technotes/glossary.md)
   + [가드레일](../technotes/guardrails.md)
   + [IP 주소](../technotes/ip-addresses.md)
   + [성능 최적화](../technotes/optimizing-performance.md)
   + [사용량 조회 및 관리](../technotes/estimate-usage.md)

+ [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/)
