---
git-repo: https://github.com/AdobeDocs/analytics-platform.ko-KR
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: true
user-guide-title: Customer Journey Analytics 안내서
user-guide-description: Experience Platform의 데이터와 함께 Analysis Workspace를 사용하는 방법 및 Customer Journey Analytics(CJA)에 대해 알아봅니다.
breadcrumb-title: Customer Journey Analytics 안내서
source-git-commit: 7e6383bf94e10f6ab6f9db990f4ef3df0fb826d3
workflow-type: tm+mt
source-wordcount: '892'
ht-degree: 98%

---


# Customer Journey Analytics 안내서 {#using}

+ [Customer Journey Analytics 안내서](../getting-started/cja-landing.md)

+ 릴리스 정보 {#releases}
   + [최신 릴리스](../release-notes/latest.md)
   + [2023년 릴리스](../release-notes/2023.md)
   + [2022년 릴리스](../release-notes/2022.md)
   + [2021년 릴리스](../release-notes/2021.md)
   + [2020년 릴리스](../release-notes/2020.md)
   + [CJA 릴리스](../release-notes/releases.md)
   + [CJA 설명서 업데이트](../release-notes/doc-changes.md)

+ 시작하기 {#cja-overview}
   + [Customer Journey Analytics 개요](../getting-started/cja-overview.md)
   + [빠른 시작 안내서](../getting-started/cja-getting-started.md)
   + [랜딩 페이지](../getting-started/landing.md)
   + [자주 묻는 질문](../getting-started/cja-faq.md)
   + [CJA와 BI 솔루션 비교](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics 및 Adobe Analytics 비교 {#compare-aa-cja}
   + [Adobe Analytics의 발전 ](../getting-started/aa-to-cja.md)
   + [Adobe Analytics 사용자를 위한 사용 안내서](../getting-started/aa-to-cja-user.md)
   + Adobe Analytics와의 비교 {#cja-aa-comparison}
      + [Customer Journey Analytics에서 Adobe Analytics 데이터 활용](../getting-started/aa-vs-cja/aa-data-in-cja.md)
      + [Customer Journey Analytics 기능 지원](../getting-started/aa-vs-cja/cja-aa.md)
      + [Analytics 소스 커넥터를 통해 전달되는 Analytics 데이터의 용어 비교](../getting-started/aa-vs-cja/terminology.md)
      + [Adobe Analytics 및 CJA에서 데이터 처리 비교](../getting-started/aa-vs-cja/data-processing-comparisons.md)
      + [가상 보고 환경 및 샌드박스 환경](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
      + [처리 규칙, VISTA 및 분류 대 데이터 준비](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
      + [AAID, ECID, AACUSTOMID 및 Analytics 소스 커넥터](../getting-started/aa-vs-cja/aaid-ecid-adc.md)

+ 데이터 수집 {#cja-data-ingestion}
   + [데이터 수집 개요](../data-ingestion/data-ingestion.md)
   + 빠른 시작 안내서 수집 및 사용{#ingest-use-guides}
      + [Adobe Analytics](../data-ingestion/analytics.md)
      + [Adobe Experience Platform Web SDK 및 Edge Network](../data-ingestion/aepwebsdk.md)
      + [배치 데이터](../data-ingestion/batch.md)
      + [스트리밍 데이터](../data-ingestion/streaming.md)
      + [소스 커넥터](../data-ingestion/sources.md)

+ 연결 {#cja-connections}
   + [연결 개요](../connections/overview.md)
   + [연결 만들기](../connections/create-connection.md)
   + [연결 관리](../connections/manage-connections.md)
   + [결합된 이벤트 데이터 세트](../connections/combined-dataset.md)
   + [표준 조회](../connections/standard-lookups.md)
   + [교차 채널 분석](../connections/cca.md)

+ 데이터 보기 {#cja-dataviews}
   + [데이터 보기 개요](../data-views/data-views.md)
   + [데이터 보기 만들기 또는 편집](../data-views/create-dataview.md)
   + 구성 요소 설정 {#component-settings}
      + [구성 요소 설정 개요](../data-views/component-settings/overview.md)
      + [기여도 분석](../data-views/component-settings/attribution.md)
      + [비헤이비어](../data-views/component-settings/behavior.md)
      + [포맷](../data-views/component-settings/format.md)
      + [포함/제외 값](../data-views/component-settings/include-exclude-values.md)
      + [지표 중복 제거](../data-views/component-settings/metric-deduplication.md)
      + [값 옵션 없음](../data-views/component-settings/no-value-options.md)
      + [지속성](../data-views/component-settings/persistence.md)
      + [하위 문자열](../data-views/component-settings/substring.md)
      + [값 버킷팅](../data-views/component-settings/value-bucketing.md)
   + [표준 구성 요소 참조](../data-views/component-reference.md)
   + [SQL 커넥터](../data-views/sql-connector.md)
   + [파생 필드](../data-views/derived-fields/derived-fields.md)
   + [레이블 및 정책](../data-views/data-governance.md)


+ 작업 영역 프로젝트 {#cja-workspace}
   + [Analysis Workspace 개요](../analysis-workspace/home.md)
   + [기본 분석 수행](../analysis-workspace/perform-basic-analysis.md)
   + [고급 분석 수행](../analysis-workspace/perform-adv-analysis.md)

   + 프로젝트 {#build-workspace-project}
      + [프로젝트 개요](../analysis-workspace/build-workspace-project/freeform-overview.md)
      + [프로젝트 만들기](/help/analysis-workspace/build-workspace-project/create-projects.md)
      + [프로젝트 저장](../analysis-workspace/build-workspace-project/save-projects.md)
      + 작업 영역의 폴더 {#workspace-folders}
         + [작업 영역의 폴더 정보](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
         + [폴더 만들기 및 하위 폴더 만들기](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
         + [폴더 삭제](../analysis-workspace/build-workspace-project/workspace-folders/delete-folders.md)
         + [프로젝트 추가](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
         + [프로젝트 제거](../analysis-workspace/build-workspace-project/workspace-folders/remove-projects.md)
         + [새 프로젝트 저장](../analysis-workspace/build-workspace-project/workspace-folders/save-new-project-folder.md)
      + [핫키 (단축키)](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
      + [색상 팔레트](../analysis-workspace/build-workspace-project/color-palettes.md)
      + [보기 밀도](../analysis-workspace/build-workspace-project/view-density.md)
   + 시각화 {#visualizations}
      + [시각화 개요](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
      + [데이터 소스 관리](../analysis-workspace/visualizations/t-sync-visualization.md)

      + 자유 형식 테이블 {#freeform-table}
         + [자유 형식 테이블](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
         + 열 및 행 설정 {#column-row-settings}
            + [열 설정](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
            + [행 설정](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
            + [동적 및 정적 항목](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
         + [테이블 필터링 및 정렬](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)

         + [작업 영역 합계](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
      + 집단 테이블 {#cohort-table}
         + [집단 분석이란?](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
         + [집단 분석 보고서 구성](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
         + [집단 분석 사용 사례](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
      + 폴아웃 {#fallout}
         + [폴아웃 개요](../analysis-workspace/visualizations/fallout/fallout-flow.md)
         + [폴아웃 시각화 구성](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
         + [차원 간 폴아웃](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
         + [폴아웃 분석에서 필터 적용](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
      + 플로우 {#flow}
         + [플로우 개요](../analysis-workspace/visualizations/c-flow/flow.md)
         + [플로우 시각화 구성](../analysis-workspace/visualizations/c-flow/create-flow.md)
         + [차원 간 플로우](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
      + [영역 및 스택 영역](../analysis-workspace/visualizations/area.md)

      + [막대 및 스택 막대](../analysis-workspace/visualizations/bar.md)
      + [글머리 기호 그래프](../analysis-workspace/visualizations/bullet-graph.md)
      + [콤보 차트](../analysis-workspace/visualizations/combo-charts.md)
      + [도넛](../analysis-workspace/visualizations/donut.md)
      + [히스토그램](../analysis-workspace/visualizations/histogram.md)
      + [가로 막대 및 스택 가로 막대](../analysis-workspace/visualizations/horizontal-bar.md)
      + [지능형 캡션](../analysis-workspace/visualizations/intelligent-captions.md)
      + [주요 지표 요약](../analysis-workspace/visualizations/key-metric.md)
      + [라인](../analysis-workspace/visualizations/line.md)
      + [산포도](../analysis-workspace/visualizations/scatterplot.md)
      + [요약 번호 및 요약 변경 사항](../analysis-workspace/visualizations/summary-number-change.md)
      + [텍스트](../analysis-workspace/visualizations/text.md)
      + [트리 맵](../analysis-workspace/visualizations/treemap.md)
      + [벤](../analysis-workspace/visualizations/venn.md)
   + 패널 {#panels}
      + [패널 개요](../analysis-workspace/c-panels/panels.md)
      + [속성 패널](../analysis-workspace/c-panels/attribution.md)
      + [빈 패널](../analysis-workspace/c-panels/blank-panel.md)
      + [실험 패널](../analysis-workspace/c-panels/experimentation.md)
      + [자유 형식 패널](../analysis-workspace/c-panels/freeform-panel.md)
      + [빠른 인사이트 패널](../analysis-workspace/c-panels/quickinsight.md)
      + [미디어 동시 뷰어 패널](../analysis-workspace/c-panels/media-concurrent-viewers.md)
      + 미디어 재생 소요 시간 {#media-playback-timespent}
         + [개요](../analysis-workspace/c-panels/media-playback-timespent/media-playback-time-spent.md)
         + [입력 및 출력 설정](../analysis-workspace/c-panels/media-playback-timespent/panel-inputs-outputs.md)
         + [FAQ](../analysis-workspace/c-panels/media-playback-timespent/faqs.md)
   + 프로젝트 구성, 공유 및 예약 {#curate-share}
      + [공유 메뉴](../analysis-workspace/curate-share/send-schedule-files.md)
      + [프로젝트 구성](../analysis-workspace/curate-share/curate.md)
      + [프로젝트 공유](../analysis-workspace/curate-share/share-projects.md)
      + [공유 가능한 링크 만들기](../analysis-workspace/curate-share/shareable-links.md)
      + [보기 전용 프로젝트](../analysis-workspace/curate-share/view-only-projects.md)
      + [PDF 또는 CSV 파일 다운로드](../analysis-workspace/curate-share/download-send.md)
      + [프로젝트 예약](../analysis-workspace/curate-share/t-schedule-report.md)
   + Virtual Analyst {#virtual-analyst}
      + [Virtual Analyst 개요](../analysis-workspace/virtual-analyst/overview.md)
      + 예외 항목 탐지 {#anomaly-detection}
         + [예외 항목 탐지 개요](../analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)
         + [Analysis Workspace에서 예외 항목 보기](../analysis-workspace/virtual-analyst/c-anomaly-detection/view-anomalies.md)
         + [예외 항목 탐지에서 사용된 통계 기법](../analysis-workspace/virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)
   + [사용자 환경 설정](../analysis-workspace/user-preferences.md)

   + 작업 영역 FAQ {#workspace-faq}
      + [자주 묻는 질문](../analysis-workspace/workspace-faq/faq.md)
      + [Analysis Workspace 성능 최적화](../analysis-workspace/workspace-faq/optimizing-performance.md)
      + [오류 메시지](../analysis-workspace/workspace-faq/error-messages.md)
      + [Analysis Workspace 제한 사항](../analysis-workspace/workspace-faq/aw-limitations.md)
      + [관리 요구 사항](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
      + [Analysis Workspace 액세스 가능 여부](../analysis-workspace/workspace-faq/aw-accessibility.md)
      + [Analysis Workspace의 롱테일](../analysis-workspace/workspace-faq/long-tail.md)











+ 구성 요소 {#cja-components}
   + [구성 요소 개요](../components/overview.md)
   + [구성 요소 설명 추가](../components/add-component-descriptions.md)
   + 주석 {#annotations}
      + [주석 개요](../components/annotations/overview.md)
      + [주석 생성](../components/annotations/create-annotations.md)
      + [주석 관리](../components/annotations/manage-annotations.md)
      + [주석 보기](../components/annotations/view-annotations.md)
      + [모바일 주석](../components/annotations/mobile-annotations.md)
   + 대상자 {#audiences}
      + [대상자 개요](../components/audiences/audiences-overview.md)
      + [대상자 생성 및 게시](../components/audiences/publish.md)
      + [대상자 관리](../components/audiences/manage.md)
   + 차원 {#dimensions}
      + [차원 미리보기](../components/dimensions/view-dimensions.md)
      + [차원 분류](../components/dimensions/t-breakdown-fa.md)
      + [차원 시간 분할](../components/dimensions/time-parting-dimensions.md)
      + [카디널리티가 매우 높은 차원](../components/dimensions/high-cardinality.md)
   + [지표](../components/apply-create-metrics.md)
   + 필터 {#cja-filters}
      + [필터 개요](../components/filters/filters-overview.md)
      + [필터 만들기](../components/filters/create-filters.md)
      + [빠른 필터](../components/filters/quick-filters.md)
      + [필터 빌더](../components/filters/filter-builder.md)
      + [필터 관리](../components/filters/manage-filters.md)
      + [연산자](../components/filters/operators.md)
   + 계산된 지표 {#cja-calcmetrics}
      + [계산된 지표 개요](../components/calc-metrics/calc-metr-overview.md)
      + 계산된 지표 워크플로 {#cm-workflow}
         + [계산된 지표 워크플로](../components/calc-metrics/cm-workflow/cm-workflow.md)
         + [지표 찾기](../components/calc-metrics/cm-workflow/cm-finding.md)
         + [지표 작성](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
         + [지표 유형 및 속성](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
         + [간단한 “방문자 수당 페이지 조회수” 지표 작성](../components/calc-metrics/cm-workflow/cm-pvv.md)
         + [필터링된 지표](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
         + [세그먼트 스택 및 바꾸기](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
         + [필터 및 가중치가 적용된 지표](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
         + [함수 사용](../components/calc-metrics/cm-workflow/cm-using-functions.md)
         + [참여도 지표](../components/calc-metrics/cm-workflow/participation-metric.md)
         + [계산된 지표에 태그 지정](../components/calc-metrics/cm-workflow/cm-tagging.md)
         + [계산된 지표 승인](../components/calc-metrics/cm-workflow/cm-approving.md)
         + [계산된 지표 공유](../components/calc-metrics/cm-workflow/cm-sharing.md)
         + [계산된 지표 관리자](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [기본 계산된 지표](../components/calc-metrics/default-calcmetrics.md)
      + [기본 함수](../components/calc-metrics/cm-functions.md)
      + [고급 함수](../components/calc-metrics/cm-adv-functions.md)
   + 날짜 범위 {#cja-date-ranges}
      + [날짜 범위 개요](../components/date-ranges/overview.md)
      + [날짜 범위 만들기](../components/date-ranges/create.md)
      + [날짜 범위 관리](../components/date-ranges/manage.md)
      + [캘린더 개요](../components/date-ranges/calendar.md)
      + [사용자 정의 날짜 범위 만들기](../components/date-ranges/custom-date-ranges.md)
      + [날짜 비교](../components/date-ranges/time-comparison.md)
   + 데이터 사전 {#data-dictionary}
      + [데이터 사전 개요](../components/data-dictionary/data-dictionary-overview.md)
      + [데이터 사전의 구성 요소 정보 보기](../components/data-dictionary/view-data-dictionary.md)
      + [데이터 사전의 구성 요소 항목 편집](../components/data-dictionary/edit-entries-data-dictionary.md)
      + [데이터 사전 상태 모니터링](../components/data-dictionary/monitor-data-dictionary-health.md)
+ Analytics 대시보드 {#cja-dashboards}
   + [Analytics 대시보드 - 개요](../mobile-app/home.md)
   + [큐레이터 작업](../mobile-app/curator.md)
   + [모바일 스코어카드 만들기](../mobile-app/create-scorecard.md)
   + [경영진이 대시보드를 사용할 수 있도록 설정](../mobile-app/set-up-execs.md)
   + [경영진 빠른 시작 안내서](../mobile-app/executive.md)
+ Report Builder {#cja-reportbuilder}
   + [Report Builder 개요](../report-builder/report-buider-overview.md)
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

+ 교차 채널 분석 {#cca}
   + [교차 채널 분석 개요](../cca/overview.md)
   + [재생 작동 방식](../cca/replay.md)
   + [교차 채널 분석 FAQ](../cca/faq.md)

+ Adobe 통합 {#integrations}
   + [CJA 개요와 Adobe 솔루션 통합](/help/integrations/overview.md)
   + [Customer Journey Analytics와 Adobe Analytics 통합](/help/integrations/aa.md)
   + [CJA와 Journey Optimizer 데이터 통합](/help/integrations/ajo.md)
   + [CJA와 의사 결정 관리 데이터 통합](/help/integrations/ajo-od.md)
   + [Customer AI와 CJA 통합](/help/integrations/customer-ai.md)

+ 데이터 거버넌스 {#cja-privacy}
   + [데이터 거버넌스](../privacy/privacy-overview.md)
   + [감사 로그](../privacy/audit-log.md)
   + [고객 관리 키](../privacy/cmk.md)

+ 사용 사례 {#cja-usecases}
   + [Customer Journey Analytics 사용 사례](../use-cases/cja-usecases.md)
   + Google Analytics 데이터 {#ga}
      + [Google Analytics에서 CJA로 데이터 마이그레이션 개요](../use-cases/ga/overview.md)
      + [Google Analytics 내역 데이터를 Platform으로 수집](../use-cases/ga/backfill.md)
      + [Platform으로의 Google Analytics 데이터 스트리밍 구성](../use-cases/ga/streaming.md)
      + [CJA에서 Google Analytics 데이터에 대한 보고](../use-cases/ga/report.md)
   + 데이터 수집 {#data-ingestion}
      + [AEP에 Marketo Engage 데이터를 수집하고 CJA에서 보고합니다.](../use-cases/data-ingestion/marketo.md)
      + [AEP 대상자를 CJA로 수집](../use-cases/data-ingestion/ingest-aep-segments.md)
   + 데이터 보기 {#data-views}
      + [데이터 보기 사용 사례](../use-cases/data-views/data-views-usecases.md)
      + [바인딩 차원 및 지표 사용](../use-cases/data-views/binding-dimensions-metrics.md)
   + B2B {#b2b}
      + [계정 수준 데이터를 조회 데이터 세트로 추가](../use-cases/b2b/b2b.md)
   + 크로스 채널 데이터 {#cross-channel}
      + [채널 간 데이터 분석](../use-cases/cross-channel/cross-channel.md)
      + [콜센터 및 웹 데이터 가져오기](../use-cases/cross-channel/call-center.md)
   + Adobe Analytics 데이터 {#aa-data}
      + [마케팅 채널 차원 사용](../use-cases/aa-data/marketing-channels.md)
      + [보고서 세트를 다른 스키마와 결합](../use-cases/aa-data/combine-report-suites.md)
   + 복잡한 데이터 {#complex-data}
      + [오브젝트 배열 사용](../use-cases/object-arrays.md)

+ 관리 {#cja-admin}
   + [액세스 제어](../admin/cja-access-control.md)
   + [사용량 보기 및 관리](../admin/estimate-usage.md)
   + [삭제 영향](../admin/cja-deletion.md)
   + [CJA 성능 최적화](../admin/cja-performance.md)

+ Labs {#labs}
   + [Labs 사용 안내서](../labs/labs.md)

+ 문제 해결 {#troubleshooting}
   + [Adobe Analytics 데이터와 CJA 데이터 비교](../troubleshooting/compare.md)
   + [Real-Time CDP와 CJA 간의 지표 및 대상자 멤버십의 일관성](../troubleshooting/consistency-rcdp-cja.md)

+ [CJA 용어](../getting-started/cja-glossary.md)

+ [CJA API](https://developer.adobe.com/cja-apis/docs/)
