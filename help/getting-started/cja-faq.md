---
title: Customer Journey Analytics FAQ
description: Customer Journey Analytics - 자주 묻는 질문
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: ht
source-wordcount: '1360'
ht-degree: 100%

---

# FAQ

CJA([!UICONTROL Customer Journey Analytics])는 차세대 분석 제품입니다. 다음은 CJA와 관련하여 자주 묻는 질문에 대한 답변입니다. 자세한 내용은 [Customer Journey Analytics 기능 지원](/help/getting-started/cja-aa.md)을 검토하십시오.

## 1. 전제 조건

| 질문 | 답변 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics]에 [!UICONTROL Private Device Graph] 또는 [!UICONTROL Device Coop]이 필요합니까? | 아니요. [!UICONTROL Customer Journey Analytics]에는 [!UICONTROL Private Device Graph] 또는 [!UICONTROL Device Coop]가 필요하지 않습니다. 실제로 아직 지원되지 않습니다. |
| [!UICONTROL Customer Journey Analytics]에 [!UICONTROL Experience Cloud ID] (ECID)가 필요합니까? | 아니요. [!UICONTROL Customer Journey Analytics]는 데이터 세트에서 선택한 ID가 ECID든 다른 ID이든 모두 지원합니다. |
| [!UICONTROL Customer Journey Analytics] 전에 데이터를 ETL(추출, 변환, 로드)해야 하는 경우엔 어떻게 해야 합니까? | Customer Journey Analytics에는 [데이터 준비](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=ko-KR) 기능이 포함되어 있으므로 데이터를 Adobe Experience Platform 데이터 레이크에 삽입하기 전에 데이터를 변환할 수 있습니다. 이미 데이터를 수집한 후 ETL이 필요한 경우 [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=ko-KR#queries)에서 일부 제한된 옵션을 제공합니다. 단, 이 경우 추가 비용이 발생할 수 있습니다. |

{style=&quot;table-layout:auto&quot;}

## 2. 데이터 결합(크로스 채널 분석)

| 질문 | 답변 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics]를 디바이스 또는 데이터 세트 간에 &quot;결합&quot;할 수 있습니까? | 예. [!UICONTROL Customer Journey Analytics]에는 CCA([크로스 채널 분석](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=ko-KR))이라고 하는 결합 솔루션이 있습니다. 이 솔루션을 사용하여 데이터 세트의 개인 ID에 대해 다시 키를 입력할 수 있으므로 여러 데이터 세트를 매끄럽게 결합할 수 있습니다. |
| 익명 동작에서 인증 동작으로 결합하는 작업이 지원됩니까? | 예. [크로스 채널 분석](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=ko-KR)은 인증된 세션과 인증되지 않은 세션의 사용자 데이터를 모두 확인하여 결합된 ID를 생성합니다. |
| CCA에서 &#39;재생&#39;은 어떻게 작동합니까? | CCA는 학습한 고유 식별자를 기반으로 데이터를 &quot;재생&quot;합니다. 재생으로 인해 연결에 새 디바이스가 결합됩니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=ko-KR#step-1%3A-live-stitching) |
| CCA에서 내역 데이터(채우기)의 결합은 어떻게 작동합니까? | 처음 켜질 때 Adobe에서 이전 달의 시작 시점(최대 60일)까지 포함하는 결합된 데이터 채우기를 제공합니다. 이 채우기 작업을 수행하려면 오래된 결합되지 않은 데이터에 임시 ID가 있어야 합니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=ko-KR#enable-cross-channel-analytics) |

{style=&quot;table-layout:auto&quot;}

## 3. [!UICONTROL Customer Journey Analytics]에 데이터 가져오기

| 질문 | 답변 |
| --- | --- |
| 하나의 [!UICONTROL Customer Journey Analytics] 연결에 다른 [!UICONTROL Adobe Experience Platform] 샌드박스의 데이터를 결합할 수 있습니까? | 아니요. 샌드박스에서 데이터에 액세스할 수 없습니다. 동일한 샌드박스 내에 있는 데이터 세트만 결합할 수 있습니다. [자세히 알아보기](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=ko-KR#select-sandbox-and-datasets) |
| [!UICONTROL Adobe Experience Platform]에서 [!UICONTROL Customer Journey Analytics]의 예상 대기 시간은 어떻게 됩니까? | <ul><li>일반 로드 중: 60분 미만입니다. <br>**참고:** 파이프라인을 통해 비정상적으로 많은 데이터 흐름이 있는 경우 최대 24시간이 소요될 수 있습니다.</li><li>데이터 채우기(크기에 상관없이 최대 13개월 데이터): &lt; 4주</li></ul> |
| [!UICONTROL Customer Journey Analytics]에서 온라인 데이터를 오프라인 데이터로 어떻게 연결합니까? | 개인 ID가 데이터 세트 간에 일치하는 경우 [!UICONTROL Customer Journey Analytics]는 전체 데이터 세트에서 필터, 기여도, 흐름, 폴아웃 등을 연결할 수 있습니다. |
| 오프라인 데이터를 [!UICONTROL Customer Journey Analytics]로 가져오려면 어떻게 해야 합니까? | Customer Journey Analytics에 대한 자격 증명을 통해 데이터를 Experience Platform에 수집할 수 있습니다. 그런 다음 Analysis Workspace에서의 보고를 위해 [!UICONTROL Customer Journey Analytics]에서 해당 데이터 및 데이터 보기에 대한 연결을 만들 수 있습니다. 필요한 경우 Experience Platform의 데이터 온보딩팀에서 추천이나 컨설팅 서비스를 제공할 수 있습니다. |
| [!UICONTROL Adobe Analytics] 데이터를 [!UICONTROL Customer Journey Analytics]로 가져오려면 어떻게 해야 합니까? | [!UICONTROL Adobe Analytics] 데이터는 [Adobe Analytics 소스 커넥터](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=ko-KR)를 통해 Experience Platform에 연결할 수 있습니다. [!UICONTROL Adobe Analytics] 필드는 대부분 XDM 형식으로 가져오지만 다른 필드는 아직 사용할 수 없습니다. |
| 데이터 세트 요소를 데이터 보기로 취합하는 데 얼마나 걸립니까? | 시작하는 데 몇 시간이 소요되고 지난 13개월간의 데이터를 채우는 데는 며칠이 소요됩니다. |
| 데이터 간의 연결을 설정하려면 PII 데이터를 가져와야 합니까? | 아니요. PII가 아닌 고객 ID의 해시를 포함하여 모든 ID를 사용할 수 있습니다. |

{style=&quot;table-layout:auto&quot;}

## 4. 기존 [!UICONTROL Adobe Analytics] 구성 요소

| 질문 | 답변 |
| --- | --- |
| Customer Journey Analytics에서 Experience Platform 통합 프로필 또는 기타 Experience Cloud 애플리케이션으로 필터(세그먼트)를 공유/게시할 수 있습니까? | 아직 아니지만 이 기능을 제공하기 위해 노력하고 있습니다. |
| 이전 eVar 설정은 어떻게 됩니까? | 기존 Adobe Analytics 센스의 eVar, prop, 이벤트는 [!UICONTROL Customer Journey Analytics]에 더 이상 존재하지 않습니다. 무제한 스키마 요소(차원, 지표, 목록 필드)가 있습니다. 따라서 이제 데이터 수집 프로세스 동안 적용했던 모든 속성 설정이 쿼리 시간에 적용됩니다. |
| 모든 세션 및 변수 지속성 설정은 현재 어디에 있습니까? | [!UICONTROL Customer Journey Analytics]의 경우 이러한 모든 설정은 보고서 시간에 적용되며 데이터 보기에 있습니다. 이제 이러한 설정을 변경하면 소급 적용되며, 여러 데이터 보기를 사용하여 여러 버전을 보유할 수 있습니다. |
| 기존 세그먼트/계산된 지표는 어떻게 됩니까? | [!UICONTROL Customer Journey Analytics]는 더 이상 eVar, prop, 이벤트를 사용하지 않으며 대신 AEP 스키마를 사용합니다. 즉, 기존 세그먼트나 계산 지표는 [!UICONTROL Customer Journey Analytics]와 호환되지 않습니다. |
| [!UICONTROL Customer Journey Analytics]는 `Uniques Exceeded` 제한 사항을 어떻게 처리합니까? | [!UICONTROL Customer Journey Analytics에는 고유 값 제한이 없으므로 걱정할 필요가 없습니다.] |
| 기존 [!DNL Data Workbench] 고객은 바로 Customer Journey Analytics로 이동할 수 있습니까? | 활용 사례에 따라 다릅니다. Adobe 계정 팀의 도움을 받으십시오. 현재 활용 사례가 이미 Customer Journey Analytics에 적합할 수도 있습니다. |

{style=&quot;table-layout:auto&quot;}

## 5. 데이터 구성 요소 삭제의 영향

데이터 삭제는 여섯 가지 유형의 구성 요소인 샌드박스, 스키마, 데이터 세트, 연결, 데이터 보기, Workspace 프로젝트와 관련이 있습니다. 다음은 이러한 구성 요소 중 하나를 삭제하는 것과 관련된 몇 가지 가능한 시나리오입니다.

| 다음을 수행하는 경우 | 발생하는 결과 |
| --- | --- |
| [!UICONTROL Adobe Experience Platform]에서 샌드박스를 삭제 | 샌드박스를 삭제하면 해당 샌드박스의 데이터 세트에 대한 [!UICONTROL Customer Journey Analytics] 연결로의 데이터 흐름이 정지됩니다. 현재는 삭제된 해당 샌드박스에 연결된 CJA의 연결이 자동으로 삭제되지 않습니다. |
| [!UICONTROL Adobe Experience Platform]에서 스키마를 삭제하지만 이 스키마와 연결된 데이터 세트는 삭제하지 않음 | [!UICONTROL Adobe Experience Platform]에서는 연관된 데이터 세트가 하나 이상 있는 스키마를 삭제할 수 없습니다. 그러나 적절한 권한 세트가 있는 관리자는 먼저 데이터 세트를 삭제한 다음 스키마를 삭제할 수 있습니다. |
| [!UICONTROL Adobe Experience Platform]에서 데이터 세트를 삭제 | AEP 데이터 레이크에서 데이터 세트를 삭제하면 해당 데이터 세트로부터 이 데이터 세트를 포함하는 모든 CJA 연결로의 데이터 흐름이 정지됩니다. 해당 데이터 세트의 데이터는 연관된 CJA 연결에서 자동으로 삭제되지 않습니다. |
| [!UICONTROL Customer Journey Analytics]에서 데이터 세트를 삭제 | 현재 저장된 연결 내에서는 데이터 세트를 삭제할 수 없습니다. 전체 연결을 삭제하고 다시 시작해야 합니다. (그러나 CJA SKU를 구매한 고객은 [!UICONTROL Adobe Experience Platform] 사용자 인터페이스에서 데이터 세트를 삭제할 수 있습니다.) |
| [!UICONTROL Adobe Experience Platform]의 데이터 세트에서 배치를 삭제 | [!UICONTROL Adobe Experience Platform] 데이터 세트에서 일괄 처리가 삭제되면 해당 특정 일괄 처리가 들어 있는 CJA 연결에서 동일한 일괄 처리가 제거됩니다.  CJA는 [!UICONTROL Adobe Experience Platform]에서 일괄 삭제 알림을 수신합니다. |
| 배치를 **Customer Journey Analytics**&#x200B;에 [!UICONTROL 수집하는 동안] 배치를 삭제 | 데이터 세트에 일괄 처리가 한 개만 있는 경우, 해당 일괄 처리의 데이터가 [!UICONTROL Customer Journey Analytics]에서 전혀 표시되지 않거나 일부 표시됩니다. 처리가 롤백됩니다. 데이터 세트에 5개의 일괄 처리가 있고 그 중 3개가 이미 데이터 세트를 삭제할 때 수집된 경우, 해당 3개 일괄 처리의 데이터가 [!UICONTROL Customer Journey Analytics]에 표시됩니다. |
| [!UICONTROL Customer Journey Analytics]에서 연결을 삭제 | 오류 메시지에 다음 내용이 표시됩니다.<ul><li>삭제된 연결에 대해 만들어진 모든 데이터 보기가 더 이상 작동하지 않습니다.</li><li> 마찬가지로, 삭제된 연결의 데이터 보기에 의존하는 모든 Analysis Workspace 프로젝트의 작동이 정지됩니다.</li></ul> |
| [!UICONTROL Customer Journey Analytics]에서 데이터 보기를 삭제 | 이 삭제된 데이터 보기에 의존하는 모든 Analysis Workspace 프로젝트의 작동이 중지된다는 오류 메시지가 표시됩니다. |
