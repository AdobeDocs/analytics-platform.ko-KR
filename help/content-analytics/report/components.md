---
title: 콘텐츠 분석 구성 요소
description: 차원, (계산된) 지표 및 파생 필드와 같은 특정 콘텐츠 분석 구성 요소에 대한 세부 정보
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: ht
source-wordcount: '910'
ht-degree: 100%

---

# 콘텐츠 분석 구성 요소

콘텐츠 분석은 Customer Journey Analytics에서 이미 사용 가능한 구성 요소에 다음과 같은 구성 요소 카테고리(차원, (계산된) 지표, 파생 필드)를 추가합니다.

* [경험 메타데이터](#experience-metadata)
* [경험 속성](#experience-attributes)
* [경험 이벤트](#experience-events)
* [자산 메타데이터](#asset-metadata)
* [자산 속성](#asset-attributes)
* [자산 이벤트](#asset-events)
* [계산된 지표](#calculated-metrics)

아래 테이블에서 ![AI 생성](/help/assets/icons/AI.svg)은 AI/ML에서 생성된 속성/값 쌍을 나타냅니다.

## 경험 메타데이터

| 제목 | 설명 | 유형 |
|---|---|---|
| 경험 채널 | 경험에 대한 채널. | 차원 |
| 경험 ID | 경험에 대한 고유 ID. | 차원 |
| 경험 썸네일 URL | 경험의 썸네일 URL. | 차원 |
| 경험 가로 비율 깊이 | 경험의 가로 백분율 깊이를 정량화할 수 있는 값. | 차원<br/>파생 필드 |
| 경험 세로 비율 깊이 | 경험의 세로 백분율 깊이를 정량화할 수 있는 값. | 차원<br/>파생 필드 |

{style="table-layout:fixed"}



## 경험 속성

| 제목 | 설명 | 유형 |
|---|---|---|
| 경험 속성 | 모든 경험 속성 이름 및 값의 ![AI 생성](/help/assets/icons/AI.svg) 전체 목록 | 차원<br>파생 필드 |
| 경험 가독성 점수 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 가독성 점수 | 차원 |
| 경험 키워드 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 키워드. | 차원<br>파생 필드 |
| 경험 설득 전략 | 주어진 경험에 존재하는 ![AI 생성](/help/assets/icons/AI.svg) 설득 전략. 가능한 값은 다음과 같습니다. 사회적 정체성, 사회적 증명, 권위, 구체성, 진입장벽, 반발 극복, 호혜성, 고정 및 비교, 사회적 영향, 희소성, 인류애. | 차원<br/>파생 필드 |
| 경험 내러티브 | 마케터의 관점에서 관련성을 기반으로 경험이 구축하고 있는 ![AI 생성](/help/assets/icons/AI.svg) 내러티브. | 차원<br/>파생 필드 |
| 경험 톤 | 마케터의 관점에서 관련성을 기반으로 경험이 구축하고 있는 ![AI 생성](/help/assets/icons/AI.svg) 톤. | 차원<br/>파생 필드 |
| 경험 마케팅 감정 | 독자가 텍스트를 읽을 때 경험의 일부로 느끼는 ![AI 생성](/help/assets/icons/AI.svg) 감정: 긴박감, 배타성, 격려, 도전, 호기심, 성취, 신뢰, 단순성, 매혹. | 차원<br/>파생 필드 |
| 경험 이모지 개수 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 이모지의 수. | 지표 |
| 경험 해시태그 개수 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 해시태그의 수. | 지표 |
| 경험 문장 수 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 문장의 수. | 지표 |
| 경험 중지 단어 비율 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 중지 단어의 수. | 지표 |
| 경험 텍스트 인용 수 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 텍스트 인용의 수. | 지표 |
| 경험 단어 수 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 단어의 수. | 지표 |
| 경험 문장당 단어 수 | 경험에 대한 ![AI 생성](/help/assets/icons/AI.svg) 문장당 단어 수. | 지표 |

{style="table-layout:fixed"}


## 경험 이벤트

| 제목 | 설명 | 유형 |
|---|---|---|
| 경험 조회수 | 경험에 대한 조회수를 정량화할 수 있는 척도. | 지표 |
| 경험 클릭 수 | 경험에 대한 클릭 수를 정량화할 수 있는 척도. | 지표 |

{style="table-layout:fixed"}


## 자산 메타데이터

| 제목 | 설명 | 유형 |
|---|---|---|
| 자산 ID | 자산의 고유 식별자. 자산 바이너리는 고유성을 결정합니다. 자산 바이너리가 변경되면 ID도 변경됩니다. 고유 ID는 URL일 수도 있지만 해시로 생성될 수도 있습니다. | 차원 |
| 자산 HTML 경로 | 자산에 대한 연결된 HTML 경로. | 차원 |
| 자산 링크 URL | 자산에 가장 가까운 페이지 앵커. | 차원 |
| 자산 표시 폭 | 콘텐츠 자산 표시 폭. | 차원 |
| 자산 표시 높이 | 콘텐츠 자산 표시 높이. | 차원 |
| 자산 절대 왼쪽 위치 | 콘텐츠 자산 절대 왼쪽 위치. | 차원 |
| 자산 절대 상단 위치 | 콘텐츠 자산 절대 상단 위치. | 차원 |

{style="table-layout:fixed"}


## 자산 속성

| 제목 | 설명 | 유형 |
|---|---|---|
| 자산 속성 | 모든 자산 속성 이름 및 값의 ![AI 생성](/help/assets/icons/AI.svg) 전체 목록 | 차원<br>파생 필드 |
| 자산 방향 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 방향. | 차원<br/>파생 필드 |
| 자산 전체 톤 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 전체 톤. | 차원<br/>파생 필드 |
| 자산 전경색 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 전경색. | 차원<br/>파생 필드 |
| 자산 배경색 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 배경색. | 차원<br/>파생 필드 |
| 자산 태그 | 자산에 대한 ![AI 생성](/help/assets/icons/AI.svg) 태그. | 차원<br/>파생 필드 |
| 자산 장면 | 자산에 대한 ![AI 생성](/help/assets/icons/AI.svg) 장면. | 차원<br/>파생 필드 |
| 자산 오브젝트 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 오브젝트. | 차원<br/>파생 필드 |
| 자산 포토그래피 스타일 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 포토그래피 스타일. | 차원<br/>파생 필드 |
| 자산 이미지 유형 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 이미지 유형. 가능한 값은 사진, 스케치, 그림, 디지털 만화, 인포그래픽, 그래픽 디자인, 콜라주, 소프트웨어 스크린샷입니다. | 차원<br/>파생 필드 |
| 자산 카메라 위치 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 카메라 위치. | 차원<br/>파생 필드 |
| 자산 카메라 근접성 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 카메라 근접성. | 차원<br/>파생 필드 |
| 자산 사람 카테고리 | 자산에 대한 ![AI 생성](/help/assets/icons/AI.svg) 사람 카테고리. 가능한 값은 사람, 남자, 여자, 사회 집단, 군중, 사람들, 소년, 소녀, 아이입니다. | 차원<br/>파생 필드 |
| 자산 시각적 콘텐츠 밀도 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 시각적 콘텐츠 밀도. 가능한 값은 낮음, 보통, 높음입니다. 콘텐츠 밀도가 낮다는 것은 이미지의 단위 면적당 존재하는 정보량이 적다는 것을 의미합니다. | 차원 |
| 자산 시각적 주의 분산 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 시각적 주의 확산. 가능한 값은 낮음, 보통, 높음입니다. 주의 분산은 뷰어의 주의가 그림의 여러 부분으로 분산되는 정도를 말합니다. | 차원<br/>파생 필드 |
| 자산 조명 조건 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 조명 조건. 가능한 값은 황금시간대, 땅거미가 진 때, 정오, 흐림, 밤, 하이키, 로우키, 일광, 백열등, 형광등, 컬러풀, 스튜디오입니다. | 차원<br/>파생 필드 |
| 자산 카메라 설정 | 자산의 ![AI 생성](/help/assets/icons/AI.svg) 카메라 설정. 가능한 값은 빠른 셔터 속도, 장시간 노출, 보케 블러, 모션 블러, 틸트-시프트 블러, 플래시, 광각, 흑백, 초현실주의, 이중 노출, 매크로, 일반 모드입니다. | 차원<br/>파생 필드 |

{style="table-layout:fixed"}


## 자산 이벤트

| 제목 | 설명 | 유형 |
|---|---|---|
| 자산 조회수 | 자산에 대한 조회수를 정량화할 수 있는 척도. | 지표 |
| 자산 클릭 수 | 자산에 대한 클릭 수를 정량화할 수 있는 척도. | 지표 |

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

| 제목 | 설명 | 유형 |
|---|---|---|
| 자산 클릭률 | 자산 클릭수/자산 조회수 | 계산된 지표 |
| 경험 클릭스루 비율 | 경험 클릭수/경험 조회수 | 계산된 지표 |

{style="table-layout:fixed"}

