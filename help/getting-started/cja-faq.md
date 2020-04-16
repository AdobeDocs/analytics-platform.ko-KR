---
title: Customer Journey Analytics FAQ
description: Customer Journey Analytics - 자주 묻는 질문
translation-type: ht
source-git-commit: 69f9154387ec11e9b1ec6f867ebab6d556451a9a

---


# FAQ

| 질문 | 답변 |
|---|---|
| **전제 조건** |  |
| [!UICONTROL Customer Journey Analytics]에 Device Graph 또는 Device Coop가 필요하십니까? | 아니요. [!UICONTROL Customer Journey Analytics]에는 개인 Device Graph 또는 Device Coop가 필요하지 않습니다. 실제로 아직 지원되지 않습니다. |
| [!UICONTROL Customer Journey Analytics]에 Experience Cloud ID(ECID)가 필요하십니까? | 아니요. [!UICONTROL Customer Journey Analytics]는 데이터 세트에 있는 ID가 ECID이든 다른 ID이든 모두 지원합니다. |
| Customer Journey Analytics 전에 데이터를 ETL(추출, 변환, 로드)해야 하는 경우엔 어떻게 해야 합니까? | 현재 AEP에 데이터를 추가하기 전에 데이터를 변환해야 하는 경우 ETL 파트너(Unifi 또는 Informatica)와 함께 작업해야 합니다. 이미 데이터를 처리한 후 ETL이 필요한 경우 AEP Query Services에서 제한된 옵션을 제공합니다. |
| **결합** |  |
| 여러 디바이스 또는 데이터 세트에서 [!UICONTROL Customer Journey Analytics]는 &quot;결합&quot;할 수 있습니까? | 아니요. [!UICONTROL Customer Journey Analytics]는 &quot;고유 ID 가져오기&quot; 분석 시스템입니다. 현재 좋은 결합 방법을 구상하고 있습니다. |
| 익명 동작에서 인증 동작으로 결합하는 작업이 지원됩니까? | 아니요. 아직 지원되지 않습니다. |
| **[!UICONTROL Customer Journey Analytics]**로 데이터 가져오기 |  |
| [!UICONTROL Experience Platform]에서 [!UICONTROL Customer Journey Analytics]의 예상 지연 시간은 얼마입니까? | <ul><li>일반 로드 중: 60분 미만입니다. <br>**참고:**파이프라인을 통해 비정상적으로 많은 데이터 흐름이 있는 경우 최대 24시간이 소요될 수 있습니다.</li><li>데이터 채우기(최대 100억 개의 이벤트)의 경우에는 4주 미만입니다.</li></ul> |
| [!UICONTROL Customer Journey Analytics]에서 온라인 데이터를 오프라인 데이터로 어떻게 연결합니까? | [!UICONTROL Customer Journey Analytics]는 &quot;고유 ID 가져오기&quot; 분석 시스템입니다. 개인 ID가 데이터 세트 간에 일치하는 경우 [!UICONTROL Customer Journey Analytics]는 세그먼트, 기여도 분석, 플로우, 폴아웃 등을 연결할 수 있습니다. 세그먼트, 기여도, 흐름, 폴아웃 등을 연결할 수 있습니다. |
| 오프라인 데이터를 Customer Journey Analytics로 가져오려면 어떻게 해야 합니까? | Customer Journey Analytics에서 오프라인 데이터를 사용하려면 먼저 고객이 모든 데이터를 Experience Platform으로 가져와야 합니다. 필요한 경우 Experience Platform의 데이터 온보딩팀에서 고객에게 추천이나 컨설팅 서비스를 제공할 수 있습니다. |
| Analytics 데이터를 Customer Journey Analytics로 가져오려면 어떻게 해야 합니까? | Analytics 데이터는 Analytics Data Connector를 통해 Experience Platform에 연결할 수 있습니다. Analytics 필드는 대부분 XDM 형식으로 가져오지만 다른 필드는 아직 사용할 수 없습니다(마케팅 채널 차원 등). |
| 데이터 세트 요소를 데이터 보기로 취합하는 데 얼마나 걸립니까? | 시작하는 데 몇 시간이 소요되고 지난 13개월간의 데이터를 채우는 데는 며칠이 소요됩니다. |
| 데이터 간의 연결을 설정하려면 PII 데이터를 가져와야 합니까? | 아니요. PII가 아닌 고객 ID의 해시를 포함하여 모든 ID를 사용할 수 있습니다. |
| **기존 Analytics 구성 요소** |  |
| 기존의 Adobe Analytics 제품에 어떤 영향을 미칩니까? | Customer Journey Analytics는 차세대 분석 제품입니다. 현재 제품에서 Customer Journey Analytics로 진화하는 데 수년이 걸리며 많은 조정이 필요합니다. 본 릴리스는 이를 목표로 한 여러 작업 중 하나의 중요한 단계입니다. |
| Customer Journey Analytics에서 AEP 또는 다른 솔루션으로 세그먼트를 공유할 수 있습니까? | 아직 공유할 수 없습니다. 향후 Customer Journey Analytics에서 AEP로 세그먼트를 오랜 지연 없이 공유할 수 있는 새롭고 혁신적인 방법을 모색하고 있습니다. 즉, 잠재적인 해결 방법으로 Query Services의 결과를 통합 프로필에 공유할 수 있습니다. |
| 이전 eVar 설정은 어떻게 됩니까? | 기존 Adobe Analytics 센스의 eVar, prop, 이벤트는 Customer Journey Analytics에 더 이상 존재하지 않습니다. 무제한 스키마 요소(차원, 지표, 목록 필드)가 있습니다. 따라서 이제 데이터 수집 프로세스 동안 적용했던 모든 속성 설정이 쿼리 시간에 적용됩니다. |
| 모든 세션 및 변수 지속성 설정은 현재 어디에 있습니까? | Customer Journey Analytics의 경우 이러한 모든 설정은 보고서 시간에 적용되며 데이터 보기에 있습니다. 이제 이러한 설정을 변경하면 소급 적용되며, 여러 데이터 보기를 사용하여 여러 버전을 보유할 수 있습니다. |
| 기존 세그먼트/계산된 지표는 어떻게 됩니까? | Customer Journey Analytics는 더 이상 eVar, prop, 이벤트를 사용하지 않으며 대신 AEP 스키마를 사용합니다. 즉, 기존 세그먼트나 계산 지표는 Customer Journey Analytics와 호환되지 않습니다. |
| Customer Journey Analytics는 `Uniques Exceeded` 제한 사항을 어떻게 처리합니까? | Customer Journey Analytics에는 고유 값 제한이 없으므로 걱정할 필요가 없습니다. |
| 기존 [!DNL Data Workbench] 고객은 바로 Customer Journey Analytics로 이동할 수 있습니까? | 상황에 따라 다릅니다. UCP(Unified Customer Process)를 많이 사용하는 경우 결합을 구현하기 전까지 기다리십시오. 이미 높은 고객 인증률을 보유하고 있거나, 모든 데이터를 한 곳에서 확인하고 싶거나, eVar를 제거하려면 Customer Journey Analytics가 적합할 수 있습니다. |

