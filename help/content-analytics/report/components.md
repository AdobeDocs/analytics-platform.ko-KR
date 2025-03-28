---
title: 콘텐츠 분석 구성 요소
description: 차원, (계산된) 지표 및 파생 필드와 같은 특정 Content Analytics 구성 요소에 대한 세부 정보
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: bb9b9850368796fe6cf2c4945ff3ef93b881b363
workflow-type: tm+mt
source-wordcount: '1194'
ht-degree: 17%

---

# 콘텐츠 분석 구성 요소

{{release-limited-testing}}

Content Analytics는 Customer Journey Analytics에서 이미 사용 가능한 구성 요소에 다음 범주의 구성 요소(차원, (계산된) 지표, 파생 필드)를 추가합니다.

* [경험 메타데이터](#experience-metadata)
* [경험 속성](#experience-attributes)
* [경험 이벤트](#experience-events)
* [에셋 메타데이터](#asset-metadata)
* [자산 속성](#asset-attributes)
* [Assets 이벤트](#asset-events)
* [계산된 지표](#calculated-metrics)

아래 표에서 ![AI 생성](/help/assets/icons/AI.svg)은(는) AI/ML 생성 특성/값 쌍을 나타냅니다.

## 경험 메타데이터

| 제목 | 설명 | 유형 | 설정 |
|---|---|---|---|
| 경험 채널 | 경험을 위한 채널. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 경험 소스 | 경험의 Source URL입니다. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 경험 ID | 경험에 대한 고유 ID입니다. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 경험 이름 | 경험의 이름입니다. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 경험 설명 | 경험에 대한 설명입니다. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 경험 썸네일 URL | 경험 썸네일용 URL. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 경험 가로 비율 깊이 | 경험의 가로 백분율 깊이를 수량화할 수 있는 값입니다. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 경험 세로 비율 깊이 | 경험의 세로 백분율 깊이에 대한 수량화 가능한 값입니다. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |

{style="table-layout:fixed"}



## 경험 속성

| 제목 | 설명 | 유형 | 설정 |
|---|---|---|---|
| 경험 키워드 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 키워드. | Dimension<br>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 경험 설득 전략 | 해당 경험에 있는 ![AI 생성](/help/assets/icons/AI.svg) 설득 전략. 가능한 가치는 사회적 정체성, 사회적 증명, 권위, 구체성, 문 안의 발, 반응 극복, 상호성, 정박과 비교, 사회적 영향, 희소성, 의인화 등이다. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 경험 내러티브 | 마케터의 관점에서 관련성을 기반으로 경험이 구축하고 있는 ![AI 생성](/help/assets/icons/AI.svg) 설명. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 경험 톤 | 마케터의 관점에서 관련성을 기반으로 경험이 구축하고 있는 ![AI 생성](/help/assets/icons/AI.svg) 톤 | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 경험 마케팅 감정 | ![AI 생성](/help/assets/icons/AI.svg) 경험의 일부로 사용되는 텍스트(긴급성, 배타성, 격려, 도전, 호기심, 성취, 신뢰, 단순성 및 매혹)를 읽을 때 독자에게 호출되는 감정입니다. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 경험 이모지 개수 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 이모지 수입니다. | 지표 | 값 계산<br/>십진수 \| 소수점 이하 자리 수: 0 |
| 경험 해시 태그 수 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 해시태그 수입니다. | 지표 | 값 계산<br/>십진수 \| 소수점 이하 자리 수: 0 |
| 경험 문장 수 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 문장 수. | 지표 | 값 계산<br/>십진수 \| 소수점 이하 자리 수: 0 |
| 경험 중지 단어 비율 | ![AI 생성](/help/assets/icons/AI.svg) 경험에 대한 정지어 수입니다. | 지표 | 값 계산<br/>십진수 \| 소수점 이하 자리 수: 0 |
| 경험 텍스트 인용 수 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 텍스트 따옴표 수. | 지표 | 값 계산<br/>십진수 \| 소수점 이하 자리 수: 0 |
| 경험 단어 수 | 경험에 대해 ![AI 생성](/help/assets/icons/AI.svg) 단어 수. | 지표 | 값 계산<br/>십진수 \| 소수점 이하 자리 수: 0 |
| 경험 문장당 단어 수 | 경험에 대한 문장당 ![AI 생성](/help/assets/icons/AI.svg) 단어 수. | 지표 | 값 계산<br/>십진수 \| 소수점 이하 자리 수: 0 |

{style="table-layout:fixed"}


## 경험 이벤트

| 제목 | 설명 | 유형 | 설정 |
|---|---|---|---|
| 경험 조회수 | 경험 보기 수에 대한 수량화 가능한 측정입니다. | 지표 | 값 계산<br/>십진수 \| 소수점 이하 자리 수: 0 |
| 경험 클릭 수 | 경험 클릭 수에 대한 수량화 가능한 측정입니다. | 지표 | 값 계산<br/>십진수 \| 소수점 이하 자리 수: 0 |

{style="table-layout:fixed"}


## 에셋 메타데이터

| 제목 | 설명 | 유형 | 설정 |
|---|---|---|---|
| 자산 소스 | 자산에 대한 공개 액세스 가능한 소스 URL. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 ID | 에셋에 대한 고유 식별자. 에셋 바이너리는 고유성을 결정합니다. 에셋 바이너리가 변경되면 ID가 변경됩니다. 고유 ID는 URL일 수 있지만 생성된 해시일 수도 있습니다. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 HTML 경로 | 에셋에 대해 연결된 HTML 경로입니다. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 링크 URL | 에셋에 가장 가까운 페이지 앵커입니다. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 표시 폭 | 콘텐츠 자산 표시 폭. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 표시 높이 | 콘텐츠 자산 표시 높이. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 절대 왼쪽 위치 | 콘텐츠 자산 절대 왼쪽 위치. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 절대 상단 위치 | 콘텐츠 자산 절대 상단 위치. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |

{style="table-layout:fixed"}


## 자산 속성

| 제목 | 설명 | 유형 | 설정 |
|---|---|---|---|
| 자산 방향 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 방향. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 전체 톤 | 에셋의 ![AI 생성](/help/assets/icons/AI.svg) 전체 톤. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 전경색 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 전경색. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 에셋 배경색 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 배경색입니다. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 태그 | 에셋에 대해 ![AI가 생성](/help/assets/icons/AI.svg)되었습니다. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 장면 | 에셋에 대해 ![AI가 생성](/help/assets/icons/AI.svg)되었습니다. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 오브젝트 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 개체. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 포토그래피 스타일 | 에셋의 ![AI 생성](/help/assets/icons/AI.svg) 사진 스타일. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 이미지 유형 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 이미지 유형. 가능한 값은 사진, 스케치, 페인팅, digital_cartoon, infographics, graphic_design, collage 및 software_screenshot입니다. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 카메라 위치 | 자산의 카메라 위치 ![AI 생성](/help/assets/icons/AI.svg)합니다. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 카메라 근접성 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 카메라 근접 정도. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 사람 카테고리 | 에셋에 대한 ![AI가 생성됨](/help/assets/icons/AI.svg)개의 사람 범주. 가능한 값은 사람, 남자, 여자, 소셜 그룹, 군중, 사람, 소년, 소녀, 그리고 아이입니다. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 시각적 콘텐츠 밀도 | 에셋의 ![AI 생성](/help/assets/icons/AI.svg) 시각적 콘텐츠 밀도. 가능한 값은 낮음, 중간 또는 높음입니다. 낮은 컨텐츠 밀도는 이미지의 단위 영역당 존재하는 정보의 양이 작음을 의미한다. | 차원 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 시각적 주의 분산 | ![AI 생성](/help/assets/icons/AI.svg) 자산의 시각적 주의 확산. 가능한 값은 낮음, 중간 또는 높음입니다. 주의력 분산은 한 사진의 서로 다른 부분 사이에서 관람자의 주의가 나누어지는 정도를 의미한다. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 조명 조건 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 조명 상태. 가능한 값은 골든아워, 블루아워, 한낮, 오버캐스트, 밤, 하이 키, 로우 키, 채광, 백열등, 형광, 화려한 스튜디오 입니다. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |
| 자산 카메라 설정 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 카메라 설정. 가능한 값은 빠른 셔터 속도, 긴 노출입니다. 보케 흐림, 동작 흐림, 기울기 이동 흐림, 플래시, 광각, 흑백, 초현실적, 이중 노출, 매크로 및 일반 모드. | Dimension<br/>파생 필드 | \| 표시 값 없음<br/>가장 최근 \| 세션 |

{style="table-layout:fixed"}


## 자산 이벤트

| 제목 | 설명 | 유형 | 설정 |
|---|---|---|---|
| 자산 조회수 | 자산 보기 수에 대한 수량화 가능한 측정입니다. | 지표 | 값 계산<br/>십진수 \| 소수점 이하 자리 수: 0 |
| 자산 클릭 수 | 자산 클릭 수에 대한 수량화 가능한 측정입니다. | 지표 | 값 계산<br/>십진수 \| 소수점 이하 자리 수: 0 |

{style="table-layout:fixed"}


<!--
## Other derived fields

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Path | Full path to the experience. | Derived Field | |
| Experience Path Root | Root path to the experience. | Derived Field | |
| Asset Location | Location of the asset. | Derived Field | |
| Asset Percenption ID + Asset ID | Combiination of asset perception identifier and asset identifier | Derived Field | |

{style="table-layout:fixed"}
-->

## 계산된 지표

| 제목 | 설명 | 유형 | 설정 |
|---|---|---|---|
| 자산 클릭스루 비율 | 자산 클릭 수 / 자산 보기 | 계산된 지표 | |
| 경험 클릭스루 비율 | 경험 클릭수 / 경험 보기 | 계산된 지표 | |

{style="table-layout:fixed"}

