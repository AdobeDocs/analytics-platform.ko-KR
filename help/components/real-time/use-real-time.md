---
description: Analysis Workspace에서 실시간 보고를 사용하는 방법을 이해합니다.
title: 실시간 보고 사용
feature: Real-time Reporting
role: User
exl-id: 6e7dba80-5fb9-4554-b989-85eb54a4bd6a
autotag-review: '2026-05-19T08:47:15.932Z'
TQID: 'https://experienceleague.adobe.com/t20pdV4qS-FIBGrxOXAD5xAD58f4gtN74uheJ94sK4s'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: d1779026-aeed-458e-a1c7-839d4acac922
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 12%

---

# 실시간 보고 사용 {#use-real-time-reporting}

>[!CONTEXTUALHELP]
>id="workspace_panel_realtime_refresh"
>title="실시간 새로 고침"
>abstract="이 패널에서 데이터와 시각화를 실시간으로 새로 고칠 수 있습니다."

실시간 보고를 사용하려면 Workspace 프로젝트에서 **[!UICONTROL 실시간 새로 고침]** 토글을 사용하도록 설정합니다.

* [빈 패널](/help/analysis-workspace/c-panels/blank-panel.md)
* [자유 형식](/help/analysis-workspace/c-panels/freeform-panel.md)
* [속성](/help/analysis-workspace/c-panels/attribution.md)
* [다음 또는 이전 항목](/help/analysis-workspace/c-panels/next-previous.md)

가장 최근 데이터 새로 고침의 타임스탬프가 포함된 메시지가 표시됩니다. 예: [!UICONTROL &#x200B; *오후 7시:55에 마지막으로 새로 고침*].

드롭다운 메뉴에서 보고할 실시간 기간을 선택합니다. 사용 가능한 옵션은 다음과 같습니다.

* [!UICONTROL 최근 15분]
* [!UICONTROL 지난 30분]
* [!UICONTROL 지난 시간]
* [!UICONTROL 지난 8시간]
* [!UICONTROL 지난 24시간]

이제 실시간 새로 고침이 활성화된 패널이 있는 브라우저 탭이 활성화되는 동안 패널의 모든 시각화가 매 분마다 최대 30분 동안 업데이트됩니다.

예를 들어, 시간이 **[!UICONTROL *06:26pm*]**&#x200B;에서 **[!UICONTROL *06:27 pm *]**(으)로 이동할 때&#x200B;**[!UICONTROL &#x200B;총 수익/시간&#x200B;]**&#x200B;막대 시각화 및&#x200B;**[!UICONTROL &#x200B;총 수익/시간&#x200B;]**&#x200B;자유 형식 테이블을 새로 고치는&#x200B;**[!UICONTROL &#x200B;실시간 보고 패널&#x200B;]**&#x200B;의 스냅숏을 아래를 참조하십시오.

![실시간 새로 고침](assets/real-time-refresh.gif)

30분 후 또는 브라우저 탭이 비활성화되는 즉시 **[!UICONTROL 실시간 새로 고침]** 토글이 자동으로 비활성화되고 실시간 업데이트가 중지됩니다.

실시간 새로 고침 토글을 사용하지 않도록 설정하면 패널(및 그 안의 모든 시각화)이 [Customer Journey Analytics의 표준 보고 데이터 및 기능 사용](real-time.md#how-it-works)(으)로 돌아갑니다.
