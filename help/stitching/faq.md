---
title: 결합 FAQ
description: 결합에 대해 자주 묻는 질문
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 78803a2062b38b0f4a80837d18dbf3e9cc609cc8
workflow-type: tm+mt
source-wordcount: '1910'
ht-degree: 28%

---

# 자주 묻는 질문

다음은 결합에 대한 몇 가지 자주 묻는 질문입니다.

## 채널 간 이동

+++ 사람들이 한 채널에서 다른 채널로 이동하는 방법을 결합으로 어떻게 확인할 수 있습니까?

데이터 세트 ID 차원과 함께 흐름 시각화를 사용할 수 있습니다.

1. [Customer Journey Analytics](https://analytics.adobe.com)에 로그인하고 빈 Workspace 프로젝트를 만듭니다.
2. 왼쪽의 **[!UICONTROL **&#x200B;시각화&#x200B;**]** 탭을 선택하고 **[!UICONTROL **&#x200B;흐름&#x200B;**]** 시각화를 오른쪽의 캔버스로 드래그합니다.
3. 왼쪽의 **[!UICONTROL **&#x200B;구성 요소&#x200B;**]** 탭을 선택하고 **[!UICONTROL **&#x200B;데이터 세트 ID **]** 차원을 **[!UICONTROL ** Dimension 또는 항목&#x200B;**]** 레이블이 지정된 가운데 위치로 드래그합니다.
4. 이 플로우 보고서는 대화형입니다. 흐름을 후속 또는 이전 페이지로 확장하려면 값 중 하나를 선택합니다. 마우스 오른쪽 버튼 클릭 메뉴를 사용하여 열을 확장하거나 축소하십시오. 동일한 플로우 보고서 내에서 다양한 차원을 사용할 수도 있습니다.

데이터 세트 ID 차원 항목의 이름을 바꾸려는 경우 조회 데이터 세트를 사용할 수 있습니다.

+++

## 재생

+++ 재생 방문자 결합은 얼마나 오래 지속됩니까?

재입력을 위한 전환 확인 기간은 데이터 재생 빈도에 따라 다릅니다. 예를 들어 매주 한 번 데이터를 재생하도록 결합을 설정하는 경우, 재입력을 위한 전환 확인 기간은 7일입니다. 데이터를 매일 재생하도록 결합을 설정하는 경우, 재입력을 위한 전환 확인 기간은 1일입니다.

+++

## 공유된 디바이스

+++ 공유 디바이스는 어떻게 처리됩니까?

상황에 따라 여러 사람이 동일한 디바이스에서 로그인할 수 있습니다. 이러한 디바이스들로는 집의 공유 디바이스, 도서관의 공유 PC 또는 소매점의 키오스크 등이 있습니다.

임시 ID는 영구 ID를 무시하므로 공유 디바이스는 동일한 디바이스에서 생성된 경우에도 별도의 사용자로 간주됩니다.

+++

## 많은 영구 ID

+++ 결합은 한 사람이 많은 영구 ID를 갖는 상황을 어떻게 처리합니까?

경우에 따라 개별 사용자가 많은 영구 ID와 연결될 수 있습니다. 예로는 개인이 브라우저의 쿠키를 자주 지우거나 브라우저의 개인/시크릿 모드를 사용하는 것입니다.

필드 기반 결합의 경우, 영구 ID 수는 임시 ID와 관련이 없습니다. 단일 사용자는 여러 디바이스를 연결하는 Customer Journey Analytics의 기능에 영향을 주지 않고 원하는 개수의 디바이스에 액세스할 수 있습니다.

그래프 기반 결합의 경우, ID 그래프에서 한 사람이 여러 개의 영구 ID를 가질 수 있습니다. 그래프 기반 결합은 지정된 네임스페이스를 기반으로 하는 영구 ID를 사용합니다. 동일한 네임스페이스에 대한 영구 ID가 더 있는 경우 사전 편집된 첫 번째 영구 ID가 사용됩니다.

+++

## 결합 프로세스

+++ 필요한 정보를 사용하여 Adobe 계정 팀에 연락하면 다시 입력되는 데이터 세트를 사용할 수 있는 데 시간이 얼마나 걸립니까?

라이브 결합은 Adobe에서 결합을 활성화한 후 약 1주 후에 사용할 수 있습니다. 채우기 가용성은 기존 데이터의 양에 따라 다릅니다. 작은 데이터 세트(하루에 100만 개 미만의 이벤트)는 보통 2일이 걸리지만 대규모 데이터 세트(하루에 10억 개의 이벤트)는 1주일 이상 걸릴 수 있습니다.

+++

## 크로스 디바이스 분석 및 크로스 채널 분석

+++ 크로스 디바이스 분석(기존 Analytics의 한 기능)과 크로스 채널 분석의 차이점은 무엇입니까?

[크로스 디바이스 분석](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html)은(는) 기존 Adobe Analytics 고유의 기능으로, 사용자가 여러 디바이스에서 작동하는 방식을 이해할 수 있습니다. 디바이스 데이터를 서로 연결하는 두 가지 워크플로, 즉 필드 기반 결합 및 디바이스 그래프를 제공합니다.

크로스 채널 분석은 Customer Journey Analytics 고유의 사용 사례로서 사용자가 디바이스와 채널 모두에서 작동하는 방식을 이해할 수 있습니다. 데이터 세트의 개인 ID를 결합하므로 해당 데이터 세트를 다른 데이터 세트와 매끄럽게 결합할 수 있습니다. 이 기능은 교차 장치 분석 필드 기반 결합과 유사하게 디자인적으로 작동하지만 기존 Analytics와 Customer Journey Analytics 간에 데이터 아키텍처가 달라 구현이 달라집니다. 자세한 내용은 [결합](overview.md) 및 [크로스 채널 분석](../use-cases/cross-channel/cross-channel.md) 사용 사례를 참조하십시오.

+++

## 개인 정보 보호

+++ 결합은 개인 정보 요청을 어떻게 처리합니까?

Adobe은 현지 및 국제 법에 따라 개인 정보 보호 요청을 처리합니다. Adobe에서는 데이터 액세스 및 삭제 요청을 제출하기 위해 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)를 제공합니다. 이러한 요청은 원래 데이터 세트와 재입력된 데이터 세트 모두에 적용됩니다.

>[!IMPORTANT]
>
>개인 정보 보호 요청의 일부로서 결합 해제 프로세스는 2025년 초에 변경됩니다. 현재 결합 해제 프로세스는 알려진 최신 버전의 ID를 사용하여 이벤트를 다시 지정합니다. 이벤트를 다른 정체성으로 재지정하는 것은 바람직하지 않은 법적 결과를 가져올 수 있습니다. 이러한 문제를 해결하기 위해 2025년부터 새로운 결합 해제 프로세스는 영구 ID로 개인 정보 보호 요청의 대상인 이벤트를 업데이트합니다.
> 

예시하려면 결합 전과 결합 후에 ID, 이벤트에 대한 다음 데이터를 상상하십시오.

| ID 맵 | Id | timestamp | 영구 ID | 영구 네임스페이스 | 임시 id | 임시 네임스페이스 |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | 알렉스 | CustId |


| 이벤트 데이터 세트 | Id | timestamp | 영구 ID | 영구 네임스페이스 | 임시 id | 임시 네임스페이스 |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | 알렉스 | CustId |


| 결합된 데이터 세트 | Id | timestamp | 영구 ID | 영구 네임스페이스 | 임시 id | 임시 네임스페이스 | 결합된 ID | 결합된 네임스페이스 |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | 알렉스 | CustId | 알렉스 | CustId |


**개인 정보 보호 요청에 대한 현재 프로세스**

CustID Bob이 있는 고객에 대한 개인 정보 보호 요청을 받으면 취소선 항목이 있는 행이 삭제됩니다. 다른 이벤트는 ID 맵을 사용하여 다시 시작됩니다. 예를 들어 결합된 데이터 세트의 첫 번째 결합된 ID는 **Alex**(으)로 업데이트됩니다.

| ID 맵 | Id | timestamp | 영구 ID | 영구 네임스페이스 | 임시 id | 임시 네임스페이스 |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | 알렉스 | CustId |


| 이벤트 데이터 세트 | Id | timestamp | 영구 ID | 영구 네임스페이스 | 임시 id | 임시 네임스페이스 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | 알렉스 | CustId |


| 결합된 데이터 세트 | Id | timestamp | 영구 ID | 영구 네임스페이스 | 임시 id | 임시 네임스페이스 | 결합된 ID | 결합된 네임스페이스 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **알렉스** | CustId |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | 알렉스 | CustId | 알렉스 | CustId |


**개인 정보 요청을 위한 새 프로세스**

CustID Bob이 있는 고객에 대한 개인 정보 보호 요청을 받으면 취소선 항목이 있는 행이 삭제됩니다. 다른 이벤트는 영구 ID를 사용하여 다시 시작됩니다. 예를 들어 결합된 데이터 세트의 첫 번째 결합된 ID는 **123**(으)로 업데이트됩니다.

| ID 맵 | Id | timestamp | 영구 ID | 영구 네임스페이스 | 임시 id | 임시 네임스페이스 |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | 알렉스 | CustId |


| 이벤트 데이터 세트 | Id | timestamp | 영구 ID | 영구 네임스페이스 | 임시 id | 임시 네임스페이스 |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | 알렉스 | CustId |


| 결합된 데이터 세트 | Id | timestamp | 영구 ID | 영구 네임스페이스 | 임시 id | 임시 네임스페이스 | 결합된 ID | 결합된 네임스페이스 |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | 알렉스 | CustId | 알렉스 | CustId |

+++

## 빈 영구 ID 값

+++ 하나 이상의 이벤트에서 영구 ID 필드가 비어 있으면 어떻게 됩니까?

결합되는 데이터 세트의 이벤트에서 영구 ID 필드가 비어 있는 경우 다음 두 가지 방법 중 하나로 해당 이벤트에 대한 결합된 ID가 결정됩니다.

* 임시 ID 필드가 비어 있지 않으면 Customer Journey Analytics은 임시 ID의 값을 결합된 ID로 사용합니다.
* 임시 ID 필드가 비어 있으면 Customer Journey Analytics은 결합된 ID도 비워 둡니다. 이 경우 이벤트에서 영구 ID, 임시 ID 및 결합된 ID는 모두 비어 있습니다. 이러한 유형의 이벤트는 결합된 ID가 개인 ID로 선택된 위치에서 결합되는 데이터 세트를 사용하여 모든 Customer Journey Analytics 연결에서 삭제됩니다.

+++


## 정의되지 않은 임시 ID 값

+++ 하나 이상의 이벤트에 있는 임시 ID 필드에 `Undefined`과(와) 같은 자리 표시자 값이 있는 경우 어떻게 됩니까?

임시 ID에 대한 자리 표시자 값을 사용하는 데이터에 스티칭이 적용될 때 발생하는 &#39;사람 축소&#39;에 주의하십시오. 아래 예제 표에서 CRM 시스템에서 가져온 데이터 세트에서 가져온 정의되지 않은 개인 ID가 &#39;Undefined&#39; 값으로 채워져 잘못된 개인 표시가 발생합니다.

| 이벤트 | 타임스탬프 | 영구 ID (쿠키 ID) | 임시 ID (로그인 ID) | 결합된 ID(재생 후) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Cory** |
| 2 | 2023-05-12 12:02 | 123 | 코리 | **Cory** |
| 3 | 2023-05-12 12:03 | 456 | 정의되지 않음 | **정의되지 않음** |
| 4 | 2023-05-12 12:04 | 456 | - | **정의되지 않음** |
| 5 | 2023-05-12 12:05 | 789 | 정의되지 않음 | **정의되지 않음** |
| 6 | 2023-05-12 12:06 | 012 | 정의되지 않음 | **정의되지 않음** |
| 7 | 2023-05-12 12:07 | 012 | - | **정의되지 않음** |
| 8 | 2023-05-12 12:03 | 789 | 정의되지 않음 | **정의되지 않음** |
| 9 | 2023-05-12 12:09 | 456 | - | **정의되지 않음** |
| 10 | 2023-05-12 12:02 | 123 | - | **Cory** |
| | | **장치 4개** | **2명**:<br/>이벤트 1, 4, 7, 9, 10 삭제됨 | **2명**:<br/>Cory, 인증되지 않음(한 명으로 축소) |

+++

## 지표 비교

+++ Customer Journey Analytics에 결합된 데이터 세트의 지표를 Customer Journey Analytics에 결합되지 않은 데이터 세트의 유사한 지표 및 Adobe Analytics과 어떻게 비교합니까?

Customer Journey Analytics의 특정 지표는 기존 Analytics의 지표와 유사하지만 비교하는 대상에 따라 다른 지표도 있습니다. 아래 표에는 몇 가지 일반적인 지표가 비교되어 있습니다.

| **Customer Journey Analytics에 결합된 데이터** | **Customer Journey Analytics에 결합되지 않은 데이터** | **Adobe Analytics** | **CDA가 포함된 Analytics Ultimate** |
| ----- | ----- | ----- | ----- |
| **사람** = 결합된 ID가 개인 ID로 선택된 고유한 개인 ID 수입니다. **인원**&#x200B;은 결합 프로세스의 결과에 따라 기존 Adobe Analytics의 **고유 방문자 수**&#x200B;보다 높거나 낮을 수 있습니다. | **사람** = 개인 ID로 선택한 열에 따른 고유한 개인 ID 수입니다. Analytics 소스 커넥터 데이터 세트의 **People**&#x200B;은(는) `endUserIDs._experience.aaid.id`이(가) Customer Journey Analytics에서 개인 ID로 사용되는 경우 기존 Adobe Analytics의 **고유 방문자 수**&#x200B;와(과) 유사합니다. | **고유 방문자 수**&#x200B;는 고유 방문자 ID의 수입니다. **고유 방문자 수**&#x200B;는 고유한 **ECID** 수와 동일하지 않을 수 있습니다. | [인원](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=ko-KR)을 참조하십시오. |
| **세션**&#x200B;은 Customer Journey Analytics 데이터 보기에서의 세션 설정을 기반으로 정의됩니다. 결합 프로세스를 통해 여러 디바이스의 개별 세션을 단일 세션으로 결합할 수 있습니다. | **세션**&#x200B;은 Customer Journey Analytics 데이터 보기에 지정된 세션 설정을 기반으로 정의됩니다. | **방문 횟수**: [방문 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=ko-KR)를 참조하십시오. | **방문 횟수**&#x200B;는 [CDA 가상 보고서 세트](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=ko-KR)에 지정된 세션 설정을 기반으로 정의됩니다. |
| **이벤트**&#x200B;는 Customer Journey Analytics에서 결합된 데이터의 행 수입니다. 이 지표는 일반적으로 기존 Adobe Analytics의 **발생 횟수**&#x200B;에 가깝습니다. 단, 영구 ID가 비어 있는 행에 대한 위의 FAQ를 참고하십시오. | **이벤트**&#x200B;는 Customer Journey Analytics에서 결합되지 않은 데이터의 행 수입니다. 이 지표는 일반적으로 기존 Adobe Analytics의 **발생 횟수**&#x200B;에 가깝습니다. 그러나 Experience Platform 데이터 레이크의 연결되지 않은 데이터에 빈 개인 ID가 포함된 이벤트가 있는 경우 이러한 이벤트는 Customer Journey Analytics에 포함되지 않습니다. | **발생 횟수**: [발생 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ko-KR)를 참조하십시오. | **발생 횟수**: [발생 횟수](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=ko-KR)를 참조하십시오. |

다른 지표는 Customer Journey Analytics 및 Adobe Analytics과 유사할 수 있습니다. 예를 들어 Adobe Analytics [사용자 지정 이벤트](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=ko-KR) 1-100의 총 횟수는 결합 여부에 관계없이 기존 Adobe Analytics과 Customer Journey Analytics 간에 호환됩니다. Customer Journey Analytics과 Adobe Analytics 간의 이벤트 중복 제거와 같은 [기능의 차이](/help/getting-started/aa-vs-cja/cja-aa.md))로 인해 두 제품 간에 불일치가 발생할 수 있습니다.

+++

## ID 맵

+++ Customer Journey Analytics이 ID 맵 필드를 사용할 수 있습니까?

아니요. 현재 Customer Journey Analytics은 결합을 위해 ID 맵 필드를 사용할 수 없습니다.

+++

## 그래프 기반 결합으로 전환

+++ 필드 기반 결합에서 그래프 기반 결합으로 전환하려면 데이터를 다시 수집해야 합니까?

데이터는 Experience Platform에 다시 가져올 필요는 없지만 Customer Journey Analytics에서 다시 구성해야 합니다. 다음 단계를 따르십시오.

1. 새 그래프 기반 결합된 데이터 세트를 설정합니다.
1. 새 데이터 세트를 Customer Journey Analytics의 새 연결의 일부로 구성합니다.
1. 새 연결을 사용하도록 기존 데이터 보기 전환(및 이러한 새 그래프 기반 결합 데이터 세트)
1. 필드 기반의 결합된 데이터 세트를 사용 중이던 이전 연결을 제거합니다.

+++

## 보고 중단

+++ 기존 보고서가 중단됩니까?

위에 설명된 단계를 따르는 경우에는 해당되지 않습니다. 그렇지 않으면 Adobe Consulting에 추가 지원을 요청하십시오.

+++


