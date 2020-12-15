---
title: Customer Journey Analytics FAQ
description: Customer Journey Analytics - 자주 묻는 질문
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 43%

---


# FAQ

## 전제 조건

| 질문 | 답변 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics]에 대해 [!UICONTROL 개인 장치 그래프] 또는 [!UICONTROL 장치 코업]이 필요합니까? | 아니요, [!UICONTROL Customer Journey Analytics]에는 [!UICONTROL 개인 장치 그래프] 또는 [!UICONTROL 장치 Coop]이 필요하지 않습니다. 실제로 아직 지원되지 않습니다. |
| [!UICONTROL Customer Journey Analytics]에 대해 [!UICONTROL Experience Cloud ID](ECID)가 필요합니까? | 아니요. [!UICONTROL Customer Journey Analytics]는 데이터 세트에서 선택한 ID가 ECID든 다른 ID이든 모두 지원합니다. |
| [!UICONTROL Customer Journey Analytics] 이전에 데이터를 ETL(추출, 변환, 로드)해야 하는 경우 어떻게 합니까? | 현재 AEP에 데이터를 추가하기 전에 데이터를 변환해야 하는 경우 ETL 파트너(Unifi 또는 Informatica)와 함께 작업해야 합니다. 데이터를 이미 인제스트한 후 ETL이 필요한 경우 [!UICONTROL Adobe Experience Platform 쿼리 서비스]는 일부 제한된 옵션을 제공합니다. |

## 데이터 연결

| 질문 | 답변 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics]를 장치 또는 데이터 세트 간에 &quot;결합&quot;할 수 있습니까? | 예. [!UICONTROL Customer Journey Analytics]는 ID 하나로 로그인하는 &quot;BYOI&quot; 분석 시스템입니다. 2020년 11월에 스티칭 솔루션을 출시했습니다. 추가 정보. |
| 익명 동작에서 인증 동작으로 결합하는 작업이 지원됩니까? | 아니요. 아직 지원되지 않습니다. |

## [!UICONTROL Customer Journey Analytics]로 데이터 가져오기

| 질문 | 답변 |
| --- | --- |
| 하나의 [!UICONTROL Customer Journey Analytics] 연결에 다른 [!UICONTROL Adobe Experience Platform] 샌드박스의 데이터를 결합할 수 있습니까? | 아니요. 샌드박스에서 데이터에 액세스할 수 없습니다. 동일한 샌드박스 내에 있는 데이터 세트만 결합할 수 있습니다. [추가 정보...](https://docs.adobe.com/content/help/ko-KR/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| [!UICONTROL Adobe Experience Platform]의 [!UICONTROL Customer Journey Analytics]에 대한 예상 지연은 무엇입니까? | <ul><li>일반 로드 중: 60분 미만입니다. <br>**참고:** 파이프라인을 통해 비정상적으로 많은 데이터 흐름이 있는 경우 최대 24시간이 소요될 수 있습니다.</li><li>데이터 채우기(크기에 상관없이 최대 13개월 데이터): &lt; 4주</li></ul> |
| [!UICONTROL Customer Journey Analytics]에서 온라인 데이터를 오프라인 데이터로 어떻게 연결합니까? | [!UICONTROL Customer Journey Analytics]는 ID 하나로 로그인하는 &quot;BYOI&quot; 분석 시스템입니다. 개인 ID가 데이터 세트 간에 일치하는 경우 [!UICONTROL Customer Journey Analytics]는 전체 데이터 세트에서 세그먼트, 기여도, 흐름, 폴아웃 등을 연결할 수 있습니다. |
| 오프라인 데이터를 [!UICONTROL Customer Journey Analytics]으로 가져오려면 어떻게 합니까? | [!UICONTROL Customer Journey Analytics]에서 사용하려면 먼저 데이터를 Experience Platform에 가져와야 합니다. 필요한 경우 Experience Platform의 데이터 온보딩팀에서 추천이나 컨설팅 서비스를 제공할 수 있습니다. |
| [!UICONTROL Adobe Analytics] 데이터를 [!UICONTROL Customer Journey Analytics]으로 가져오려면 어떻게 합니까? | [!UICONTROL Adobe ] 분석 데이터는  [Adobe Analytics 소스 커넥터를 통해 Experience Platform에 연결할 수 있습니다](https://docs.adobe.com/content/help/ko-KR/experience-platform/sources/connectors/adobe-applications/analytics.html). 대부분의 [!UICONTROL Adobe Analytics] 필드는 XDM 형식으로 가져오지만 다른 필드는 아직 사용할 수 없습니다(예: [!UICONTROL 마케팅 채널] 차원). |
| 데이터 세트 요소를 데이터 보기로 취합하는 데 얼마나 걸립니까? | 시작하는 데 몇 시간이 소요되고 지난 13개월간의 데이터를 채우는 데는 며칠이 소요됩니다. |
| 데이터 간의 연결을 설정하려면 PII 데이터를 가져와야 합니까? | 아니요. PII가 아닌 고객 ID의 해시를 포함하여 모든 ID를 사용할 수 있습니다. |

## 기존 [!UICONTROL Adobe Analytics] 구성 요소

| 질문 | 답변 |
| --- | --- |
| 기존 [!UICONTROL Adobe Analytics] 제품의 경우 어떤 의미입니까? | [!UICONTROL Customer Journey Analytics는 차세대 분석 제품입니다. ] 현재 제품에서 [!UICONTROL Customer Journey Analytics]으로 진화하는 데 몇 년이 걸리고 많은 조정이 필요합니다. 자세한 내용은 [Customer Journey Analytics 기능 지원](/help/getting-started/cja-aa.md)을 검토하세요. |
| [!UICONTROL Customer Journey Analytics]에서 AEP 또는 다른 솔루션으로 세그먼트를 공유할 수 있습니까? | 아직 공유할 수 없습니다. 이렇게 긴 지연이 없는 미래 동안 [!UICONTROL Customer Journey Analytics]에서 AEP로 세그먼트를 공유하는 새롭고 혁신적인 방법을 모색하고 있습니다. 즉, 잠재적인 해결 방법으로 Query Services의 결과를 통합 프로필에 공유할 수 있습니다. |
| 이전 eVar 설정은 어떻게 됩니까? | 기존 Adobe Analytics 센스의 eVar, prop 및 이벤트는 더 이상 [!UICONTROL Customer Journey Analytics]에 없습니다. 무제한 스키마 요소(차원, 지표, 목록 필드)가 있습니다. 따라서 이제 데이터 수집 프로세스 동안 적용했던 모든 속성 설정이 쿼리 시간에 적용됩니다. |
| 모든 세션 및 변수 지속성 설정은 현재 어디에 있습니까? | [!UICONTROL Customer Journey Analytics의 경우 이러한 모든 설정은 보고서 시간에 적용되며 데이터 보기에 있습니다. ] 이제 이러한 설정을 변경하면 소급 적용되며, 여러 데이터 보기를 사용하여 여러 버전을 보유할 수 있습니다. |
| 기존 세그먼트/계산된 지표는 어떻게 됩니까? | [!UICONTROL Customer Journey Analytics는 더 이상 eVar, prop, 이벤트를 사용하지 않으며 대신 AEP 스키마를 사용합니다. ] 즉, 기존 세그먼트 또는 계산 지표가 [!UICONTROL Customer Journey Analytics]과 호환되지 않음을 의미합니다. |
| [!UICONTROL Customer Journey Analytics]은 `Uniques Exceeded` 제한을 어떻게 처리합니까? | [!UICONTROL Customer Journey Analytics에는 고유 값 제한이 없으므로 걱정할 필요가 없습니다.] |
| 기존 [!DNL Data Workbench] 고객은 바로 Customer Journey Analytics로 이동할 수 있습니까? | 상황에 따라 다릅니다. UCP(Unified Customer Process)를 많이 사용하는 경우 결합을 구현하기 전까지 기다리십시오. 이미 높은 고객 인증률을 보유하고 있거나, 모든 데이터를 한 곳에서 확인하고 싶거나, eVar를 제거하려면 Customer Journey Analytics가 적합할 수 있습니다. |

## 데이터 구성 요소 삭제에 대한 의미

삭제에 관한 한, 우리는 6가지 구성 요소에 대해 염려하고 있다.샌드박스, 스키마, 데이터 세트, 연결, 데이터 보기 및 작업 공간 프로젝트 다음은 이러한 구성 요소 중 하나를 삭제하는 것과 관련된 몇 가지 가능한 시나리오입니다.

| 만약.. | 이런 일이... |
| --- | --- |
| [!UICONTROL Adobe Experience Platform]에서 샌드박스를 삭제하시겠습니까? | 샌드박스를 삭제하면 해당 샌드박스의 데이터 세트에 대한 [!UICONTROL Customer Journey Analytics] 연결에 대한 데이터 흐름이 중지됩니다. 현재 해당 샌드박스에 연결된 CJA의 연결은 자동으로 삭제되지 않습니다. |
| [!UICONTROL Adobe Experience Platform]에서 스키마를 삭제하지만 이 스키마와 연결된 데이터 집합/s는 삭제하시겠습니까? | [!UICONTROL Adobe Experience ] Platform에서는 연관된 데이터 세트가 하나 이상 있는 스키마를 삭제할 수 없습니다. 그러나 적절한 권한 집합을 가진 관리자는 먼저 데이터 집합을 삭제한 다음 스키마를 삭제할 수 있습니다. |
| [!UICONTROL Adobe Experience Platform]에서 데이터 세트를 삭제하시겠습니까? | AEP에서 데이터 세트를 삭제하면 해당 데이터 세트에서 해당 데이터 세트를 포함하는 모든 연결로의 데이터 흐름이 중지됩니다. 해당 데이터 세트의 데이터는 연관된 CJA 연결에서 자동으로 삭제되지 않습니다. |
| [!UICONTROL Customer Journey Analytics]에서 데이터 세트를 삭제하시겠습니까? | 현재 저장된 연결 내에서는 데이터 세트를 삭제할 수 없습니다. 전체 연결을 삭제하고 다시 시작해야 합니다. 그러나 [!UICONTROL Adobe Experience Platform]에서 데이터 세트를 삭제할 수 있습니다. |
| 데이터 세트에서 일괄 처리를 삭제하시겠습니까([!UICONTROL Adobe Experience Platform])? | [!UICONTROL Adobe Experience Platform] 데이터 세트에서 일괄 처리가 삭제되면 해당 특정 일괄 처리가 들어 있는 CJA 연결에서 동일한 일괄 처리가 제거됩니다.  CJA는 [!UICONTROL Adobe Experience Platform]에서 일괄 삭제 알림을 수신합니다. |
| 인제스트하는 동안 **일괄 처리를 [!UICONTROL Customer Journey Analytics]에 삭제하시겠습니까?** | 데이터 세트에 하나의 일괄 처리만 있을 경우 해당 일괄 처리에서 얻은 데이터나 부분 데이터는 [!UICONTROL Customer Journey Analytics]에 표시되지 않습니다. 수집은 롤백됩니다. 예를 들어 데이터 세트에 5개의 배치가 있고 데이터 세트를 삭제할 때 이미 인제스트한 3개의 배치인 경우 해당 3개의 배치의 데이터가 [!UICONTROL Customer Journey Analytics]에 표시됩니다. |
| [!UICONTROL Customer Journey Analytics]에서 연결을 삭제하시겠습니까? | 다음과 같은 오류 메시지가 표시됩니다.<ul><li>삭제된 연결에 대해 만들어진 모든 데이터 보기는 더 이상 작동하지 않습니다.</li><li> 마찬가지로, 삭제된 연결의 데이터 보기에 의존하는 모든 Workspace 프로젝트는 작동하지 않습니다.</li></ul> |
| [!UICONTROL Customer Journey Analytics]에서 데이터 보기를 삭제하시겠습니까? | 이 삭제된 데이터 보기에 의존하는 모든 Workspace 프로젝트가 작동하지 않는다는 오류 메시지가 표시됩니다. |
