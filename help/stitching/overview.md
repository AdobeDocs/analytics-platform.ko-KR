---
title: 결합 개요
description: 결합 개요.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
source-git-commit: 058b8d997c7cb2e4e73d3c2026a4b9bf29db26bd
workflow-type: tm+mt
source-wordcount: '1468'
ht-degree: 21%

---

# 결합 개요

ID 결합 (또는 간단히 결합)은 크로스 채널 분석에 대한 이벤트 데이터 세트의 적합성을 높이는 강력한 기능입니다. 크로스 채널 분석은 Customer Journey Analytics이 처리할 수 있는 주요 사용 사례이며, 이를 통해 공통 식별자(개인 ID)를 기반으로 다른 채널의 여러 데이터 세트에 보고서를 원활하게 결합하고 실행할 수 있습니다.

유사한 개인 ID를 사용하여 데이터 세트를 결합하면 속성이 디바이스 및 채널 간에 전달됩니다. 예를 들어 사용자가 먼저 데스크탑 컴퓨터의 광고를 통해 사이트를 방문합니다. 해당 사용자가 주문 시 문제가 발생하면 고객 서비스 팀에 문의하여 문제를 해결할 수 있습니다. 크로스 채널 분석을 사용하면 콜 센터 이벤트를 원래 클릭한 광고에 연결할 수 있습니다.

안타깝게도, Customer Journey Analytics에서 연결에 포함된 모든 이벤트 기반 데이터 세트에 이 속성을 즉시 지원할 수 있는 데이터가 충분히 채워지지는 않습니다. 특히 웹 기반 또는 모바일 기반 경험 데이터 세트에는 모든 이벤트에서 사용할 수 있는 실제 개인 ID 정보가 없는 경우가 많습니다.

결합을 사용하면 한 데이터 세트의 행 내에서 ID를 재입력할 수 있으므로 각 이벤트에서 개인 ID(결합된 ID)를 사용할 수 있는지 확인할 수 있습니다. 결합은 인증된 세션과 인증되지 않은 세션의 사용자 데이터를 확인하여 결합된 ID로 사용할 수 있는 일반적인 임시 ID 값을 결정합니다. 이러한 재입력을 통해 디바이스나 쿠키 수준이 아닌 개인 수준에서 분석을 위해 서로 다른 레코드를 단일 결합 ID로 확인할 수 있습니다.

Customer Journey Analytics 연결을 정의하는 과정에서 결합된 데이터 세트 중 하나 이상을 콜 센터 데이터와 같은 다른 데이터 세트와 결합하는 경우 크로스 채널 분석의 이점을 누릴 수 있습니다. 이는 다른 데이터 세트에도 결합된 ID와 유사한 개인 ID가 모든 행에 이미 포함되어 있다고 가정합니다.


## 사전 요구 사항

{{select-package}}

>[!IMPORTANT]
>
>모든 전제 조건을 충족하지 못하면 크로스채널 분석을 제대로 수행할 수 없습니다.

결합을 사용하기 전에 조직에서 다음 사항을 준비했는지 확인하십시오.

* 원하는 데이터를 Adobe Experience Platform으로 가져옵니다:

   * Adobe Analytics 데이터의 경우 [Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 활용](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   * 다른 유형의 데이터는 Adobe Experience Platform 문서에서 [스키마 만들기](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ko-KR) 및 [데이터 수집](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=ko-KR)을 참조하십시오.

* 결합을 적용할 Adobe Experience Platform의 이벤트 데이터 세트에는 방문자를 식별하는 데 도움이 되는 두 개의 열이 있어야 합니다.

   * 모든 행에 표시되는 식별자인 **영구 ID**. 예를 들어 Adobe Analytics AppMeasurement 라이브러리에서 생성된 방문자 ID 또는 Adobe Experience Cloud ID 서비스에서 생성된 ECID입니다.
   * 일부 행에만 있는 식별자인 **일시적 ID**. 예를 들어 방문자가 인증을 받은 후 해시된 사용자 이름 또는 이메일 주소입니다. 원하는 거의 모든 식별자를 사용할 수 있습니다. 결합하면 실제 개인 ID 정보를 보유하기 위해 이 필드가 고려됩니다. 최상의 결합 결과를 위해 임시 ID는 각 영구 ID에 대해 데이터 세트의 이벤트 내에서 적어도 한 번 전송되어야 합니다. 이 데이터 세트를 Customer Journey Analytics 연결 내에 포함하려는 경우 다른 데이터 세트에도 유사한 공통 식별자가 있는 것이 좋습니다.

  두 열(영구 ID 및 임시 ID)은 결합하려는 데이터 세트의 기본 설정된 스키마에 ID 네임스페이스가 있는 ID 필드로 정의해야 합니다. Real-time Customer Data Platform에서 ID 결합을 사용할 때 [identityMap 필드 그룹](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=en#identity), 이 섹션에서 설명한 재생 결합은 identityMap 필드 그룹을 지원하지 않으므로 id 네임스페이스가 있는 id 필드를 추가해야 합니다. identityMap 필드 그룹을 기반으로 Real-time Customer Data Platform에서 ID 결합을 사용하는 동안 ID 필드를 추가할 때 다음을 수행하십시오 *아님* 추가 id 필드를 기본 id로 설정합니다. 이 경우 Real-time Customer Data Platform의 identityMap 필드 그룹 기반 id 결합이 방해됩니다.

* 결합에는 인증된 사용자 데이터와 인증되지 않은 사용자 데이터의 병합이 포함됩니다. 이벤트 데이터 세트에 대한 결합을 활성화하기 전에 필요한 최종 사용자 권한을 얻는 등 관련 법률 및 규정을 준수하는지 확인하십시오. 다음을 참조하십시오 [UI에서 ID 필드 정의](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html?lang=en#) 추가 정보.


## 결합 사용

조직이 모든 전제 조건을 충족하고 다음을 이해하면 [제한 사항](#limitations), 다음 단계에 따라 Customer Journey Analytics에서 결합을 사용할 수 있습니다.

### 지원 요청

1. 다음과 관련된 질문이 있는 경우 Adobe 고객 지원 센터에 문의하십시오.

   * 결합 활성화 요청.
   * 다시 입력할 데이터 세트에 대한 데이터 세트 ID.
   * 원하는 데이터 세트에 대한 영구 ID의 열 이름 (모든 행에 표시되는 식별자).
   * 원하는 데이터 세트에 대한 임시 ID의 열 이름(연결 컨텍스트에서 데이터 세트 간 링크 역할도 하는 개인 식별자).
   * [재생](explained.md) 빈도 및 전환 길이에 대한 사용자 환경 설정입니다. 옵션으로 7일 전환 확인 기간이 있는 일주일에 한 번 재생 또는 1일 전환 확인 기간이 있는 매일 재생이 있습니다.
   * 샌드박스 이름


2. Adobe 고객 지원 팀은 Adobe 엔지니어링과 함께 작동하여 요청을 접수할 때 결합을 활성화합니다. 활성화되면 새로운 결합된 ID 열이 포함된 재입력된 새 데이터 세트가 Adobe Experience Platform에 나타납니다. Adobe 고객 지원 센터에서 새 데이터 세트의 ID를 제공할 수 있습니다.

3. 처음 켜면 Adobe에서 60일 이전의 결합된 데이터 채우기를 제공합니다.

4. 크로스 채널 분석에서 결합된 새 데이터 세트를 사용하려면 를 로 추가해야 합니다 [연결](../connections/overview.md) 다른 필요한 데이터 세트와 함께 Customer Journey Analytics. 각 데이터 세트에 올바른 개인 ID를 선택합니다.

5. 연결을 기반으로 [데이터 보기를 만듭니다](/help/data-views/create-dataview.md).

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

데이터 보기가 설정되면 채널 및 디바이스 간에 Customer Journey Analytics 보고 분석을 실행할 수 있습니다.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->


## 제한 사항

>[!IMPORTANT]
>
>* 전역 이벤트 데이터 세트 스키마에 대한 변경 사항을 결합된 새 데이터 세트 스키마에도 적용합니다. 그렇지 않으면 결합된 데이터 세트가 손상됩니다.
>
>* 소스 데이터 세트를 제거하면 연결된 데이터 세트가 처리를 중지하고 시스템에서 제거됩니다.
>
>* 데이터 사용 레이블은 결합된 데이터 세트 스키마에 자동으로 전파되지 않습니다. 소스 데이터 세트 스키마에 데이터 사용 레이블이 적용된 경우 이러한 데이터 사용 레이블을 결합된 데이터 세트 스키마에 수동으로 적용해야 합니다. 다음을 참조하십시오 [Experience Platform에서 데이터 사용 레이블 관리](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=ko-KR) 추가 정보.

결합은 획기적이고 강력한 기능이지만 사용 방법에 대한 제한이 있습니다.

* 현재 재입력 기능은 한 단계로 제한됩니다(영구 ID를 임시 ID로). 여러 단계의 키 재입력(예: 영구 ID를 임시 ID로, 그 다음 다른 임시 ID로 변경)은 지원되지 않습니다.
* 이벤트 데이터 세트만 지원됩니다. 조회 데이터 세트와 같은 다른 데이터 세트는 지원되지 않습니다.
* 조직에서 사용한 사용자 정의 ID 맵은 지원되지 않습니다.
* 결합은 어떤 방식으로도 결합에 사용된 필드를 변형하지 않습니다. 결합은 데이터 레이크 내의 결합되지 않은 데이터 세트에 존재하는 것처럼 지정된 필드의 값을 사용합니다. 결합 프로세스는 대소문자를 구분합니다. 예를 들어 때때로 &quot;Bob&quot;이라는 단어가 필드에 나타나고, 때로는 &quot;BOB&quot;이라는 단어가 나타나는 경우 이러한 ID는 두 명의 개별적인 사람으로 처리됩니다.
* 결합은 대소문자를 구분합니다. Analytics 소스 커넥터를 통해 생성된 데이터 세트의 경우 Adobe은 임시 ID 필드에 적용되는 VISTA 규칙 또는 처리 규칙을 검토할 것을 권장합니다. 이 검토를 통해 이러한 규칙 중 동일한 ID의 새로운 형식을 도입하는 규칙이 없는지 확인합니다. 예를 들어 VISTA 또는 처리 규칙이 이벤트의 일부에서만 임시 ID 필드에 소문자를 도입하지 않는지 확인해 보아야 합니다.
* 결합은 필드를 결합하거나 연결하지 않습니다.
* 임시 ID 필드는 단일 유형의 ID(단일 네임스페이스의 ID)를 포함해야 합니다. 예를 들어 임시 ID 필드는 로그인 ID와 이메일 ID의 조합을 포함해서는 안 됩니다.
* 동일한 영구 ID에 대해 동일한 타임스탬프를 가진 여러 이벤트가 발생하지만 임시 ID 필드의 값이 다른 경우, 결합은 알파벳 순서를 기반으로 ID를 선택합니다. 따라서 영구 ID A에 동일한 타임스탬프를 가진 두 개의 이벤트가 있고 이벤트 중 하나가 &quot;Bob&quot;을 지정하고 다른 하나는 &quot;Ann&quot;을 지정하는 경우 결합은 &quot;Ann&quot;을 선택합니다.
* 디바이스를 여러 사용자가 공유하고 사용자 간 총 전환 수가 50,000개를 초과하는 경우 Customer Journey Analytics은 해당 디바이스에 대한 데이터 결합을 중지합니다.
* 임시 ID에 자리 표시자 값이 포함된 시나리오에 주의하십시오(예: &#39;정의되지 않음&#39;). 다음을 참조하십시오 [FAQ](faq.md) 추가 정보.

결합을 다음과 혼동하지 마십시오.

* 두 개 이상의 데이터 세트 병합. 결합은 하나의 데이터 세트에만 적용됩니다. 데이터 세트 병합은 Customer Journey Analytics 연결을 설정하고 연결에서 선택한 데이터 세트에서 동일한 개인 ID를 선택한 결과로서 발생합니다.

* 두 데이터 세트의 결합. Customer Journey Analytics에서 조인은 종종 Analysis Workspace에서 조회 또는 분류에 사용됩니다. 결합은 결합 기능을 사용하지만 프로세스 자체에는 조인보다 더 많은 것이 포함됩니다.
