---
title: 브랜드 가시성 인바운드 통합 구성
description: Customer Journey Analytics과의 브랜드 가시성 통합을 구성하는 방법에 대해 알아봅니다
feature: Experience Platform Integration
role: Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e3958dfbad19f5fdd78b2755817d21afad8f8e84
workflow-type: tm+mt
source-wordcount: '2118'
ht-degree: 0%
---
# 인바운드 통합 설정 및 구성

이 문서에서는 Customer Journey Analytics과의 브랜드 가시성 인바운드 통합 설정 및 구성을 위한 [사전 요구 사항](#prerequisites), [책임](#responsibilities), [확인하는 단계](#verification), [문제 해결 단계](#troubleshoot) 및 [완료 기준](#completion-criteria)에 대해 자세히 설명합니다.

## 사전 요구 사항

인바운드 통합을 활성화하기 전에 다음 전제 조건을 고려하십시오. 아래의 [확인 절차](#verification)를 사용하여 각 필수 구성 요소를 확인하십시오.

### BYOCDN 로그 전달

CDN 액세스 로그는 각 브랜드 가시성 사이트에 대해 Adobe Brand Visibility으로 전송 및 수신해야 브랜드 가시성 소스 커넥터를 실행할 수 있습니다.

이 요구 사항은 각 브랜드 가시성 사이트에 적용됩니다. 한 사이트, 도메인 또는 하위 도메인에 대한 CDN 구성 또는 로그 피드는 해당 사이트만 다룹니다.

핸드오프의 두 부분 확인:

1. 필요한 액세스 로그를 Adobe이 제공하는 Amazon S3 대상에 전달하도록 관련 CDN 또는 로그 파이프라인을 구성했습니다.
1. 브랜드 가시성이 관련 사이트에 대한 로그를 수신 및 감지하고 있습니다. 그런 다음 Experience Platform의 Adobe Brand Visibility 소스에서 사이트를 선택할 수 있습니다.

BYOCDN 로그 전달은 자동화된 에이전트 트래픽 분석에 사용되는 서버측 CDN 요청 데이터를 제공합니다. 데이터는 브라우저에서 실행되는 JavaScript 태그에 따라 달라지지 않습니다. 필수
CDN 로그 피드는 다운스트림 요약 데이터 세트에 의도된 브랜드 가시성 에이전트 트래픽 데이터가 포함되어 있는지 확인합니다. 자세한 내용은 [BYOCDN 로그 전달 참조](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview)를 참조하십시오.

### 필수 정보

각 브랜드 가시성 사이트에 대해 아래 표에 나열된 모든 필수 세부 정보에 대한 값이 있는지 확인합니다.

| 필수 값 | 확인 또는 메모 |
|---|---|
| 브랜드 가시성 사이트 또는 도메인 | CDN 로그 전달이 적용되는 사이트를 확인합니다. |
| CDN 공급자 | 사이트를 제공하는 CDN을 식별합니다. |
| CDN 로그 전달 상태 | 브랜드 가시성이 사이트에 대한 로그를 전달하고 감지한다는 증명입니다. |
| 브랜드 가시성 소스에서 사용 가능한 사이트 | 브랜드 가시성 소스에서 사이트를 선택할 수 있는지 확인합니다. 사이트는 Brand Visibility에서 구문 분석된 CDN 로그의 가용성에 따라 사용할 수 있습니다. |
| IMS 조직 | Brand Visibility, Experience Platform과 연결된 정확한 IMS 조직을 사용합니다. |
| 샌드박스 | 인바운드 통합을 위해 지정된 정확한 샌드박스 이름을 사용합니다. |
| 연결 | 데이터 세트를 포함해야 하는 고객 여정 연결을 식별합니다. |
| 데이터 보기 | 구성 요소를 포함해야 하는 신규 또는 기존 Customer Journey Analytics 데이터 보기를 식별합니다. |
| 관리자 또는 소유자 | 구성 담당자의 이름 또는 팀을 입력합니다. |

계속하기 전에 Adobe Brand Visibility 소스에서 각 사이트를 선택할 수 있는지 확인하십시오.

### 샌드박스

해당 샌드박스의 **[!UICONTROL 데이터 세트]**&#x200B;에 데이터 세트가 나타난 후 데이터 세트를 CJA 연결에 추가할 수 있습니다.

다음을 확인하십시오.

* IMS 조직
* Target Experience Platform 샌드박스

Target AEP 샌드박스는 해당 Customer Journey Analytics 연결 또는 데이터 세트를 포함하는 연결에서 사용하는 동일한 이름의 샌드박스입니다.

고객은 Adobe에서 관리되는 데이터 세트가 생성되었음을 확인한 후에만 해당 CJA 연결에 데이터 세트를 추가할 수 있습니다.

### 요약 데이터 세트

인바운드 통합은 LLM, 보트 및 자동화된 에이전트와 연결된 서버측 CDN 요청 정보가 포함된 Experience Platform의 집계된 요약 데이터 세트를 제공합니다
트래픽.

Brand Visibility은 CDN 액세스 로그를 사용하여 보트 및 자동화된 에이전트의 요청을 식별합니다. 이 트래픽은 브라우저 JavaScript 태그를 실행하지 않으므로 기존 웹 분석 구현을 통해 캡처되지 않습니다.

인바운드 통합, 데이터 집합 구조 및 사용 가능한 필드에 대한 자세한 설명은 [데이터 집합 정보](#about-the-dataset)를 참조하세요.

브랜드 가시성 소스는 다음을 사용하여 Experience Platform에서 요약 데이터 세트를 만듭니다.

* **[!UICONTROL XDM 요약 지표]** 클래스
* **[!UICONTROL CDN 요청 요약]** 필드 그룹
* **[!UICONTROL cdn]** 개체에 구성된 필드

커넥터는 다음 명명 패턴을 사용하여 각 브랜드 가시성 사이트에 대한 데이터 집합을 만듭니다. <code>Adobe Brand Visibility(ABV) 데이터 집합 - _구성표 없는 baseUrl_</code>. <br/>(예: <https://example.com> 사이트에 대해 `Adobe Brand Visibility (ABV) Dataset - example.com`).

이 명명 규칙이 채택되기 전에 만들어진 데이터 집합은 이전 패턴 <code>LLM 최적화(LLMO) 데이터 집합 - _구성표 없는 baseUrl_&#x200B;을(를) 표시합니다.</code>.

데이터 흐름을 만든 샌드박스 내의 **[!UICONTROL 데이터 세트]**&#x200B;에서 데이터 세트를 찾습니다.

데이터 세트는 집계된 요약 데이터입니다. Customer Journey Analytics에서 요청 볼륨을 분석할 때 데이터 세트 행을 카운트하지 않고 제공된 **[!UICONTROL CDN 요청 카운트]** 지표를 사용하십시오.

특정 브랜드 가시성 사이트에 대해 생성된 데이터 세트 스키마의 사용 가능한 필드를 확인합니다. 데이터 보기의 구성을 계획하려면 필드를 검토하십시오.

## 책임

브랜드 가시성 소스를 활성화한 후 브랜드 가시성:

* 선택한 사이트에 대한 요약 데이터 세트를 제공합니다.
* 데이터 흐름을 만든 샌드박스에 데이터 세트를 놓습니다.

고객으로서의 책임은 다음과 같습니다.

* CDN 로그가 각 브랜드 가시성 사이트에 대해 브랜드 가시성으로 전달되고 수신되도록 하기 위해.
* 올바른 샌드박스에서 브랜드 가시성 소스를 활성화하려면 사이트를 선택할 수 있는지 확인하고 선택합니다.
* 데이터 세트를 포함해야 하는 Customer Journey Analytics 연결을 선택하려면 다음을 수행하십시오.
* 해당 연결에 데이터 세트를 추가합니다.
* 관련 Customer Journey Analytics 데이터 보기의 구성 요소로 표시할 필드를 선택하려면 를 클릭하십시오.
* 결과 차원 및 지표가 의도한 분석을 지원하는지 확인하기 위해

>[!IMPORTANT]
>
>관리되는 커넥터는 Experience Platform 데이터 세트를 만들고 채운 후 의도적으로 중지됩니다. Adobe은 Customer Journey Analytics 연결 또는 데이터 보기를 수정하지 않습니다.

데이터 세트는 연결에 추가할 때까지 Customer Journey Analytics 분석에 사용할 수 없습니다. 데이터
는 관련 필드가 해당 데이터 보기에 추가될 때까지 데이터 보기를 통해 사용자에게 사용할 수 없습니다.

소스를 사용하려면:

1. Experience Platform에서 데이터 세트를 저장할 샌드박스를 선택합니다. 사이트는 한 번만 할당할 수 있으므로 이 샌드박스가 원하는 샌드박스인지 확인하십시오.
1. **[!UICONTROL 소스]**, **[!UICONTROL 카탈로그]**, Adobe 애플리케이션으로 이동합니다. **[!UICONTROL Adobe Brand Visibility]** 카드에서 처음으로 **[!UICONTROL 설정]**&#x200B;을 선택합니다. 그 후 카드에 **[!UICONTROL 데이터 추가]**&#x200B;가 표시됩니다.

   ![소스에서 브랜드 가시성 선택](assets/aep-sources-select-bv.png)

1. **[!UICONTROL 데이터 추가]**&#x200B;를 선택합니다.

   ![브랜드 가시성 원본에 데이터 추가](assets/aep-sources-bv-add-data.png)

1. ➊ **[!UICONTROL 데이터 선택]** 단계:

   1. **[!UICONTROL 사이트 이름]** 테이블에서 사이트를 선택하십시오. 사이트가 데이터 흐름에 할당되면 해당 사이트나 다른 샌드박스에서 사이트를 다시 선택할 수 없습니다.

      ![브랜드 가시성 원본 구성의 1단계](assets/bv-source-step-1.png)

   1. **[!UICONTROL 다음]**&#x200B;을 선택합니다.

1. ➋ **[!UICONTROL 데이터 흐름 세부 정보]** 단계:

   1. **[!UICONTROL 데이터 흐름 이름]** 및 선택적 **[!UICONTROL 설명]**&#x200B;을 입력하십시오. 경고 **[!UICONTROL 소스 데이터 흐름 실행 시작]**, **[!UICONTROL 소스 데이터 흐름 실행 성공]** 및 **[!UICONTROL 소스 데이터 흐름 실행 실패]**&#x200B;에 가입할 수도 있습니다.

      Brand Visuity 소스 구성의 ![2단계](assets/bv-source-step-2.png)

   1. **[!UICONTROL 다음]**&#x200B;을 선택합니다.

1. ➌ **[!UICONTROL 검토]** 단계에서:

   1. 연결 및 데이터 세트 할당을 확인합니다.

      ![브랜드 가시성 원본 구성의 3단계](assets/bv-source-step-3.png)

   1. **[!UICONTROL 완료]**&#x200B;를 선택합니다.

데이터 세트가 자동으로 할당되며 필드 매핑이 필요하지 않습니다.

>[!IMPORTANT]
>
>사이트는 한 번만 할당할 수 있습니다. 다른 샌드박스에서 사이트를 사용하려면 사이트가 할당된 데이터 흐름을 삭제하십시오. 데이터 흐름을 삭제하면 이 소스의 데이터를 사용하는 모든 Customer Journey Analytics 연결 또는 데이터 보기에 영향을 줍니다.
>


## 확인

다음 절차를 사용하여 인바운드 통합을 확인합니다.

1. ABV 사이트 및 CDN 로그 준비 상태를 확인합니다.

   각 ABV 사이트의 경우:

   * CDN 로그 전달에서 다루는 정확한 사이트 또는 도메인을 확인합니다.
   * Experience Platform 내의 브랜드 가시성 소스에서 사이트를 선택할 수 있는지 확인합니다. 사이트는 Brand Visibility에서 구문 분석된 CDN 로그의 가용성에 따라 사용할 수 있습니다.
   * &quot;CDN 로그가 활성화되었습니다.&quot;라는 일반 문을 계속 진행하지 마십시오. 특정 ABV 사이트를 선택할 수 있을 때 계속 진행합니다.
   * 브랜드 가시성이 해당 사이트에 대한 로그를 받거나 감지하고 있는지 확인합니다.
   * Adobe에서 사이트의 브랜드 가시성 준비 확인 을 얻습니다.

1. Experience Platform에서 데이터 세트를 확인합니다.

   데이터 흐름을 만든 후:
   1. **[!UICONTROL Experience Platform]**&#x200B;에 로그인합니다.
   1. 데이터 흐름을 만든 샌드박스를 선택합니다.
   1. **[!UICONTROL 데이터 세트]**&#x200B;에서 브랜드 가시성 사이트의 데이터 세트를 찾습니다.
   1. 데이터 세트가 예상 브랜드 가시성 사이트와 연결되어 있는지 확인합니다.
   1. **[!UICONTROL 데이터 세트 ID]**&#x200B;를 기록하고 연결된 **[!UICONTROL 스키마]**&#x200B;를 기록하십시오.
   1. 허용되는 경우 데이터 세트 레코드 수, 최신 수집 정보 및 사용 가능한 샘플 데이터를 검토하십시오.
   1. 연결된 스키마를 열고 예상 XDM 구조를 확인합니다.
      * 클래스: **[!UICONTROL XDM 요약 지표]**
      * 필드 그룹: **[!UICONTROL CDN 요청 요약]**
      * 개체: **[!UICONTROL cdn]**
      * **[!UICONTROL botType]**, **[!UICONTROL cdnProvider]**, **[!UICONTROL url]**, **[!UICONTROL host]**, **[!UICONTROL status]**, **[!UICONTROL requests]** 및 **[!UICONTROL timeToFirstByte]**&#x200B;과 같은 예상 차원 및 지표입니다.

1. 연결에 데이터 세트 추가

   Customer Journey Analytics 관리자는 의도한 연결에 데이터 세트를 추가해야 합니다.

   1. Customer Journey Analytics에 로그인합니다.
   1. [새 연결을 만들거나 의도한 기존 연결을 편집합니다](/help/connections/create-connection.md). 연결이 데이터 세트를 만든 것과 동일한 Experience Platform 샌드박스를 사용하는지 확인합니다.
   1. 이름 또는 데이터 세트 ID로 데이터 세트를 검색합니다.
   1. 연결에 데이터 세트를 추가합니다.
   1. 고객의 Customer Journey Analytics 디자인에 따라 데이터 세트 설정을 구성합니다.
   1. 연결을 저장합니다.
   1. 데이터 세트가 포함되어 있으며 수집이 진행 중인지 확인하려면 연결 세부 정보를 검토하십시오.

1. 데이터 보기 구성 또는 업데이트

   데이터 세트가 연결의 일부가 된 후:
   1. Customer Journey Analytics에 로그인합니다.
   1. [새 데이터 보기를 만들거나 의도한 보고 사용 사례와 연결된 데이터 보기를 편집합니다](/help/data-views/create-dataview.md).
   1. 관리되는 브랜드 가시성 데이터 세트가 포함된 연결을 선택하십시오.
   1. 필요한 스키마 필드를 차원 또는 지표로 추가합니다.
   1. 다음과 같이 계획된 분석에 필요한 필드를 포함합니다.
      * **[!UICONTROL CDN 보트 유형]**
      * **[!UICONTROL CDN 공급자]**
      * **[!UICONTROL CDN URL]**
      * **[!UICONTROL CDN 호스트]**
      * **[!UICONTROL CDN HTTP 상태]**
      * **[!UICONTROL CDN 요청 개수]**
      * **[!UICONTROL 첫 번째 바이트까지의 CDN 평균 시간]**
   1. 데이터 보기를 저장합니다.
   1. Analysis Workspace 또는 고객이 선택한 보고 워크플로의 필드를 확인합니다.

1. 전체적인 결과의 유효성 검사

   최근 보고 기간을 사용하여 다음을 확인합니다.

   * 예상 브랜드 가시성 사이트가 표시됩니다.
   * 예상 CDN 공급자 및 호스트 값이 있습니다.
   * 봇 또는 자동화된 에이전트 트래픽이 표시됩니다.
   * URL 및 HTTP 상태 차원에는 예상 값이 포함되어 있습니다.
   * CDN 요청 카운트 및 성능 지표를 사용할 수 있습니다.
   * 데이터 세트는 의도한 연결에 포함됩니다.
   * 필수 필드는 의도한 데이터 보기에 표시됩니다.

데이터를 사용하는 데 필요한 정확한 시간은 수집 및 Customer Journey Analytics 처리 워크플로우에 따라 다릅니다.

## 문제 해결

문제가 발생하는 경우 다음 단계를 검토하십시오.

* 데이터 세트가 AEP에 표시되지 않습니다.

  다음을 확인합니다.

  * IMS 조직이 올바릅니다.
  * 선택한 Experience Platform 샌드박스가 올바릅니다.
  * CDN 로그 전달이 작동한 후 소스가 활성화되었습니다.
  * Adobe에서 제공한 데이터 세트 이름 또는 ID가 사용되었습니다.
  * 올바른 브랜드 가시성 사이트에 대해 데이터 세트가 생성되었습니다.

* 데이터 세트가 존재하지만 예상 데이터가 없습니다.

  다음을 확인합니다.
  * 정확한 브랜드 가시성 사이트에 대해 CDN 로그가 전달됩니다.
  * 브랜드 가시성이 사이트에 대한 로그를 받거나 감지하고 있습니다.
  * CDN 구성의 사이트 또는 도메인은 브랜드 가시성 사이트와 일치합니다.
  * CDN 로그 준비가 확인된 후 관리되는 커넥터가 활성화되었습니다.
  * 선택한 날짜 범위에는 로그 수집이 시작된 후 기간이 포함됩니다.


* 데이터 세트가 Experience Platform에 있지만 Customer Journey Analytics에서 사용할 수 없습니다.

  다음을 확인합니다.
  * Customer Journey Analytics 연결에서는 동일한 이름의 Experience Platform 샌드박스를 사용합니다.
  * 데이터 세트가 연결에 명시적으로 추가되었습니다.
  * Customer Journey Analytics 관리자에게 필요한 권한이 있습니다.
  * 데이터 세트가 추가된 후 연결이 저장되었습니다.

* 데이터 세트가 연결에 있지만 필드를 보고에 사용할 수 없습니다.

  다음을 확인합니다.
  * 데이터 보기에서 올바른 Customer Journey Analytics 연결이 선택됩니다.
  * 예상 스키마 필드가 데이터 보기 구성 요소로 추가되었습니다.
  * 의도한 **[!UICONTROL 차원]** 또는 **[!UICONTROL 지표]** 섹션에 필드가 배치되었습니다.
  * 구성 요소가 추가된 후 데이터 보기가 저장되었습니다.
  * 데이터 집합 스키마가 필요한 **[!UICONTROL CDN 요청 요약]** 필드 그룹 구조와 일치합니다.

* 사이트가 목록에 없습니다.

  다음을 확인합니다.

  * Brand Visibility에서 구문 분석된 CDN 로그의 가용성에 따라 사이트를 선택할 수 있습니다.
  * CDN 로그 전달이 설정되었으며 사이트에서 작동합니다.

* 사이트를 선택할 수 없습니다.

  사이트가 데이터 흐름에 할당되면 해당 사이트나 다른 샌드박스에서 다시 선택할 수 없습니다. 다른 샌드박스에서 사이트를 사용하려면 사이트가 할당된 데이터 흐름을 삭제하십시오. 그런 다음 사이트를 다시 선택할 수 있습니다. 데이터 흐름을 삭제하면 이 소스의 데이터를 사용하는 모든 Customer Journey Analytics 연결 또는 데이터 보기에 영향을 줍니다.

* 데이터 흐름에 실패 상태가 표시됩니다.

  **[!UICONTROL 모니터링]** 대시보드를 사용하십시오. **[!UICONTROL 원본]** 개요에서는 30일 동안 연속적으로 실패하는 원본 데이터 흐름이 자동으로 비활성화되어 있음을 알 수 있습니다.


## 완료 기준


다음 사항이 모두 확인되면 인바운드 통합이 고객 측 Customer Journey Analytics 구성을 위해 준비됩니다.

* CDN 로그는 요청된 각 ABV 사이트에 대해 브랜드 가시성으로 전달되고 수신됩니다.
* 각 브랜드 가시성 사이트는 Adobe Brand Visibility 소스에서 선택할 수 있습니다.
* 의도한 샌드박스에서 Adobe Brand Visibility 소스를 활성화했습니다.
* 사이트별 요약 데이터 세트가 해당 샌드박스에 표시됩니다.
* 데이터 세트와 해당 XDM 스키마를 확인했습니다.
* 의도한 CJA 연결에 데이터 세트를 추가했습니다.
* 관련 CJA 데이터 보기 구성 요소를 구성했습니다.

