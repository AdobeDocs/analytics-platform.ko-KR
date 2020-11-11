---
title: 연결 관리
description: Platform 데이터 세트에 대한 연결을 관리하는 방법을 설명합니다.
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 22%

---


# 연결 관리

하나 이상의 연결을 만들었으면 [!UICONTROL Connections] Manager에서 관리할 수 있습니다. You can

* 연결을 삭제할 수 있습니다.
* 연결 이름을 변경할 수 있습니다.
* 연결에서 데이터 보기를 만들 수 있습니다.
* 데이터 스트리밍을 시작 및 중지할 수 있습니다.

![연결 관리자](assets/connections-manager.png)

1. **[!UICONTROL 연결]** 탭을 클릭합니다.

2. 편집하거나 관리할 연결을 선택합니다.

3. 다음 작업 중 하나를 완료합니다.

   | 작업 | 설명 |
   |---|---|
   | [!UICONTROL 삭제] | 데이터 세트가 [!DNL Adobe Experience Platform]에 있으므로 연결을 삭제해도 데이터 세트가 삭제되지 않습니다. 아래의 &quot;연결 삭제&quot;를 참조하십시오. |
   | [!UICONTROL 이름 변경] | 연결을 설명하는 이름으로 연결 이름을 바꿀 수 있습니다. |
   | [!UICONTROL 데이터 보기 만들기] | 이 링크를 클릭하면 [데이터 보기 빌더](/help/data-views/create-dataview.md)로 이동합니다. |
   | [!UICONTROL 데이터 스트리밍 시작 또는 중지] | &quot;스트리밍&quot;은 연결에서 데이터 세트에 새 배치가 추가되는 경우 보고를 위해 이 새 데이터를 [!UICONTROL Customer Journey Analytics]로 가져옵니다. |

## 연결 삭제

| 만약.. | 이 경우 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics]에서 연결을 삭제하시겠습니까? | 다음과 같은 오류 메시지가 표시됩니다.<ul><li>삭제된 연결에 대해 만들어진 모든 데이터 보기는 더 이상 작동하지 않습니다.</li><li> 마찬가지로, 삭제된 연결의 데이터 보기에 의존하는 모든 Workspace 프로젝트의 작업이 중단됩니다.</li></ul> |
| [!UICONTROL Adobe Experience Platform]에서 데이터 세트를 삭제하시겠습니까? | AEP에서 데이터 세트를 삭제하면 해당 데이터 세트에서 해당 데이터 세트를 포함하는 모든 연결로의 데이터 흐름이 중지됩니다. 해당 데이터 집합의 데이터는 관련 CJA 연결에서 자동으로 삭제되지 않습니다. |
| [!UICONTROL Customer Journey Analytics]에서 데이터 세트를 삭제하시겠습니까? | 현재 저장된 연결 내에서는 데이터 세트를 삭제할 수 없습니다. 전체 연결을 삭제하고 다시 시작해야 합니다. 그러나 [!UICONTROL Adobe Experience Platform]에서 데이터 세트를 삭제할 수 있습니다. |
| 데이터 세트에서 일괄 처리를 삭제하시겠습니까([!UICONTROL Adobe Experience Platform])? | [!UICONTROL Adobe Experience Platform] 데이터 세트에서 일괄 처리를 삭제하면 해당 특정 일괄 처리를 포함하는 [!UICONTROL Customer Journey Analytics] 연결에서 동일한 일괄 처리가 제거됩니다. [!UICONTROL 고객 여정 ] 분석은  [!UICONTROL Adobe Experience Platform]에서 삭제된 배치에 대해 알립니다. |
| 인제스트하는 동안 **묶음을 [!UICONTROL Customer Journey Analytics]에 삭제하시겠습니까?** | 데이터 세트에 하나의 일괄 처리만 있을 경우 해당 묶음의 데이터 또는 부분 데이터는 [!UICONTROL Customer Journey Analytics]에 표시되지 않습니다. 섭취 되돌아갑니다. 예를 들어 데이터 세트에 5개의 배치가 있고 데이터 세트를 삭제할 때 이미 인제스트된 3개의 배치인 경우 해당 3개의 배치의 데이터가 [!UICONTROL Customer Journey Analytics]에 나타납니다. |
