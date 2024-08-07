---
description: 다차원 폴아웃 시퀀스를 만들기 위해 터치포인트를 지정하는 방법을 살펴보십시오.
title: 폴아웃 시각화 구성
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 67%

---

# 폴아웃 시각화 구성

터치포인트를 지정하여 차원이 여러 개인 폴아웃 시퀀스를 만들 수 있습니다. 일반적으로 터치포인트는 사이트에 있는 페이지입니다. 하지만 터치포인트는 페이지에 제한되지 않습니다. 예를 들어 고유 방문자 및 재방문뿐만 아니라 단위와 같은 이벤트를 추가할 수 있습니다. 범주, 브라우저 유형 또는 내부 검색어와 같은 차원을 추가할 수도 있습니다.

또한 터치포인트 내의 필터를 추가할 수도 있습니다. 예를 들어 iOS 및 Android 사용자와 같은 필터를 비교할 수 있습니다. 원하는 필터를 폴아웃의 맨 위에 드래그하십시오. 그러면 해당 필터에 대한 정보가 폴아웃 보고서에 추가됩니다. 해당 필터만 표시하려는 경우, 모든 방문 수 기준선을 제거할 수 있습니다.

추가할 수 있는 단계의 수나 사용된 차원의 수에 대한 제한은 없습니다.

머천다이징 eVar 및 [listVars](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html)(제품, listVars, 머천다이징 eVar 및 목록 속성과 같이 이벤트당 여러 개의 값이 있을 수 있는 변수)을 포함하여 eVar에 대해 경로를 지정할 수 있습니다. 예를 들어 어떤 사람이 한 페이지에서 신발, 셔츠를 보고 다른 페이지에서는 셔츠, 양말을 보는 경우, 신발의 다음 제품 흐름 보고서는 셔츠가 아니라 셔츠 및 양말이 됩니다.

1. 시각화 드롭다운의 [!UICONTROL 폴아웃] 시각화를 [!UICONTROL 자유 형식 테이블]로 드래그합니다.

1. 페이지 차원을 자유 형식 테이블로 드래그하고, 거기에서 페이지 (이 경우, 홈 - JJEsquire)를 **[!UICONTROL 터치포인트 추가]** 필드에 첫 번째 터치포인트로서 드래그합니다.

   ![JJEsquire가 터치포인트 추가 필드로 드래그한 것을 보여 주는 모든 방문 드롭다운입니다.](assets/fallout1.png)

   마우스를 터치 포인트 위에 놓아 폴아웃과, 터치 포인트의 이름, 해당 포인트에서의 개인 카운트와 같은 해당 수준에 대한 기타 정보를 확인하고, 해당 터치 포인트에 대한 성공률을 확인합니다(또한 성공률을 다른 터치 포인트에 대해 비교합니다.).

   막대의 회색 부분에서 원으로 표시된 숫자는 터치포인트 사이에 있는 폴아웃을 표시합니다 (해당 포인트에 대한 전체 폴아웃이 아님). 터치포인트 %는 이전 단계에서 성공한 폴스루를 폴아웃 보고서의 현재 단계에 표시합니다.

   단일 페이지를 전체 차원이 아닌 폴아웃 보고서에 추가할 수도 있습니다. 페이지 차원에서 오른쪽 화살표 &quot;>&quot;를 클릭하여 폴아웃 보고서에 추가할 특정 페이지를 선택합니다.

1. 시퀀스가 완료될 때까지 터치포인트를 계속 추가합니다.

   하나 이상의 추가 터치포인트를 한 터치포인트에 드래그하여 **여러 터치포인트를 결합** 할 수 있습니다.

   >[!NOTE]
   >
   >여러 필터는 AND로 결합되지만 차원 항목 및 지표와 같은 여러 항목은 OR로 결합됩니다.

   ![페이지:CamerRoll 또는 페이지: 카메라 터치포인트를 강조 표시했습니다.](assets/multiple_obj_touchpoint.png)

1. 또한 **개별 터치포인트를 경로 내의 다음 이벤트로 제한**&#x200B;할 수 있습니다(&quot;결과적으로&quot; 실행되는 것과 대조적으로). 각 터치포인트 아래에는 다음과 같이 &quot;최종 경로&quot;와 &quot;다음 히트&quot;라는 옵션이 있는 선택기가 있습니다.

   ![최종 경로 옵션을 강조 표시한 모든 방문 보기. ](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>최종 경로 </p> <p>(기본값) </p> </td> 
   <td colname="col2"> <p>방문자는 경로에 있는 다음 페이지에 "결국" 도달하지만, 다음 이벤트일 필요는 없는 것으로 간주됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>다음 히트 </p> </td> 
   <td colname="col2"> <p>다음 이벤트의 경로에서 다음 페이지에 도착하는 방문자는 카운트됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 폴아웃 설정 {#section_0C7C89D72F0B4D6EB467F278AC979093}

| 설정 | 설명 |
|--- |--- |
| 폴아웃 컨테이너 <ul><li>방문</li><li>방문자</li></ul> | 방문과 방문자 간을 전환하여 개인 경로 지정을 분석할 수 있도록 합니다. 기본값은 방문자입니다. 이러한 설정을 통해 방문 간 개인 수준에서 개인 참여를 이해하거나 분석을 단일 방문으로 제한할 수 있습니다. |

**터치포인트를 마우스 오른쪽 버튼으로 클릭**&#x200B;하면 다음 옵션이 표시됩니다.

| 옵션 | 설명 |
|--- |--- |
| 터치포인트 트렌드 | 터치포인트에 대한 트렌드 데이터를 사전 빌드된 일부 예외 항목 탐지 데이터가 있는 선 그래프로 확인하십시오. |
| 터치포인트 트렌드 (%) | 총 폴아웃 비율의 트렌드를 표시합니다. |
| 모든 터치포인트의 트렌드 표시 (%) | 동일한 차트에서 폴아웃 (&quot;모든 방문&quot;이 포함된 경우 &quot;모든 방문&quot; 제외)의 모든 터치포인트 비율의 트렌드를 표시합니다. |
| 이 터치포인트에서 폴스루 분류 | 사람들이 다음 터치포인트로 계속 이동할 경우 두 터치포인트 (이 터치포인트와 다음 터치포인트) 간 수행한 작업을 봅니다. 이렇게 하면 차원을 보여 주는 자유 형식 테이블이 만들어집니다. 차원과 테이블의 다른 요소를 교체할 수 있습니다. |
| 이 터치포인트에서 폴아웃 분류 | 단계를 통과하지 않은 사람이 선택된 단계 직후 무엇을 했는지 볼 수 있습니다. |
| 터치 포인트에서 필터 만들기 | 선택한 터치포인트에서 새 필터를 만듭니다. |
