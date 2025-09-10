---
title: 결합 개요
description: 결합 개요
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 9774e0e3af024823a03dbcd8d6766877f55e95d8
workflow-type: ht
source-wordcount: '792'
ht-degree: 100%

---

# 결합 개요

>[!NOTE]
>
>이 섹션에서 설명하는 기능을 사용하려면 **Select** 패키지 이상[필드 기반 결합](fbs.md)) 또는 **Prime** 패키지 이상([그래프 기반 결합](gbs.md))이 있어야 합니다. 보유 중인 Customer Journey Analytics 패키지가 무엇인지 확실하지 않은 경우에는 귀사의 관리자에게 문의하십시오.

ID 결합(또는 간단히 결합)은 크로스 채널 분석에 대한 이벤트 데이터 세트의 적합성을 높이는 강력한 기능입니다. 크로스 채널 분석은 Customer Journey Analytics가 처리할 수 있는 주요 사용 사례로, 공통 식별자(개인 ID)를 기반으로 다양한 채널의 여러 데이터 세트에 대한 보고서를 원활하게 결합하고 실행할 수 있습니다.

유사한 개인 ID를 사용하여 데이터 세트를 결합하면 속성이 디바이스 및 채널 간에 전달됩니다. 예를 들어 사용자가 먼저 데스크탑 컴퓨터의 광고를 통해 사이트를 방문합니다. 해당 사용자가 주문 시 문제가 발생하면 고객 서비스 팀에 문의하여 문제를 해결할 수 있습니다. 크로스 채널 분석을 사용하면 콜센터 이벤트를 원래 클릭한 광고에 연결할 수 있습니다.

안타깝게도 Customer Journey Analytics에서 연결에 포함된 모든 이벤트 기반 데이터 세트에 이러한 속성을 지원할 수 있는 데이터가 충분히 채워져 있는 것은 아닙니다. 특히 웹 기반 또는 모바일 기반 경험 데이터 세트에는 모든 이벤트에 대한 실제 사용자 ID 정보가 없는 경우가 많습니다.

결합은 하나의 데이터 세트 행 내에서 ID를 재입력하여, 각 이벤트에서 개인 ID(결합된 ID)를 사용할 수 있도록 합니다. 결합은 인증된 세션과 비인증된 세션의 사용자 데이터를 모두 검토하여 결합된 ID로 사용할 수 있는 공통 임시 ID(개인 ID) 값을 결정합니다. 이렇게 재입력하면 디바이스나 쿠키 수준이 아니라 개인 수준에서 결합된 단일 ID에 대한 개별 레코드 문제를 해결하고 분석할 수 있습니다.

Customer Journey Analytics은 [필드 기반 결합](fbs.md)과 [그래프 기반 결합](gbs.md), 두 가지 유형의 결합을 지원합니다.

## 사전 요구 사항

>[!IMPORTANT]
>
>모든 전제 조건을 충족하지 못하면 크로스 채널 분석을 제대로 수행하지 못할 수 있습니다.

결합을 사용하기 전에 조직에서 다음 사항을 준비했는지 확인하십시오.

- 결합에는 인증된 사용자 데이터와 인증되지 않은 사용자 데이터를 병합하는 작업이 포함됩니다. 이벤트 데이터 세트에서 결합을 활성화하기 전에 필요한 최종 사용자 권한을 획득하는 등 해당 법률 및 규정을 준수하도록 하십시오. 자세한 내용은 [UI에서 ID 필드 정의](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/ui/fields/identity)를 참조하십시오.

- 원하는 데이터를 Adobe Experience Platform으로 가져옵니다.

   - Adobe Analytics 데이터는 [Customer Journey Analytics에서 Adobe Analytics 보고서 세트 데이터 활용](/help/getting-started/aa-vs-cja/aa-data-in-cja.md)을 참조하십시오.
   - 다른 유형의 데이터는 Adobe Experience Platform 문서에서 [스키마 만들기](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/tutorials/create-schema-ui) 및 [데이터 수집](https://experienceleague.adobe.com/ko/docs/experience-platform/ingestion/home)을 참조하십시오.

Customer Journey Analytics 연결을 정의하는 과정에서 하나 이상의 결합된 데이터 세트를 콜센터 데이터와 같은 다른 데이터 세트와 결합하면 크로스 채널 분석의 이점을 얻을 수 있습니다. 이 연결 구성은 다른 데이터 세트에 이미 결합된 ID와 유사하게 모든 행에 개인 ID를 포함하고 있다고 가정합니다.


## 제한 사항

>[!IMPORTANT]
>
>
>- 소스 이벤트 데이터 세트 스키마에 변경한 내용을 새로운 결합된 데이터 세트 스키마에도 적용합니다.
>
>- 소스 데이터 세트를 제거하면 결합된 데이터 세트가 처리를 중지하고 시스템에서 제거됩니다.
>
>- 데이터 사용 레이블은 결합된 데이터 세트 스키마에 자동으로 전파되지 않습니다. 소스 데이터 세트 스키마에 데이터 사용 레이블을 적용하는 경우, 이러한 데이터 사용 레이블을 결합된 데이터 세트 스키마에 수동으로 적용해야 합니다. 자세한 내용은 [Experience Platform에서 데이터 사용량 레이블 관리](https://experienceleague.adobe.com/ko/docs/experience-platform/data-governance/labels/overview)를 참조하십시오.

결합은 획기적이고 강력한 기능이지만 사용 방법에 대한 제한 사항이 있습니다.

- 이벤트 데이터 세트만 지원됩니다. 조회 데이터 세트와 같은 다른 데이터 세트는 지원되지 않습니다.
- 결합은 결합에 사용되는 필드를 어떤 방식으로도 변형시키지 않습니다. 결합은 데이터 레이크 내의 분해 데이터 세트에 존재하는 것처럼 지정된 필드의 값을 사용합니다.
- 결합 프로세스는 대소문자를 구분합니다. 예를 들어 때때로 “Bob”이라는 단어가 필드에 나타나고, 때로는 “BOB”이라는 단어가 나타난다면 이 ID는 두 명의 개별적인 사람으로 취급될 것입니다.

다음과 같은 결합을 혼동하지 않도록 주의하십시오.

- 두 개 이상의 데이터 세트 병합. 결합은 하나의 데이터 세트에만 적용됩니다. 데이터 세트 병합은 Customer Journey Analytics 연결을 설정하고 연결된 선택된 데이터 세트에서 동일한 사용자 ID를 선택하면 발생합니다.

- 두 데이터 세트의 조인. Customer Journey Analytics에서 조인은 종종 Analysis Workspace에서 조회나 분류에 사용됩니다. 결합은 조인 기능을 사용하지만 그 과정 자체는 조인 이상의 작업을 포함합니다.


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
>>[그래프 기반 결합](gbs.md)
>>[결합 사용](use-stitching.md)
>>[스티칭 검증](validate.md)
>>[스티칭 FAQ](faq.md)

