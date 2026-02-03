---
title: 스티칭 개요
description: ID 결합의 개념, 이점, 사전 요구 사항 및 제한 사항에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 9bebfaf7e10762bc7382d8b0d55148ee23698dd9
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 65%

---

# 결합 개요

>[!NOTE]
>
>이 섹션에 설명된 기능을 사용하려면 Customer Journey Analytics **Select** 패키지 이상([필드 기반 결합](fbs.md)의 경우) 또는 Customer Journey Analytics **Prime** 패키지 이상([그래프 기반 결합](gbs.md)의 경우)이 있어야 합니다. 보유 중인 Customer Journey Analytics 패키지가 무엇인지 확실하지 않은 경우에는 귀사의 관리자에게 문의하십시오.

ID 결합(또는 간단히 결합)은 크로스 채널 분석에 대한 이벤트 데이터 세트의 적합성을 높이는 강력한 기능입니다. 크로스 채널 분석은 Customer Journey Analytics의 주요 사용 사례입니다. 이 기능을 통해 다양한 채널의 여러 데이터 세트 대한 보고서를 공통 식별자(개인 ID)를 기준으로 원활하게 결합하고 실행할 수 있습니다.

유사한 개인 ID를 사용하여 데이터 세트를 결합하면 속성이 디바이스 및 채널 간에 전달됩니다. 예를 들어 사용자가 데스크탑 컴퓨터의 광고를 통해 사이트를 방문합니다. 사용자가 제품을 구매하지만 주문에 문제가 발생합니다. 그런 다음 사용자가 고객 서비스 팀에 문의하여 문제 해결을 요청합니다. 크로스 채널 분석을 사용하면 콜센터 이벤트를 사용자가 원래 클릭한 광고에 연결할 수 있습니다.

안타깝게도 Customer Journey Analytics에서 연결에 포함된 모든 이벤트 기반 데이터 세트에 이러한 속성을 지원할 수 있는 데이터가 충분히 채워져 있는 것은 아닙니다. 특히 웹 기반 또는 모바일 기반 경험 데이터 세트에는 모든 이벤트에 대한 실제 개인 ID 정보가 없는 경우가 많습니다.

결합은 각 이벤트에서 개인 ID(결합된 ID)를 사용할 수 있도록 한 데이터 세트의 행 내에서 ID를 다시 키 대조합니다. 결합은 인증된 세션과 비인증된 세션의 사용자 데이터를 모두 검토하여 결합된 ID로 사용할 수 있는 공통 개인 ID 값을 결정합니다. 이렇게 재입력하면 디바이스나 쿠키 수준이 아닌 사용자 수준에서 서로 다른 레코드를 단일 결합 ID로 분석하여 분석할 수 있습니다.

Customer Journey Analytics은 [필드 기반 결합](fbs.md)과 [그래프 기반 결합](gbs.md), 두 가지 유형의 결합을 지원합니다.

## 사전 요구 사항

>[!IMPORTANT]
>
>모든 전제 조건을 충족하지 못하면 크로스 채널 분석을 제대로 수행하지 못할 수 있습니다.

결합을 사용하기 전에 조직에서 다음 사항을 준비했는지 확인하십시오.

- 결합에는 인증된 사용자 데이터와 인증되지 않은 사용자 데이터를 병합하는 작업이 포함됩니다. 이벤트 데이터 세트에 대한 결합을 활성화하기 전에 필요한 최종 사용자 권한을 얻는 등 관련 법률 및 규정을 준수하는지 확인하십시오.

- 원하는 데이터를 Adobe Experience Platform으로 가져옵니다.

   - Adobe Analytics 데이터는 [Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 활용](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)을 참조하십시오.
   - 다른 유형의 데이터는 Adobe Experience Platform 문서에서 [스키마 만들기](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/tutorials/create-schema-ui) 및 [데이터 수집](https://experienceleague.adobe.com/ko/docs/experience-platform/ingestion/home)을 참조하십시오.

Customer Journey Analytics 연결을 정의하는 과정에서 하나 이상의 결합된 데이터 세트를 콜센터 데이터와 같은 다른 데이터 세트와 결합하면 크로스 채널 분석의 이점을 얻을 수 있습니다. 이 연결 구성은 다른 데이터 세트에 이미 결합된 ID와 유사하게 모든 행에 개인 ID를 포함하고 있다고 가정합니다.

조직이 일반 [필수 구성 요소](overview.md#prerequisites)를 충족하고 일반 [제한 사항](overview.md#limitations)을(를) 이해하며 결합 방법별([필드 기반](fbs.md) 및 [그래프 기반](gbs.md)) 필수 구성 요소 및 제한 사항도 이해하면 Customer Journey Analytics에서 결합을 요청하고 사용할 수 있습니다.


## 제한 사항

결합은 획기적이고 강력한 기능이지만 사용 방법에 대한 제한 사항이 있습니다.

- 이벤트 데이터 세트만 지원됩니다. 조회 데이터 세트와 같은 다른 데이터 세트는 지원되지 않습니다.
- 결합은 결합에 사용되는 필드를 어떤 방식으로도 변형시키지 않습니다. 결합은 데이터 레이크 내의 분해 데이터 세트에 존재하는 것처럼 지정된 필드의 값을 사용합니다.
- 결합 프로세스는 대소문자를 구분합니다. 예를 들어 ID 값 `Bob`과(와) `BOB`은(는) 두 명의 개별 사용자로 취급됩니다.

다음과 같은 결합을 혼동하지 않도록 주의하십시오.

- 두 개 이상의 데이터 세트 병합. 결합은 하나의 데이터 세트에만 적용됩니다. 데이터 세트 병합은 Customer Journey Analytics 연결을 설정하고 연결된 선택된 데이터 세트에서 동일한 개인 ID를 선택하면 발생합니다.

- 두 데이터 세트의 조인. Customer Journey Analytics에서 조인은 종종 Analysis Workspace에서 조회나 분류에 사용됩니다. 결합은 조인 기능을 사용하지만 그 과정 자체는 조인 이상의 작업을 포함합니다.


## 옵션

권한이 부여된 Customer Journey Analytics 패키지는 사용 가능한 결합 방법, 초기 채우기 기간, 전환 확인 기간, 재생 빈도 및 결합에 허용된 최대 데이터 세트 수에 대한 옵션을 결정합니다. 자세한 내용은 [Customer Journey Analytics 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/customer-journey-analytics.html)을 참조하세요. 결합을 활성화하기 전에 사용 가능한 옵션을 결정하십시오.

| | Customer Journey Analytics<br/>선택 | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| 사용 가능한 결합 방법 | 필드 기반 결합 | 필드 기반 결합<br/>그래프 기반 결합 | 필드 기반 결합<br>그래프 기반 결합</li> |
| 1회 스티칭 채우기 기간 | 13개월 | 13개월 | 25개월 |
| 전환 확인 기간 및 재생 빈도 | 1일, 매일<br/>최대 7일, 매주 | 1일, 매일<br/>최대 14일, 매주 | 1일, 매일<br/>최대 30일, 매주 |
| 결합에 허용되는 최대 데이터 세트 수 | 5 | 15 | 50 |

## 결합 활성화

다음 두 가지 방법으로 결합을 활성화할 수 있습니다.

- [결합을 사용하도록 요청](/help/stitching/use-stitching.md)(더 이상 사용되지 않음). 승인되면 결합을 요청한 데이터 세트에 대해 중복 데이터 세트가 만들어집니다. 이 중복 데이터 세트에는 결합된 식별자가 있는 추가 열이 포함되어 있습니다. Customer Journey Analytics에서 결합된 데이터를 사용하려면 결합된 데이터 세트가 포함된 새 연결을 만들거나 기존 연결을 편집해야 합니다.
- [연결 인터페이스에서 연결을 활성화합니다](/help/stitching/use-stitching-ui.md). 연결 인터페이스에서 데이터 세트에 대한 결합을 구성할 때 Customer Journey Analytics의 해당 데이터 세트에서 데이터를 수집하는 동안 결합이 즉시 발생합니다.


## Journey Optimizer 데이터 세트

결합은 다음과 같이 자동으로 생성된 Journey Optimizer 데이터 세트를 지원합니다.

- AJO 여정 단계 이벤트
- AJO 인바운드 활동 이벤트 데이터 세트
- AJO 표면 데이터 세트
- AJO 메시지 피드백 이벤트 데이터 세트* AJO 푸시 추적 경험 이벤트 데이터 세트
- AJO 이메일 추적 경험 이벤트 데이터 세트
- AJO BCC 피드백 이벤트 데이터 세트
- AJO 라이브 활동 피드백 이벤트 데이터 세트
- AJO ExD 결정 이벤트 데이터 세트

>[!MORELIKETHIS]
>
>[필드 기반 결합](fbs.md)
>[그래프 기반 결합](gbs.md)
>[결합 사용](use-stitching.md)
>[결합 검증](validate.md)
>[결합 FAQ](faq.md)

