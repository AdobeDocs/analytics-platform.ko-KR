---
title: 연결 크기 예상
description: 현재 Customer Journey Analytics 사용 현황 보고
translation-type: tm+mt
source-git-commit: 1f496175e504cefed4239aab454744ecae72a6ea
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%

---


# 연결 크기 예상

현재 [!UICONTROL Customer Journey Analytics]에 있는 데이터의 행 수를 알고 있어야 합니다. 이 항목의 목적은 [!UICONTROL Customer Journey Analytics]의 현재 사용 현황을 보고하는 방법을 보여 주기 위한 것입니다.

1. [!UICONTROL Customer Journey Analytics]에서 **[!UICONTROL 연결]** 탭을 클릭합니다.
1. [!UICONTROL 연결 편집] 화면에서 사용/연결 크기를 결정할 연결을 선택합니다.

   ![연결 편집](assets/edit-connection.png)

1. 왼쪽 레일에서 연결의 일부인 데이터 세트를 선택합니다. 이 경우 &quot;B2B 노출 수&quot; 데이터 집합입니다.

   ![데이터 집합](assets/dataset.png)

1. 이름 옆에 있는 파란색(i) 아이콘(정보)을 클릭합니다. 데이터 세트에 3.8k 행/이벤트가 있음을 알 수 있습니다. 또한 정확한 개수의 행을 보려면 미리 보기 테이블 아래 **[!UICONTROL Experience Platform에서 편집]**&#x200B;을 클릭합니다. 이렇게 하면 [!UICONTROL Adobe Experience Platform]의 데이터 세트로 리디렉션됩니다.

   ![AEP 데이터 세트 정보](assets/data-size.png)

1. 이 데이터 세트에 대한 **[!UICONTROL 전체 레코드]**&#x200B;는 3.83k 레코드이며 데이터 크기는 388.59KB입니다.

1. 연결의 다른 데이터 세트에 대해 1-5단계를 반복하여 레코드/행 수를 추가합니다. 마지막으로 집계한 숫자는 연결의 사용 지표가 됩니다. [!UICONTROL Adobe Experience Platform]에서 인제스트할 연결의 데이터 집합 수입니다.

## 인제스트된 행 수 확인

[!UICONTROL Customer Journey Analytics]에서 실제로 수집되는 이벤트 수는 연결 구성 설정에 따라 달라집니다. 또한 잘못된 개인 ID를 선택했거나 데이터 집합의 일부 행에 이 ID를 사용할 수 없는 경우 [!UICONTROL Customer Journey Analytics]은 해당 행을 무시합니다. 인제스트된 이벤트의 실제 행을 확인하려면 다음 단계를 수행하십시오.

1. 연결을 저장하면 필터 없이 동일한 연결의 데이터 보기를 만듭니다.
1. 작업 공간 프로젝트를 만들고 올바른 데이터 보기를 선택합니다. 자유 형식 테이블을 만들고 **[!UICONTROL 연도]** 차원으로 **[!UICONTROL 이벤트]** 지표를 드래그하여 놓습니다. 날짜 선택 달력에서 데이터 범위를 충분히 확장하여 연결에 있는 모든 데이터를 캡슐화합니다. 이렇게 하면 [!UICONTROL Customer Journey Analytics]에 인제스트되는 이벤트 수를 볼 수 있습니다.

   ![작업 공간 프로젝트](assets/event-number.png)

   >[!NOTE]
   >
   >이렇게 하면 이벤트 데이터 세트에서 인제스트되는 이벤트 수를 볼 수 있습니다. 여기에는 프로필 및 조회 유형 데이터 세트가 포함되지 않습니다. 프로필 및 조회 데이터 세트에 대해 &quot;연결 크기 예측&quot;에서 1-3단계를 수행하고 숫자를 추가하여 이 연결에 대한 총 행 수를 가져옵니다.

## 불일치 진단

경우에 따라 연결로 인제스트된 총 이벤트 수가 [!UICONTROL Adobe Experience Platform]의 데이터 세트에 있는 행 수와 다를 수 있습니다. 이 예에서 데이터 세트 &quot;B2B 노출 수&quot;에는 7650개의 행이 있지만 데이터 세트에 [!UICONTROL Adobe Experience Platform]의 3830개의 행이 포함됩니다. 불일치가 발생할 수 있는 몇 가지 이유가 있으며 다음 단계를 수행하여 진단할 수 있습니다.

1. 이 차원을 **[!UICONTROL 플랫폼 데이터 집합 ID]**&#x200B;로 분류하면 크기가 같지만 다른 **[!UICONTROL 플랫폼 데이터 집합 ID]**&#x200B;인 데이터 집합이 2개 있음을 알 수 있습니다. 각 데이터 세트에 3825개의 레코드가 있습니다. 즉, 사람 ID가 없거나 타임스탬프가 누락되어 [!UICONTROL Customer Journey Analytics]이 5개의 레코드를 무시했습니다.

   ![분류](assets/data-size2.png)

1. 또한 [!UICONTROL Adobe Experience Platform]에서 체크 인할 경우 ID가 &quot;5f21c12b732044194bffc1d0&quot;인 데이터 세트가 없으므로 첫 연결이 만들어졌을 때 누군가 이 특정 데이터 세트를 [!UICONTROL Adobe Experience Platform]에서 삭제했습니다. 나중에 [!UICONTROL Customer Journey Analytics]에 다시 추가되었지만 다른 [!UICONTROL 플랫폼 데이터 집합 ID]가 [!UICONTROL Adobe Experience Platform]에 의해 생성되었습니다.

   [!UICONTROL Customer Journey Analytics] 및 [!UICONTROL Adobe Experience Platform]의 데이터 세트 및 연결 삭제](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#implications-of-deleting-data-components)에 대한 [의미를 자세히 읽으십시오.
