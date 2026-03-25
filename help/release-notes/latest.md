---
title: 최신 Customer Journey Analytics 릴리스 정보
description: 최신 Customer Journey Analytics 릴리스 정보 보기
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 5319c0aafa5c92215176044a35953ac1e183eb53
workflow-type: tm+mt
source-wordcount: '1630'
ht-degree: 24%

---

# 최신 Customer Journey Analytics 릴리스 정보 (2026년 3월)

**마지막 업데이트**: 2026년 3월 11일

이 릴리스 노트는 2026년 3월 릴리스 기간을 다룹니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 게재 모델](releases.md)에서 작동합니다. 따라서 이들 릴리스 정보는 월별로 여러 차례 업데이트됩니다. 이들 릴리스 정보를 정기적으로 확인하십시오.

## 새로운 기능 또는 업데이트된 기능

| 기능 및 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| -----------|-----------|-----------|
| **헤더 재정의** <br/>Content Analytics에서 헤더 이름과 암호 헤더 값을 지정할 수 있습니다. 이 [헤더는 구성을 무시합니다](/help/content-analytics/config/guided.md#header-overrides) Content Analytics에서 사용자가 구현한 보트 검색 또는 게이트 트래픽 기술을 무시하도록 사용자 지정 HTTP 헤더를 보내도록 합니다. |  | 2026년 2월 2일 화요일 |
| **여러 IMS 조직의 보고서 세트 결합**<br/> Analytics Source 커넥터를 사용하여 여러 IMS 조직의 보고서 세트를 결합할 수 있습니다. 이 [IMS 간 데이터 매핑](/help/getting-started/aa-vs-cja/mapping-data-ims-orgs.md) 기능을 사용하면 고객 데이터가 여러 IMS 조직에 분산되어 있는 경우에도 조직에서 고객 데이터를 통합적으로 볼 수 있습니다. <p>**참고:** 이 구성은 Adobe 고객 지원 센터에 요청을 제출하는 경우에만 사용할 수 있습니다.</p> |  | 2026년 2월 12일 금요일 |
| **자유 형식 테이블에 여러 차원 열 포함**<br/>&#x200B;이제 자유 형식 테이블에 최대 5개의 차원 열을 포함할 수 있으므로 여러 차원 항목을 나란히 볼 수 있습니다. 차원 항목의 각 행은 연결된 단일 차원 항목처럼 작동합니다.<p>여러 차원 열이 있는 자유 형식 테이블에 필터, 정렬, 분류 등을 적용하여 더욱 심층적이고 사용자 정의된 분석을 만들 수 있습니다.</p><p>이전에는 자유 형식 테이블에 차원 열을 1개만 포함할 수 있었습니다.</p><p>자세한 내용은 [자유 형식 테이블에 여러 차원 열 포함](/help/analysis-workspace/visualizations/freeform-table/freeform-table-multidimensions.md)을 참조하십시오.</p> | 2026년 1월 28일 | 2026년 3월 4일 목요일 <p>(원래 2026년 2월 18일 목요일로 계획됨)</p> |
| **여러 열로 테이블을 정렬합니다**<br/>&#x200B;이제 Analysis Workspace에서 자유 형식 테이블의 데이터를 차원이든 지표든 여러 열로 정렬할 수 있습니다.<p>여러 열에 대해 데이터를 정렬할 때 데이터는 각 열에 할당한 우선순위에 따라 정렬됩니다. 우선순위 번호는 정렬 아이콘 옆에 표시됩니다.</p><p>자세한 내용은 [자유 형식 테이블 필터링 및 정렬](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)을 참조하십시오.</p> | 2026년 1월 28일 | 2026년 3월 4일 목요일 <p>(원래 2026년 2월 18일 목요일로 계획됨)</p> |
| **Content Analytics: 분산형 시각화 썸네일 및 미리 보기** <br/>[썸네일 및 미리 보기](/help/content-analytics/report/report.md)는 Content Analytics의 분산형 시각화에서 에셋 및 경험에 사용할 수 있습니다. | 2026년 2월 17일 수요일 | 2026년 3월 2일 화요일 |
| **Content Analytics: 막대 시각화 썸네일 및 미리 보기** <br/>[썸네일 및 미리 보기](/help/content-analytics/report/report.md)는 Content Analytics의 막대(스택) 및 가로 막대(스택) 시각화에서 에셋 및 경험에 사용할 수 있습니다. | 2026년 2월 23일 화요일 | 2026년 3월 9일 화요일 |
| **연결에서 데이터 세트 미리 보기 다시 디자인**<br/>&#x200B;개인 기반 연결에서 데이터 세트를 [추가](/help/connections/create-connection.md#add-datasets) 또는 [편집](/help/connections/create-connection.md#edit-a-dataset)하면 데이터 미리 보기 환경이 개선됩니다. 활성화된 데이터 세트 결합의 경우 [결합 지표](/help/stitching/use-stitching-ui.md#stitching-metrics) 및 [잘못된 ID에 대한 정보](/help/stitching/use-stitching-ui.md#bad-ids)를 추가로 사용할 수 있습니다. | 2026년 3월 6일 토요일 | TBD |
| **Report Builder: 예약된 모든 통합 문서에 대한 관리자 가시성**<br/> Report Builder Excel 추가 기능에는 예약된 사용자에 관계없이 관리자가 특정 조직의 예약된 모든 통합 문서를 볼 수 있는 새로운 필터 옵션이 포함되어 있습니다. 이 필터 옵션은 Analytics 관리자만 사용할 수 있습니다. 예약된 통합 문서를 볼 때 통합 문서 탭과 레거시 탭 모두에서 사용할 수 있습니다.<p>모든 예약된 통합 문서를 보는 기능은 관리자가 마이그레이션하기 전에 모든 이전 통합 문서를 쉽게 찾을 수 있도록 해 주기 때문에 분산 팀에서 통합 문서를 마이그레이션할 때 특히 유용합니다.</p><p>이전에는 관리자가 다른 사용자가 예약한 통합 문서가 아니라 예약한 통합 문서만 볼 수 있었습니다.</br>자세한 내용은 [예약된 통합 문서 관리](/help/report-builder/manage-schedules-reportbuilder.md)를 참조하십시오.</p> | | 2026년 3월 10일 수요일 |
| **근사 고유 개수 함수 업데이트**<br/>&#x200B;근사 고유 개수 함수에 사용되는 HLL 확률적 알고리즘이 곧 업데이트됩니다. 이 함수를 사용하는 숫자에 대한 결과 출력은 다음과 같이 과거 숫자에서 약간 변경될 수 있습니다.<ul><li>매우 적은 양의 고유 값을 계산할 때 추정치를 사용하지 않고 정확한 개수를 사용하도록 결과가 개선됩니다.</li><li>더 큰 값을 계산할 때 예상 횟수는 이 업데이트 전과 동일한 정확도를 유지합니다(예상 횟수는 정확한 횟수의 5%, 시간의 95% 내에서 정확함).</li></ul><p>근사 고유 개수 함수에 대한 자세한 내용은 [고급 함수](/help/components/calc-metrics/cm-adv-functions.md#approximate-count-distinct)에서 [근사 고유 개수](/help/components/calc-metrics/cm-adv-functions.md)를 참조하십시오.</p> | | 2026년 3월 10일 수요일 |
| **전체 테이블 내보내기 개선 사항**<br/>&#x200B;전체 테이블 내보내기에는 다음과 같은 개선 사항이 포함됩니다.<p>내보내기 만들기 및 구성 개선 사항</p><ul><li>내보내기 페이지에서 내보내기를 만듭니다. 이전에는 표를 마우스 오른쪽 단추로 클릭하여 Analysis Workspace에서 내보내기만 만들 수 있었습니다.</li><li>내보내기를 만들 때 새 계정 또는 위치를 추가합니다.</li><li>내보낸 파일의 파일 이름 생성 및 폴더 배치를 자동화합니다. 이렇게 하면 파일 이름을 예측할 수 있고 논리적으로 폴더에 구성할 수 있습니다. 이전에는 파일 이름을 예측할 수 없었고 단일 폴더로 그룹화되었습니다.</li><li>데이터 웨어하우스 호환성을 개선하기 위해 데이터를 Parquet 파일로 내보낼 수 있습니다. 이전에는 CSV 및 JSON만 지원되었습니다.</li></ul><p>내보내기 관리 개선 사항</p><ul><li>내보내기 페이지에서 하나 이상의 내보내기를 갱신하거나 취소합니다.</li><li>로그 페이지에서 하나 이상의 내보내기를 다시 보냅니다.</li><li>내보내기가 실패하거나 만료될 예정인 경우 개별 사용자 또는 그룹에 이메일을 보냅니다.</li><li>내보내기 실패에 대한 보다 정확한 오류 메시지.</li></ul><p>계산된 지표, 세그먼트 및 차원 개선 사항</p><ul><li>더 많은 계산된 지표 함수를 지원합니다. 이전에는 단순한 수학 함수만 지원되었습니다.</li><li>내보내기를 만들 때 세그먼트를 적용합니다.</li><li>정밀도 향상을 위해 더블 데이터 유형 차원을 지원합니다.</li></ul><p>관리 개선 사항</p><ul><li>이제 관리자는 생성된 사용자에 관계없이 모든 내보내기 및 로그를 볼 수 있습니다.</li></ul><p>자세한 내용은 다음 리소스를 참조하십시오.<ul><li>[클라우드로 전체 테이블 내보내기](/help/analysis-workspace/export/export-cloud.md)</li><li>[클라우드 내보내기 계정 구성](/help/components/exports/cloud-export-accounts.md)</li><li>[클라우드 내보내기 위치 구성](/help/components/exports/cloud-export-locations.md)</li><li>[내보내기 관리](/help/components/exports/manage-exports.md)</li><li>[클라우드 내보내기 위치 및 계정 관리](/help/components/exports/manage-export-locations.md)</li><li>[내보내기 로그 관리](/help/components/exports/manage-export-logs.md)</li></ul></p> | 2026년 2월 25일 목요일 | 2026년 3월 11일 목요일<p>(원래 2026년 3월 4일 목요일로 계획됨)</p> |
| **Analysis Workspace을 위한 실습 자습서**<br/>&#x200B;이제 새로운 실습 자습서를 통해 새로운 사용자에게 Analysis Workspace의 패널, 시각화 및 구성 요소 사용에 대한 기본 사항을 안내할 수 있습니다. <p>자세한 내용은 [Customer Journey Analytics 랜딩 페이지](/help/getting-started/landing.md)를 참조하세요.</p> | | 2026년 3월 18일 목요일 |
| **데이터 미러 지원**<br/> Experience Platform의 특정 소스 커넥터에 대한 모델 기반 스키마 및 변경 데이터 캡처(CDC) 기능을 지원하면 Customer Journey Analytics에서 [, ](/help/data-mirror/data-mirror.md) 및 [!DNL Snowflake]과(와) 같은 데이터 웨어하우스 솔루션의 [!DNL Azure Databricks]데이터 미러[!DNL Google BigQuery] 기능을 지원할 수 있습니다.<p>Beta에 액세스하려면 Adobe 계정 팀에 문의하십시오.</p> | Beta 릴리스: 2025년 9월 24일 | 2026년 3월 25일 목요일 |
| **Copilot과 Data Insights Agent 통합** <br/> 이제 Data Insights Agent이 Microsoft Copilot과 통합되어 Teams, Powerpoint 등을 포함한 Microsoft 도구 내에서 직접 자연어 프롬프트를 사용하여 Customer Journey Analytics 데이터와 상호 작용할 수 있습니다.<p>(참조할 설명서 링크입니다.)</p> | | 2026년 3월 26일 금요일 |
| **Adobe 엔지니어링 에이전트에서 데이터 유효성 검사** <br/>Data Engineering Agent 내에서 새로운 데이터 유효성 검사 기술을 사용할 수 있습니다. 이러한 기술은 Customer Journey Analytics에서 데이터를 분석하기 전에 Adobe Experience Platform에서 직접 데이터 품질을 팀이 빠르게 평가하는 데 도움이 됩니다. <p>데이터 유효성 검사 기술을 통해 온디맨드, 필드 수준 및 데이터 세트 수준 유효성 검사를 수행할 수 있으며, 여기에는 통계 요약과 유효하지 않거나 비정상적인 값을 지능적으로 감지하는 기능이 결합되어 있습니다. </p><p>데이터 유효성 검사 기술을 사용하면 수동 QA 노력을 줄이고 데이터 엔지니어링 워크플로 전반에서 신뢰할 수 있는 데이터 온보딩 및 변환을 가속화할 수 있습니다.</p><p>(참조할 설명서 링크입니다.)<!--For more information, see [Data Engineering Agent]() (will be in this repo: https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/cja-data-insights-agent).--></p> | | 2026년 4월 말 <p>(원래 2026년 3월 31일 수요일 릴리스로 계획됨)</p> |
| **패널에 분류 적용**<br/>&#x200B;이제 패널에 분류를 적용할 수 있습니다. 패널 수준에서 분류를 적용하면 패널 내의 모든 자유 형식 테이블의 모든 열에 분류가 적용됩니다. | 2026년 3월 | 2026년 5월 |
| **스트리밍 미디어 서비스: 일정 데이터 지원** <br/>이제 이전 라이브 스트리밍 미디어 콘텐츠의 일정 데이터를 업로드하여 시청률을 보다 쉽고 정확하게 추적할 수 있습니다.<p>다음은 일정 데이터 업로드가 지원되는 라이브 콘텐츠의 예입니다.</p><ul><li>FAST(무료 광고 지원 TV) 플랫폼</li><li>로컬 스트림</li><li>라이브 스포츠</li></ul><p>일정 데이터를 업로드하면 업로드 파일에서 지정한 시간 동안 실행된 개별 프로그램의 시청자 수 데이터를 추적할 수 있습니다. 특정 주제나 프로그램 세그먼트에 대한 시청자 수 데이터를 수집할 수도 있습니다.</p><p>이러한 기능은 스트리밍 미디어 컬렉션을 어떻게 구현하든 관계없이 사용할 수 있습니다.</p><p>이전에는 라이브 콘텐츠를 분석할 때 주어진 세션을 특정 프로그램에 정확하게 연결하는 것이 어려웠고, 주어진 세션을 개별 주제나 프로그램 세그먼트에 연결하는 것도 불가능했습니다.</p><p>자세한 내용은 [라이브 콘텐츠를 추적할 일정 데이터 업로드](https://experienceleague.adobe.com/ko/docs/media-analytics/using/media-use-cases/track-schedule-data)를 참조하십시오.</p> | 2025년 10월 29일 | 2026년 상반기<p>(원래 2025년 10월 29일 릴리스로 계획됨)</p> |
| **이탈리아어 지원**<br/>&#x200B;이탈리아어 로케일(it-IT)은 이제 Customer Journey Analytics의 Analysis Workspace에서 지원됩니다. <p>Customer Journey Analytics은 [Experience Platform UI에 대한 브라우저 및 언어 지원](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#language-support)에 설명된 대로 Experience Platform UI에서 지원되는 모든 언어를 지원합니다.</p><p>Experience Platform에서 [기본 언어를 변경](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-ui/browser-language-support#change-default-language)할 수 있습니다.</p> | | 2026년 4월 8일 목요일 |

## Customer Journey Analytics의 수정 사항

**Analysis Workspace**: AN-440336, AN-440216, AN-438445, AN-438216, AN-437856, AN-437776, AN-437765, AN-437365, AN-432793, AN-432094, AN-431557, AN-431200, AN-429621, AN-429424, AN-427973, AN-426089, AN-425883 424359
**구성 요소**:
**Content Analytics**:
**분석 가이드**:
**내보내기**: AN-432030
**데이터 보기**: AN-440004, AN-437154, AN-431165
**구현**:
**Report Builder**: AN-437895, AN-437083, AN-434288, AN-434209, AN-433224, AN-430622
**보고**: AN-439482, AN-439545, AN-438708, AN-431206, AN-430079, AN-428302, AN-428257, AN-425779, AN-423330
**세그먼테이션**:
**예약된 보고서**:
**공유된 지표 및 차원**:
**기타**: AN-439795, AN-434783, AN-434233, AN-434005, AN-433368, AN-431322, AN-431165, AN-431012, AN-429983, AN-429067, AN-423285


## Customer Journey Analytics 관리자에 대한 중요 공지

| 공지 | 공지 추가 또는 업데이트됨 | 설명 |
| --- | --- | --- |
| **TLS 1.2 암호 그룹 제거** | 2026년 2월 11일 목요일 | 관리자에게 알림: Adobe은 2026년 5월 27일에 Adobe 데이터 수집 서버에서 다음 TLS 1.2 암호 세트에 대한 지원을 중단할 예정입니다.<ul><li>`TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_128_CBC_SHA`</li><li>`TLS_RSA_WITH_AES_256_CBC_SHA`</li></ul><p>대부분의 구현에 고객 작업이 필요하지 않습니다. 이 변경 사항은 주로 오래된 TLS 라이브러리를 사용하는 이전 기본 애플리케이션에서 전송된 Analytics 데이터와 오래된 브라우저나 운영 체제에서 적은 수의 웹 방문자에게 영향을 줍니다. 이러한 암호 세트에 대한 지원을 제거하면 보안이 강화되고 Adobe이 최신 암호화 표준에 맞게 조정됩니다. 현재 데이터 수집 트래픽의 0.1% 미만이 이러한 암호 세트에 의존합니다.</p> |

## 관련 리소스

* [2025년의 이전 Customer Journey Analytics 릴리스 정보](/help/release-notes/2025.md)
* [Adobe Analytics 릴리스 정보](https://experienceleague.adobe.com/ko/docs/analytics/release-notes/latest)
* [스트리밍 미디어 컬렉션 릴리스 정보](https://experienceleague.adobe.com/ko/docs/media-analytics/using/release-notes/release-notes)
* [Adobe Experience Cloud 릴리스 정보](https://experienceleague.adobe.com/ko/docs/release-notes/experience-cloud/current)
* [Customer Journey Analytics 설명서 업데이트](/help/release-notes/doc-changes.md)
