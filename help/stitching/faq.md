---
title: 결합 FAQ
description: 결합에 대해 자주 묻는 질문
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: c87aaefdd15e02b7fe2cf8e638830aa278d46b92
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 35%

---

# 자주 묻는 질문

다음은 결합에 대한 몇 가지 자주 묻는 질문입니다.

+++**사람들이 한 채널에서 다른 채널로 이동하는 방법을 결합으로 어떻게 확인할 수 있습니까?**

데이터 세트 ID 차원과 함께 흐름 시각화를 사용할 수 있습니다.

1. 에 로그인 [Customer Journey Analytics](https://analytics.adobe.com) 빈 Workspace 프로젝트를 만듭니다.
2. 다음 항목 선택 **[!UICONTROL **&#x200B;시각화&#x200B;**]** 왼쪽의 탭을 클릭하고 **[!UICONTROL **&#x200B;플로우&#x200B;**]** 오른쪽에 있는 캔버스로 시각화하십시오.
3. 다음 항목 선택 **[!UICONTROL **&#x200B;구성 요소&#x200B;**]** 왼쪽의 탭을 클릭하고 차원을 드래그합니다. **[!UICONTROL **&#x200B;데이터 세트 ID **]** 레이블이 지정된 가운데 위치로 **[!UICONTROL ** Dimension 또는 항목&#x200B;**]**.
4. 이 플로우 보고서는 대화형입니다. 흐름을 후속 또는 이전 페이지로 확장하려면 값 중 하나를 선택합니다. 마우스 오른쪽 버튼 클릭 메뉴를 사용하여 열을 확장하거나 축소하십시오. 동일한 플로우 보고서 내에서 다양한 차원을 사용할 수도 있습니다.

데이터 세트 ID 차원 항목의 이름을 바꾸려는 경우 조회 데이터 세트를 사용할 수 있습니다.

+++

+++**재생 방문자 결합은 얼마나 오래 지속됩니까?**

재입력을 위한 전환 확인 기간은 데이터 [재생](explained.md) 빈도에 따라 다릅니다. 예를 들어 매주 한 번 데이터를 재생하도록 결합을 설정하는 경우, 재입력을 위한 전환 확인 기간은 7일입니다. 데이터를 매일 재생하도록 결합을 설정하는 경우, 재입력을 위한 전환 확인 기간은 1일입니다.

+++

+++**공유 디바이스는 어떻게 처리됩니까?**

상황에 따라 여러 사람이 동일한 디바이스에서 로그인할 수 있습니다. 이러한 디바이스들로는 집의 공유 디바이스, 도서관의 공유 PC 또는 소매점의 키오스크 등이 있습니다.

임시 ID는 영구 ID를 무시하므로 공유 디바이스는 동일한 디바이스에서 생성된 경우에도 별도의 사용자로 간주됩니다.

+++

+++**결합은 한 사람이 많은 영구 ID를 갖는 상황을 어떻게 처리합니까?**

경우에 따라 개별 사용자가 많은 영구 ID와 연결될 수 있습니다. 예로는 개인이 브라우저의 쿠키를 자주 지우거나 브라우저의 개인/시크릿 모드를 사용하는 것입니다.

영구 ID 수는 임시 ID와 관련이 없습니다. 단일 사용자는 여러 디바이스를 연결하는 Customer Journey Analytics의 기능에 영향을 주지 않고 원하는 개수의 디바이스에 액세스할 수 있습니다.

+++

+++**원하는 정보를 사용하여 Adobe 계정 팀에 연락하면 다시 입력된 데이터 세트를 사용할 수 있는 데 시간이 얼마나 걸립니까?**

라이브 결합은 Adobe에서 결합을 활성화한 후 약 1주 후에 사용할 수 있습니다. 채우기 가용성은 기존 데이터의 양에 따라 다릅니다. 작은 데이터 세트(하루에 100만 개 미만의 이벤트)는 보통 2일이 걸리지만 대규모 데이터 세트(하루에 10억 개의 이벤트)는 1주일 이상 걸릴 수 있습니다.

+++

+++**크로스 디바이스 분석(기존 Analytics의 한 기능)과 크로스 채널 분석의 차이점은 무엇입니까?**

[크로스 디바이스 분석](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html) 는 기존 Adobe Analytics 고유의 기능으로, 사용자가 여러 디바이스에서 작동하는 방식을 이해할 수 있습니다. 디바이스 데이터를 서로 연결하는 두 가지 워크플로, 즉 필드 기반 결합 및 디바이스 그래프를 제공합니다.

크로스 채널 분석은 Customer Journey Analytics 고유의 사용 사례로서 사용자가 디바이스와 채널 모두에서 작동하는 방식을 이해할 수 있습니다. 데이터 세트의 개인 ID를 결합하므로 해당 데이터 세트를 다른 데이터 세트와 매끄럽게 결합할 수 있습니다. 이 기능은 교차 장치 분석 필드 기반 결합과 유사하게 디자인적으로 작동하지만 기존 Analytics와 Customer Journey Analytics 간에 데이터 아키텍처가 달라 구현이 달라집니다. 다음을 참조하십시오 [결합](overview.md) 및 [크로스 채널 분석](../use-cases/cross-channel/cross-channel.md) 자세한 내용은 사용 사례 를 참조하십시오.

+++**결합은 GDPR 및 CCPA 요청을 어떻게 처리합니까?**

Adobe은 현지 및 국제 법에 따라 GDPR 및 CCPA 요청을 처리합니다. Adobe에서는 데이터 액세스 및 삭제 요청을 제출하기 위해 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)를 제공합니다. 이러한 요청은 원래 데이터 세트와 재입력된 데이터 세트 모두에 적용됩니다.

+++

+++**하나 이상의 이벤트에서 영구 ID 필드가 비어 있으면 어떻게 됩니까?**

결합되는 데이터 세트의 이벤트에서 영구 ID 필드가 비어 있는 경우 다음 두 가지 방법 중 하나로 해당 이벤트에 대한 결합된 ID가 결정됩니다.

* 임시 ID 필드가 비어 있지 않으면 Customer Journey Analytics은 임시 ID의 값을 결합된 ID로 사용합니다.
* 임시 ID 필드가 비어 있으면 Customer Journey Analytics은 결합된 ID도 비워 둡니다. 이 경우 이벤트에서 영구 ID, 임시 ID 및 결합된 ID는 모두 비어 있습니다. 이러한 유형의 이벤트는 결합된 ID가 개인 ID로 선택된 위치에서 결합되는 데이터 세트를 사용하여 모든 Customer Journey Analytics 연결에서 삭제됩니다.

+++

+++**Customer Journey Analytics에 결합된 데이터 세트의 지표를 Customer Journey Analytics에 결합되지 않은 데이터 세트의 유사한 지표 및 Adobe Analytics과 어떻게 비교합니까?**

Customer Journey Analytics의 특정 지표는 기존 Analytics의 지표와 유사하지만 비교하는 대상에 따라 다른 지표도 있습니다. 아래 표에는 몇 가지 일반적인 지표가 비교되어 있습니다.

| **Customer Journey Analytics 결합 데이터** | **연결되지 않은 데이터 Customer Journey Analytics** | **Adobe Analytics** | **CDA가 포함된 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **사람** = 결합된 ID가 개인 ID로 선택된 고유한 개인 ID 수입니다. **인원**&#x200B;은 결합 프로세스의 결과에 따라 기존 Adobe Analytics의 **고유 방문자 수**&#x200B;보다 높거나 낮을 수 있습니다. | **사람** = 개인 ID로 선택한 열에 따른 고유한 개인 ID 수입니다. **사람** analytics 소스 커넥터 데이터 세트의 는 와 유사합니다. **고유 방문자 수** 기존 Adobe Analytics에서 `endUserIDs._experience.aaid.id` 는 Customer Journey Analytics에서 개인 ID로 사용됩니다. | **고유 방문자 수**&#x200B;는 고유 방문자 ID의 수입니다. **고유 방문자 수**&#x200B;는 고유한 **ECID** 수와 동일하지 않을 수 있습니다. | [인원](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=ko-KR)을 참조하십시오. |
| **세션**: Customer Journey Analytics 데이터 보기의 세션 설정을 기반으로 정의됩니다. 결합 프로세스를 통해 여러 디바이스의 개별 세션을 단일 세션으로 결합할 수 있습니다. | **세션**: Customer Journey Analytics 데이터 보기에 지정된 세션 설정을 기반으로 정의됩니다. | **방문 횟수**: [방문 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=ko-KR)를 참조하십시오. | **방문 횟수**&#x200B;는 [CDA 가상 보고서 세트](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=ko-KR)에 지정된 세션 설정을 기반으로 정의됩니다. |
| **이벤트** = Customer Journey Analytics에서 결합된 데이터의 행 수입니다. 이 지표는 일반적으로 기존 Adobe Analytics의 **발생 횟수**&#x200B;에 가깝습니다. 단, 영구 ID가 비어 있는 행에 대한 위의 FAQ를 참고하십시오. | **이벤트** = Customer Journey Analytics에서 결합되지 않은 데이터의 행 수입니다. 이 지표는 일반적으로 기존 Adobe Analytics의 **발생 횟수**&#x200B;에 가깝습니다. 그러나 Experience Platform 데이터 레이크의 연결되지 않은 데이터에 빈 개인 ID가 포함된 이벤트가 있는 경우 이러한 이벤트는 Customer Journey Analytics에 포함되지 않습니다. | **발생 횟수**: [발생 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ko-KR)를 참조하십시오. | **발생 횟수**: [발생 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ko-KR)를 참조하십시오. |

다른 지표는 Customer Journey Analytics 및 Adobe Analytics과 유사할 수 있습니다. 예를 들어 Adobe Analytics의 총 횟수입니다 [사용자 지정 이벤트](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=ko-KR) 1-100은 기존 Adobe Analytics과 Customer Journey Analytics(결합 여부에 상관없이)에 필적합니다. [기능의 차이점](/help/getting-started/aa-vs-cja/cja-aa.md)) Customer Journey Analytics과 Adobe Analytics 간의 이벤트 중복 제거와 같은 기능은 두 제품 간에 불일치를 일으킬 수 있습니다.

+++

+++**Customer Journey Analytics이 ID 맵 필드를 사용할 수 있습니까?**

아니요. 현재 Customer Journey Analytics은 결합을 위해 ID 맵 필드를 사용할 수 없습니다.

+++
