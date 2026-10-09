---
title: Customer Journey Analytics에서 유료 미디어 데이터 수집
description: Adobe Experience Platform 소스 커넥터를 통해 유료 미디어 데이터를 수집하고 Customer Journey Analytics에서 연결, 데이터 보기 및 지표를 준비하는 방법에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Use Cases
hold: true
role: Admin
source-git-commit: 29a21d57b6b50d873a4464d1a705c1b4855dd3ea
workflow-type: tm+mt
source-wordcount: '1198'
ht-degree: 0%
---

# 유료 미디어 데이터 수집 및 사용

유료 미디어 데이터에는 광고 성능과 [!DNL Meta Ads], [!DNL Google Ads], [!DNL TikTok] 및 [!DNL LinkedIn]과(와) 같은 플랫폼의 메타데이터가 포함됩니다. 이 안내서에서는 해당 데이터를 Adobe Experience Platform으로 수집하고 보고 및 분석을 위해 Customer Journey Analytics에서 사용할 수 있도록 설정하는 방법을 설명합니다.

유료 미디어 데이터는 일반적으로 다음 세 단계를 통해 이동합니다.

1. Advertising 플랫폼은 캠페인, 광고, 에셋 및 성능 데이터를 제공합니다.
1. Adobe Experience Platform은 소스 커넥터를 통해 해당 데이터를 수집하여 표준 유료 미디어 데이터 세트에 저장합니다.
1. Customer Journey Analytics은 Workspace에서 데이터를 분석할 수 있도록 연결 및 데이터 보기를 통해 데이터 세트를 노출합니다.

유료 미디어 데이터는 Experience Platform 소스 커넥터를 통해 수집됩니다. 예를 들어 Advertising 범주에서 [!DNL Meta Ads] 커넥터를 사용할 수 있습니다. 지원되는 소스를 연결하면 Adobe이 글로벌 유료 미디어 스키마 및 필드 그룹을 기반으로 표준 유료 미디어 데이터 세트를 프로비저닝합니다.

## 사전 요구 사항

Experience Platform에서 다음 액세스 권한이 있는지 확인하십시오.

* 소스를 보고 관리할 수 있는 권한.
* 스키마, 데이터 세트 및 데이터 흐름을 만들 수 있는 권한.
* 작업하도록 선택한 샌드박스. 설치 단계를 진행하기 전에 샌드박스를 선택합니다.

[!DNL Meta Ads]을(를) 소스로 사용하는 경우 다음 사전 요구 사항도 있는지 확인하십시오.

* 캠페인, 광고 세트, 광고 및 자산을 포함하는 하나 이상의 활성 광고 계정이 있는 [!DNL Meta Business Manager] 계정입니다.
* [!DNL Graph API] 및 [!DNL Marketing API]에 대해 인증되고 [!DNL Meta] 개발자 콘솔에 구성되어 [!DNL Business Manager]에 연결된 [!DNL Meta] 앱입니다.
* 앱에 대해 `ads_read` 및 `ads_management` 범위를 승인했습니다.
* 연결을 승인한 사용자에 대한 광고주 수준 이상의 액세스 권한.
* [!DNL Meta] 사용자 인터페이스에서 의도한 광고 계정에 대한 액세스를 확인했습니다.

커넥터에 대한 인증에서 [!DNL OAuth 2.0]을(를) 사용합니다. 설치하는 동안 로그인하고 커넥터에 대한 액세스 권한을 부여합니다. 액세스 토큰은 만료되므로 부여가 취소되는 경우 연결을 재인증할 준비를 하십시오.

## 데이터 모델

[Content Analytics 유료 미디어 자동 구성](/help/content-analytics/config/paid-media.md)에서는 유료 미디어 데이터 모델에 대해 자세히 설명합니다. 이러한 자동 구성은 일반적으로 필요한 데이터 세트와 구성 요소를 만들고, 콘텐츠를 특별히 분석하기 위해 구성합니다.

유료 미디어 데이터 모델을 이해하려면 이 설명서 를 참조하십시오. Customer Journey Analytics에서 사용할 데이터 세트를 결정할 때 사용합니다. 구성된 소스 커넥터는 이러한 데이터 세트를 생성합니다.

## 유료 미디어 데이터 수집

소스를 연결하고 유료 미디어 데이터를 Experience Platform에 수집하려면 다음 프로세스를 사용하십시오.

1. 필요한 Experience Platform 소스 권한 및 광고 플랫폼 액세스 권한이 있는지 확인합니다.
1. Experience Platform에서 **[!UICONTROL 소스]** > **[!UICONTROL 카탈로그]** > **[!UICONTROL Advertising]**(으)로 이동합니다.
1. 유료 미디어 데이터 세트를 포함하는 샌드박스에 있는지 확인합니다.
1. 사용할 커넥터(예: **[!DNL Meta Ads]**)를 선택하십시오. **[!UICONTROL 설정]**&#x200B;을 선택하여 새 연결을 만들거나 **[!UICONTROL 데이터 추가]**&#x200B;를 선택하여 기존 연결에 데이터를 더 추가합니다.
1. 필요한 광고주 수준 액세스 권한이 있는 사용자로 로그인하여 [!DNL OAuth 2.0]을(를) 인증합니다.
1. 수집할 광고 계정, 엔티티 및 insight 데이터를 선택합니다.
1. 조회 데이터 세트 및 요약 지표 데이터 세트가 올바르게 프로비저닝되었는지 확인합니다.
1. 데이터 흐름 설정을 입력하고 대상 데이터 세트를 확인하고 수집 일정을 구성합니다.
1. 데이터 흐름을 저장하고 **[!UICONTROL 소스]** > **[!UICONTROL 데이터 흐름]**&#x200B;에서 실행을 모니터링합니다.
1. 표준 유료 미디어 데이터 세트가 존재하며 데이터를 포함하는지 확인합니다.

Customer Journey Analytics으로 이동하기 전에 수집된 데이터의 유효성을 검사합니다.

* 엔터티 `GUID` 및 기본 ID 값이 요약 지표 및 조회 데이터 세트에서 일관되게 채워졌는지 확인하십시오.
* 모든 요약 지표 행에 타임스탬프가 포함되어 있는지 확인합니다.
* 차원(예: `channel`, `adNetwork`) 및 지표(예: `impressions`, `clicks`, `spend`)와 같은 주요 보고 필드에 값이 있는지 확인하십시오. 일부 원본 플랫폼이 `region`과(와) 같은 일부 필드를 채우는 것은 아닙니다.
* 관련 계정 전체에서 통화 및 시간대 값이 일관되는지 확인합니다.

## 유료 미디어 데이터 사용

Customer Journey Analytics은 Experience Platform 데이터 세트에 대해 직접 보고하지 않습니다. 대신 연결을 통해 데이터 세트를 노출한 다음 보고에 사용되는 차원, 지표 및 논리를 정의하는 데이터 보기를 빌드합니다.

### 연결 만들기 또는 업데이트

연결을 만들거나 업데이트하려면 다음 프로세스를 사용하십시오.

1. Customer Journey Analytics에서 [기존 연결을 만들거나 편집합니다](/help/connections/create-connection.md).
1. 유료 미디어 데이터 세트를 포함하는 샌드박스를 연결 구성의 일부로 선택해야 합니다.
1. 요약 지표 데이터 세트를 요약 데이터로 추가합니다. 여러 요약 지표 데이터 세트를 사용할 수 있는 경우 [search](/help/connections/create-connection.md#add-datasets)을(를) 사용하여 `Paid Media` 클래스별로 필터링하여 올바른 데이터 세트를 식별하십시오.
1. 각 조회 데이터 세트를 조회 데이터 세트로 추가합니다. 계정, 캠페인, 광고 그룹, 광고, 에셋 및 경험에 대한 해당 엔티티 GUID 식별자(Adobe에서 생성한 전역 키)를 사용하여 조회 데이터 세트를 요약 데이터에 조인합니다. 일부 소스 플랫폼은 기본 ID 값에 대한 조인도 지원합니다.
1. 필요한 경우, 총 유료 미디어 데이터를 ID, 추적 코드 또는 `UTM` 매개 변수와 같은 공유 메타데이터에 연결하려는 경우 클릭스트림 이벤트 데이터를 추가합니다.
1. 각 데이터 세트에 대한 [데이터 세트별 설정](/help/connections/create-connection.md#dataset-settings)을 검토하십시오.
1. 연결을 저장하고 연결이 데이터 채우기를 시작하는지 확인합니다.

유료 미디어 데이터는 집계 데이터이며 개인 수준 ID 결합에 의존하지 않습니다. 요약 테이블의 엔티티 식별자는 조회 테이블에서 유사한 ID에 조인하는 데 사용됩니다.

### 데이터 보기 만들기

연결이 준비되면 연결에 대한 하나 이상의 데이터 보기를 생성하거나 편집해야 합니다.


1. Customer Journey Analytics에서 [하나 이상의 데이터 보기를 만들거나 편집합니다](/help/data-views/create-dataview.md):
1. 표준 시간대 및 통화 등 기본 설정을 정의합니다.
1. 유료 미디어 분석에 필요한 구성 요소를 추가합니다.

다음과 같은 구성 요소를 포함합니다.

* **차원**: 캠페인, 채널, 광고 네트워크, 광고 그룹, 광고, 자산, 계정, 지역 및 장치 유형.
* **지표**: 노출 횟수, 클릭 수, 클릭스루 비율, 지출, 전환, 전환 값, 참여 및 관련 비디오 또는 노출 점유율 지표.
* **파생 필드**: [구문 분석](/help/data-views/derived-fields/derived-fields.md#url-parse), [정규 표현식](/help/data-views/derived-fields/derived-fields.md#regex-replace) 또는 [조회](/help/data-views/derived-fields/derived-fields.md#lookup) 논리를 사용하여 차원을 정규화하거나 분류하여 광고 네트워크에서 일관된 채널 및 캠페인 값을 생성합니다.
* **요약 그룹화**: [여러 데이터 세트의 관련 값을 단일 보고 차원으로 결합](/help/data-views/component-settings/summary-data-group.md)(예: 통합 유료 채널 차원).
* **계산된 지표**: CPC, CPM, CPA, CTR 및 전환율과 같은 재사용 가능한 효율성 지표를 정의합니다.

### 프로젝트를 만듭니다.

유료 미디어 데이터에 대해 보고하고 분석하려면 Analysis Workspace에서 프로젝트를 만듭니다.

## 유효성 검사

다음 체크리스트를 사용하여 구현의 유효성을 검사합니다.

### Adobe Experience Platform 확인

* 소스 권한 및 광고 플랫폼 액세스 권한이 있는지 확인합니다.
* 커넥터가 인증되었고 데이터 흐름이 일정대로 실행되고 있는지 확인합니다.
* 모든 유료 미디어 데이터 세트가 있고 채워져 있는지 확인합니다.
* 스키마에서 글로벌 유료 미디어 클래스와 필드 그룹을 사용하는지 확인합니다.
* 조인 키, 타임스탬프 및 키 보고 필드가 채워져 있는지 확인합니다.

### Customer Journey Analytics 확인

* 연결에 요약 지표 데이터 세트와 6개의 조회 데이터 세트가 포함되어 있는지 확인합니다.
* 데이터 보기에 필요한 광고 차원 및 유료 미디어 지표가 포함되어 있는지 확인합니다.
* 파생 필드가 예상대로 채널 및 캠페인 값을 정규화하는지 확인합니다.
* 요약 그룹화가 필요한 경우 다중 네트워크 데이터를 통합하는지 확인합니다.
* 계산된 지표가 조직에서 사용하는 비율에 대해 정의되었는지 확인합니다.
* Workspace 보고가 소스 광고 플랫폼 보고와 일치하는지 확인합니다.


>[!MORELIKETHIS]
>
>[Meta Ads 소스 커넥터](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/advertising/meta-ads)
>[Content Analytics 유료 미디어 자동 구성](/help/content-analytics/config/paid-media.md)
