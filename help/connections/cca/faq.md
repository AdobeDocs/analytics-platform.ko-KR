---
title: 크로스 채널 분석 FAQ
description: 크로스 채널 분석 FAQ
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 100%

---

# FAQ

## 사람들이 한 채널에서 다른 채널로 이동하는 방법을 CCA로 어떻게 확인할 수 있습니까?

데이터 세트 ID 차원과 함께 흐름 시각화를 사용할 수 있습니다.

1. [analytics.adobe.com](https://analytics.adobe.com)에 로그인하고 빈 Workspace 프로젝트를 만듭니다.
2. 왼쪽의 시각화 탭을 클릭하고 플로우 시각화를 오른쪽의 캔버스로 드래그합니다.
3. 왼쪽의 구성 요소 탭을 클릭하고 &#39;데이터 세트 ID&#39; 차원을 &#39;차원 또는 항목&#39;이라는 레이블이 지정된 가운데 위치로 드래그합니다.
4. 이 플로우 보고서는 대화형입니다. 플로우를 다음 또는 이전 페이지로 확장하려면 값을 클릭합니다. 마우스 오른쪽 버튼 클릭 메뉴를 사용하여 열을 확장하거나 축소하십시오. 동일한 플로우 보고서 내에서 다양한 차원을 사용할 수도 있습니다.

데이터 세트 ID 차원 항목의 이름을 바꾸려는 경우 조회 데이터 세트를 사용할 수 있습니다.

## CCA는 방문자 재입력 기간을 얼마나 오래 전까지 적용합니까?

재입력을 위한 전환 확인 기간은 데이터 [재생](replay.md) 빈도에 따라 다릅니다. 예를 들어 매주 한 번 데이터를 재생하도록 CCA를 설정하는 경우, 재입력의 전환 확인 기간은 7일입니다. 데이터를 매일 재생하도록 CCA를 설정하는 경우, 재입력 전환 확인 기간은 1일입니다.

## 공유 디바이스는 어떻게 처리됩니까?

상황에 따라 여러 사람이 동일한 디바이스에서 로그인할 수 있습니다. 이러한 디바이스들로는 집의 공유 디바이스, 도서관의 공유 PC 또는 소매점의 키오스크 등이 있습니다.

임시 ID는 영구 ID를 무시하므로 공유 디바이스는 동일한 디바이스에서 생성된 경우에도 별도의 사용자로 간주됩니다.

## CCA는 단일 사용자가 다수의 영구 ID를 갖는 상황을 어떻게 처리합니까?

경우에 따라 개별 사용자가 복수의 영구 ID와 연결될 수 있습니다. 이러한 예로는 개인이 브라우저 쿠키를 자주 지우거나 브라우저의 개인/시크릿 모드를 사용하는 경우가 있습니다.

영구 ID 수는 임시 ID와 관련이 없습니다. 단일 사용자는 여러 디바이스를 연결하는 CCA의 기능에 영향을 주지 않고 원하는 개수의 디바이스에 액세스할 수 있습니다.

## 필요한 정보를 사용하여 계정 관리자에게 연락하면 다시 입력되는 데이터 세트를 사용할 수 있는 데 시간이 얼마나 걸립니까?

라이브 결합은 Adobe에서 크로스 채널 분석을 활성화한 후 약 1주 후에 사용할 수 있습니다. 채우기 가용성은 기존 데이터의 양에 따라 다릅니다. 작은 데이터 세트(하루에 100만 개 미만의 이벤트)는 보통 2일이 걸리지만 대규모 데이터 세트(하루에 10억 개의 이벤트)는 1주일 이상 걸릴 수 있습니다.

## 크로스 채널 분석은 GDPR 및 CCPA 요청을 어떻게 처리합니까?

Adobe는 현지 및 국제 법에 따라 GDPR 및 CCPA 요청을 처리합니다. Adobe에서는 데이터 액세스 및 삭제 요청을 제출하기 위해 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=ko-KR)를 제공합니다. 이러한 요청은 원래 데이터 세트와 재입력된 데이터 세트 모두에 적용됩니다.

## 하나 이상의 이벤트에서 영구 ID 필드가 비어 있으면 어떻게 됩니까?

필드 기반 결합으로 결합되는 데이터 세트의 이벤트에서 `Persistent ID` 필드가 비어 있는 경우 CCA에서는 다음 두 가지 방법 중 하나로 `Stitched ID` 필드가 채워집니다.
* `Transient ID` 필드가 비어 있지 않으면 CCA는 `Transient ID`의 값을 `Stitched ID`로 사용합니다.
* `Transient ID` 필드가 비어 있으면 CCA는 `Stitched ID`도 비워 둡니다. 이 경우 이벤트에서 `Persistent ID`, `Transient ID` 및 `Stitched ID`는 모두 비어 있게 됩니다. 이와 같은 이벤트는 `Stitched ID`가 `Person ID`로 선택된 위치에서 결합되는 데이터 세트를 사용하여 모든 CJA 연결의 CJA에서 삭제됩니다.

## CJA에 결합된 데이터 세트의 지표를 CJA에 결합되지 않은 데이터 세트의 유사한 지표 및 기존 Adobe Analytics와 비교하려면 어떻게 합니까?

CJA의 특정 지표는 기존 Analytics의 지표와 유사하지만 비교하는 대상에 따라 전혀 다른 지표도 있습니다. 아래 표에는 몇 가지 일반적인 지표가 비교되어 있습니다.

| **CJA에 결합된 데이터** | **CJA에 결합되지 않은 데이터** | **기존 Adobe Analytics** | **CDA가 포함된 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **인원**&#x200B;은 `Stitched ID`가 `Person ID`로 선택된 고유한 `Person ID`의 수입니다. **인원**&#x200B;은 결합 프로세스의 결과에 따라 기존 Adobe Analytics의 **고유 방문자 수**&#x200B;보다 높거나 낮을 수 있습니다. | **인원**&#x200B;은 `Person ID`로 선택된 열에 기반한 고유 `Person ID`의 수입니다. Adobe Analytics 커넥터 (ADC) 데이터 세트에 있는 **인원**&#x200B;은 CJA에서 `endUserIDs. _experience. aaid.id`가 `Person ID`로 선택된 경우 기존 Adobe Analytics의 **고유 방문자 수**&#x200B;와 유사합니다. | **고유 방문자 수**&#x200B;는 고유 방문자 ID의 수입니다. **고유 방문자 수**&#x200B;는 고유한 **ECID** 수와 동일하지 않을 수 있습니다. | [인원](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=en)을 참조하십시오. |
| **세션**&#x200B;은 CJA 데이터 보기에 지정된 세션화 설정을 기반으로 정의됩니다. 결합 프로세스를 통해 여러 디바이스의 개별 세션을 단일 세션으로 결합할 수 있습니다. | **세션**&#x200B;은 CJA 데이터 보기에 지정된 세션화 설정을 기반으로 정의됩니다. | **방문 횟수**: [방문 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=en)를 참조하십시오. | **방문 횟수**&#x200B;는 [CDA 가상 보고서 세트](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=en)에 지정된 세션화 설정을 기반으로 정의됩니다. |
| **이벤트**&#x200B;는 CJA에서 결합된 데이터의 행 수입니다. 일반적으로 이는 기존 Adobe Analytics의 **발생 횟수**&#x200B;에 가깝습니다. 단, 빈 `Persistent ID`가 있는 행에 대한 위의 FAQ를 참고하십시오. | **이벤트**&#x200B;는 CJA에서 결합되지 않은 데이터의 행 수입니다. 일반적으로 이는 기존 Adobe Analytics의 **발생 횟수**&#x200B;에 가깝습니다. 그러나 AEP 데이터 레이크의 연결되지 않은 데이터에 빈 `Person ID`가 포함된 이벤트가 있는 경우 이러한 이벤트는 CJA에서 삭제(미포함)됩니다. | **발생 횟수**: [발생 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en)를 참조하십시오. | **발생 횟수**: [발생 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en)를 참조하십시오. |

다른 지표는 CJA 및 기존 Adobe Analytics와 유사할 수 있습니다. 예를 들어, Adobe Analytics [사용자 지정 이벤트](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=en)(이벤트 1-100)의 총 횟수는 일반적으로 기존 Adobe Analytics 및 CJA에서 결합 여부에 관계없이 매우 유사해야 합니다. 단, 이는 CJA와 기존 Adobe Analytics 간의 이벤트 중복 제거와 같은 [기능의 차이](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-aa.html?lang=en)로 인해 항상 적용되지 않을 수 있습니다.
