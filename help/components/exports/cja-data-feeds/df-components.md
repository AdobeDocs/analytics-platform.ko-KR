---
title: Customer Journey Analytics 데이터 피드에서 사용할 수 있는 구성 요소
description: Customer Journey Analytics 데이터 피드를 만들 때 필수, 지원되지 않음, 제한됨 또는 대체해야 하는 차원 및 지표에 대해 알아봅니다.
hide: true
feature: Components
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: adc7e85339e89c181375c0d3ea5c228d473239a7
workflow-type: tm+mt
source-wordcount: '1419'
ht-degree: 43%
---
# 데이터 피드의 구성 요소 가용성

{{release-limited-testing}}

일부 Customer Journey Analytics 구성 요소는 데이터 피드에서 사용할 수 없습니다. 일부 차원은 모든 데이터 피드에 포함되며, 일부 구성 요소는 포함될 수 없으며, 일부 지표는 대체 요소로 대체해야 합니다.

[데이터 피드를 만들](/help/components/exports/cja-data-feeds/create-feed.md)때 포함할 수 있는 구성 요소를 이해하려면 다음 정보를 사용하십시오.

## 필요한 차원 {#required-dimensions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_required_dimensions"
>title="필요한 차원"
>abstract="모든 데이터 피드는 차원 이름 옆에 **필수** 레이블로 식별되는 특정 차원을 포함해야 합니다. 이러한 차원은 이벤트 수준 분석에 필요한 최소한의 구조를 제공합니다."

<!-- markdownlint-enable MD034 -->

다음 차원은 기본적으로 모든 데이터 피드에 포함되며 제거할 수 없습니다.

| 차원 이름 | 참고 | 데이터 피드 | 기타 보고 |
|---|---|---|---|
| 타임스탬프 UTC | 이벤트가 발생한 날짜 및 시간으로, UTC 시간대로 표시됩니다. 초 미만(초단위) 세부 기간을 지원합니다. | 필수 여부 | 사용할 수 없음 |
| 행 ID | 데이터 피드에 포함된 각 행의 고유 식별자입니다. | 필수 여부 | 사용할 수 없음 |
| 세션 ID | 데이터 피드에 포함된 각 세션의 고유 식별자입니다. | 필수 여부 | 사용할 수 없음 |
| 개인 ID | 데이터 보기 및 연결에 대한 개인 식별자 | 필수 여부 | 선택 사항 표준 |
| 계정 ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 계정 컨테이너를 사용할 때의 계정 ID | 필수 여부 | 선택 사항 표준 |

## 지원되지 않는 차원 {#unsupported-dimensions}

Customer Journey Analytics 표준 차원은 데이터 피드에 포함할 수 없습니다. 다음 표에는 이러한 차원이 나열되어 있습니다.

| 차원 이름 | 참고 | 데이터 피드 |
|---|---|---|
| 5분 | 이벤트가 발생한 5분 간격(내림) | 사용할 수 없음 |
| 15분 | 이벤트 발생 시 15분 간격(내림) | 사용할 수 없음 |
| 30분 | 이벤트 발생 시 30분 간격(내림) | 사용할 수 없음 |
| 일 | 이벤트 발생 일 | 사용할 수 없음 |
| 요일 | 이벤트가 발생한 요일 | 사용할 수 없음 |
| 날짜 (월 기준) | 이벤트가 발생한 날짜 | 사용할 수 없음 |
| 시간 | 이벤트 발생 시간(내림) | 사용할 수 없음 |
| 시간 | 이벤트가 발생한 시간(내림) | 사용할 수 없음 |
| 분 | 이벤트 발생 시간(분)(내림) | 사용할 수 없음 |
| 분/시간 | 이벤트가 발생한 시간(분)(내림) | 사용할 수 없음 |
| 월 | 이벤트 발생 월 | 사용할 수 없음 |
| 월(연 기준) | 이벤트가 발생한 월의 월 | 사용할 수 없음 |
| 분기 | 이벤트 발생 분기 | 사용할 수 없음 |
| 사분기 | 이벤트가 발생한 사분기 | 사용할 수 없음 |
| Second | 이벤트가 발생한 두 번째 시간(내림) | 사용할 수 없음 |
| 주 | 이벤트 발생 주 | 사용할 수 없음 |
| 주(한 해 기준) | 이벤트가 발생한 주 | 사용할 수 없음 |
| 년 | 이벤트 발생 연도 | 사용할 수 없음 |

## 지원되지 않는 지표 {#unsupported-metrics}

다음 Customer Journey Analytics 표준 지표는 데이터 피드에 포함할 수 없습니다.

| 지표 이름 | 참고 | 데이터 피드 |
|---|---|---|
| Adobe 방문자 프로필 | | 사용할 수 없음 |
| Adobe Opportunities Union | | 사용할 수 없음 |
| Adobe 영업 기회 프로필 | | 사용할 수 없음 |
| Adobe 계정 조합 | | 사용할 수 없음 |
| Adobe 계정 프로필 | | 사용할 수 없음 |
| Adobe 구매 그룹 연합 | | 사용할 수 없음 |
| Adobe 구매 그룹 프로필 | | 사용할 수 없음 |
| Adobe 글로벌 계정 연합 | | 사용할 수 없음 |
| Adobe 글로벌 계정 프로필 | | 사용할 수 없음 |
| Adobe 사람 조합 | | 사용할 수 없음 |
| Adobe 사용자 프로필 | | 사용할 수 없음 |

## 함께 사용할 수 없는 차원 {#incompatible-dimensions}

<!-- markdownlint-disable MD034 -->

<!-- pretty sure this isn't being used -->

>[!CONTEXTUALHELP]
>id="cja_datafeed_user_agent"
>title=""
>abstract="사용자 에이전트 데이터와 디바이스 조회 데이터는 동일한 데이터 피드 구성에 존재할 수 없습니다."

<!-- markdownlint-enable MD034 -->

>[!IMPORTANT]
>
>특정 차원은 Experience Platform 데이터 세트에서 함께 사용할 수 없으므로 동일한 데이터 피드에 포함할 수 없습니다.
>
>데이터 피드에 **사용자 에이전트** 또는 **모바일 ID** 차원을 포함하도록 선택한 경우 아래 나열된 차원을 데이터 피드에 추가할 수 없습니다.
>
>웹 SDK을 사용하는 경우 데이터가 Experience Platform 데이터 세트에 도달하기 전에 데이터 스트림에 이 제한이 적용됩니다. 자세한 내용은 데이터 수집 가이드의 [데이터 스트림 만들기 및 구성](https://experienceleague.adobe.com/ko/docs/experience-platform/datastreams/configure)에서 [장치 조회 구성](https://experienceleague.adobe.com/ko/docs/experience-platform/datastreams/configure#geolocation-device-lookup)을 참조하십시오.

다음 차원은 **사용자 에이전트** 또는 **Mobile ID** 차원과 함께 사용할 수 없습니다.

>[!NOTE]
>
>다음 목록은 기본 차원 이름을 사용합니다. 데이터 보기에서 이름이 변경된 차원은 사용자 지정 이름과 함께 데이터 피드에 표시됩니다.


* 브라우저 유형
* 브라우저
* 브라우저 ID
* 모바일 제조업체
* 모바일 디바이스 유형
* 모바일 오디오 지원
* 모바일 DRM
* 모바일 Java VM
* 모바일 정보 서비스
* 모바일 이미지 지원
* 모바일 색상 깊이
* 모바일 네트 프로토콜
* 모바일 디바이스 번호
* 모바일 최대 이메일 길이
* 모바일 메일 데코레이션
* 모바일 Push To Talk
* 모바일 화면 너비
* 모바일 최대 브라우저 URL 길이
* 모바일 운영 체제 (더 이상 사용되지 않음)
* 모바일 화면 높이
* 모바일 비디오 지원
* 모바일 쿠키 지원
* 모바일 최대 책갈피 길이
* 모바일 화면 크기
* 모바일 디바이스 이름
* 운영 체제 유형
* 운영 체제
* 운영 체제 ID

## 대체가 필요한 지표 {#substitute-metrics}

다음 Customer Journey Analytics 지표를 대체해야 합니다.

| 지표 이름 | 참고 | 데이터 피드 |
|---|---|---|
| 계정 ([!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}) | 연결에 지정된 계정 ID를 기반으로 함 | 사용할 수 없음. 계정 ID 고유 개수 사용. |
| 구매 그룹 [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 연결의 구매 그룹 ID를 기반으로 하는 구매 그룹 | 사용할 수 없음. 구매 그룹 ID의 고유 개수를 사용합니다. |
| 이벤트 | 연결의 모든 이벤트 데이터 세트의 행 수 | 사용할 수 없음. 행 ID의 고유 개수 사용. |
| 글로벌 계정 ([!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}) | 연결의 글로벌 계정 ID 기반 | 사용할 수 없음. 글로벌 계정 ID의 고유 개수를 사용합니다. |
| 기회 ([!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}) | 연결의 영업 기회 ID를 기반으로 하는 영업 기회 | 사용할 수 없음. 영업 기회 ID 고유 개수 사용. |
| 사람 | 연결에 지정된 개인 ID 기반 | 사용할 수 없음. 개인 ID 고유 개수 사용. |
| 대화 | 대화 수 | 사용할 수 없음. 대화 ID 고유 개수 사용. |
| 세션 종료 | 세션의 마지막 이벤트였던 이벤트 수 | 사용할 수 없음 |
| 세션 시작 | 세션의 첫 번째 이벤트였던 이벤트 수 | 사용할 수 없음 |
| 세션 | 데이터 보기의 세션 설정을 기반으로 합니다. | 사용할 수 없음. 세션 ID의 고유 개수 사용. |
| 체류 시간 (초) | 서로 다른 두 차원 값 사이의 시간을 합합니다. | 사용할 수 없음 |

## 선택 사항 표준 구성 요소 {#optional-standard-components}

| 구성 요소 이름 | 유형 | 참고 | 데이터 피드 |
|---|---|---|---|
| 오전/오후 | 차원 시간 분할 | 오전 또는 오후 | 사용할 수 없음 |
| 배치 ID | 차원 | Experience Platform 배치용 식별자 | 사용 가능 |
| 데이터 세트 ID | 차원 | Experience Platform 데이터 세트에 대한 식별자 | 사용 가능 |
| 날짜 (월 기준) | 차원 시간 분할 | 1-31 | 사용할 수 없음 |
| 요일 | 차원 시간 분할 | 월요일부터 일요일까지 | 사용할 수 없음 |
| 일(한 해 기준) | 차원 시간 분할 | 1-366 | 사용할 수 없음 |
| 이벤트 심도 | 치수 | 순차적 숫자 값(1, 2, 3 등) 세션 내의 각 이벤트 상호 작용에 할당됨<p>각 새 세션이 시작될 때 재설정</p> | 사용 가능 |
| 시간 | 차원 시간 분할 | 0-23 | 사용할 수 없음 |
| 월(연 기준) | 차원 시간 분할 | 1월-12월 | 사용할 수 없음 |
| 최초 세션 | 지표 | 보고 기간 내에 개인의 첫 번째 정의된 세션 | 사용할 수 없음 |
| 재방문 세션 | 지표 | 개인의 첫 번째 세션이 아닌 세션 | 사용할 수 없음 |
| 개인 ID 네임스페이스 | 차원 | 개인 ID가 구성하는 ID 유형(예: 이메일 또는 쿠키 ID) | 사용 가능 |
| 글로벌 계정 ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 차원 | 글로벌 계정 컨테이너를 사용할 때의 글로벌 계정 ID | 사용 가능 |
| 영업 기회 ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 차원 | 영업 기회 컨테이너를 사용할 때의 영업 기회 ID | 사용 가능 |
| 구매 그룹 ID [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} | 차원 | 구매 그룹 컨테이너를 사용할 때 구매 그룹 ID | 사용 가능 |
| 사분기 | 차원 시간 분할 | Q1, Q2, Q3, Q4 | 사용할 수 없음 |
| 세션 반복 | 지표 | 개인의 첫 번째 세션이 아닌 세션 | 사용할 수 없음 |
| 세션 유형 | 차원 | 두 가지 값: 최초 또는 재방문 | 사용할 수 없음 |
| 이벤트당 소비한 시간 | 차원 | 소비한 시간 지표를 이벤트 버킷에 버킷팅합니다 | 사용할 수 없음 |
| 세션당 소비한 시간 | 차원 | 소비한 시간 지표를 세션 버킷에 버킷팅합니다 | 사용할 수 없음 |
| 사용자당 소비한 시간 | 차원 | 소비한 시간 지표를 사용자 버킷에 버킷팅합니다 | 사용할 수 없음 |
| 주말/평일 | 차원 시간 분할 | 주말 또는 평일 | 사용할 수 없음 |
