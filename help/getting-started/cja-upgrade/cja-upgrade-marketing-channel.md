---
title: Customer Journey Analytics용 마케팅 채널 파생 필드 만들기
description: Customer Journey Analytics용 마케팅 채널 파생 필드 만들기 방법에 대해 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 100%

---

# Customer Journey Analytics용 마케팅 채널 파생 필드 만들기 {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="마케팅 채널 파생 필드 만들기"
>abstract="파생 필드는 데이터 보기 내에서 생성됩니다.<br><br>기본 마케팅 채널 설정 사용 시간은 몇 분 정도이지만 고도로 맞춤화된 마케팅 채널 설정을 만들기 위해서는 몇 시간이 걸릴 수 있습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Analytics 소스 커넥터를 사용하는 경우 마케팅 채널 데이터는 해당 커넥터를 통해 Customer Journey Analytics로 흐릅니다. 마케팅 채널 규칙은 계속 기존의 Adobe Analytics에서 구성되며 일부 규칙은 지원되지 않습니다. 자세한 내용은 [마케팅 채널 차원 사용](/help/use-cases/aa-data/marketing-channels.md)을 참조하십시오.

Experience Platform Web SDK를 사용할 때 Customer Journey Analytics에서 마케팅 채널을 사용하려면 데이터 보기에서 파생 필드를 사용하여 Customer Journey Analytics에 대한 동일한 마케팅 채널과 처리 규칙을 다시 만들 수 있습니다.

1. Customer Journey Analytics에서 마케팅 채널을 추가할 데이터 보기를 선택합니다.

1. 데이터 보기에서 **[!UICONTROL 구성 요소]** 탭을 선택합니다.

1. 왼쪽 레일에서 **[!UICONTROL 파생 필드 만들기]**&#x200B;를 선택합니다.

1. **[!UICONTROL 파생 필드 만들기]** 대화 상자의 드롭다운 메뉴에서 **[!UICONTROL 함수 템플릿]**&#x200B;을 선택합니다.

   ![파생 필드 함수 템플릿 만들기](assets/derived-field-create.png)

1. **[!UICONTROL 마케팅 채널]** 템플릿을 빈 캔버스에 드래그합니다.

1. Adobe Analytics 환경에서 각 채널을 식별하는 데 사용하는 논리와 일치하도록 각 마케팅 채널에 대한 논리를 사용자 정의합니다.

   출력 채널 이름을 수정하거나 논리를 추가하여 조직에 맞는 추가 채널을 식별할 수 있습니다.

1. 오른쪽 열에 마케팅 채널의 이름과 설명을 지정합니다.

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

   새 파생 필드는 데이터 보기의 왼쪽 레일에 있는 스키마 필드의 일부로 파생 필드 > 컨테이너에 추가됩니다.

{{upgrade-final-step}}
