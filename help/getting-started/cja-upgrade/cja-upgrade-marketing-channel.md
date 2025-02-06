---
title: Customer Journey Analytics을 위한 마케팅 채널 파생 필드 만들기
description: Customer Journey Analytics을 위한 마케팅 채널 파생 필드를 만드는 방법을 알아봅니다
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 2a74da97-61cb-4c98-949b-3fc428839d70
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 4%

---

# Customer Journey Analytics을 위한 마케팅 채널 파생 필드 만들기 {#create-marketing-channel-derived-field}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channel"
>title="마케팅 채널 파생 필드 만들기"
>abstract="파생된 필드는 데이터 보기 내에 만들어집니다.<br><br>기본 마케팅 채널 설정을 사용하는 데 몇 분 밖에 걸리지 않습니다. 고도로 사용자 지정된 마케팅 채널 설정을 만드는 데 몇 시간이 걸릴 수 있습니다."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>이전의 모든 업그레이드 단계를 완료한 후에만 이 페이지의 단계를 따르십시오. [권장되는 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)를 따르거나, [Adobe Analytics을 사용하여 조직에 대해 동적으로 생성된 업그레이드 단계를 따라 업그레이드 Customer Journey Analytics을](https://gigazelle.github.io/cja-ttv/)할 수 있습니다.
>
>이 페이지의 단계를 완료한 후 권장되는 업그레이드 단계 또는 동적으로 생성된 업그레이드 단계를 계속 수행합니다.

Analytics 소스 커넥터를 사용하면 마케팅 채널 데이터가 해당 커넥터를 통해 Customer Journey Analytics으로 전송됩니다. 마케팅 채널 규칙은 계속 기존의 Adobe Analytics에서 구성되며 일부 규칙은 지원되지 않습니다. 자세한 내용은 [마케팅 채널 차원 사용](/help/use-cases/aa-data/marketing-channels.md)을 참조하세요.

Experience Platform 웹 SDK을 사용할 때 Customer Journey Analytics에서 마케팅 채널을 사용하려면 데이터 보기에서 파생 필드를 사용하여 동일한 마케팅 채널과 Customer Journey Analytics에 대한 처리 규칙을 다시 만들 수 있습니다.

1. Customer Journey Analytics에서 마케팅 채널을 추가할 데이터 보기를 선택합니다.

1. 데이터 보기에서 **[!UICONTROL 구성 요소]** 탭을 선택합니다.

1. 왼쪽 레일에서 **[!UICONTROL 파생 필드 만들기]**&#x200B;를 선택합니다.

1. **[!UICONTROL 파생 필드 만들기]** 대화 상자의 드롭다운 메뉴에서 **[!UICONTROL 함수 템플릿]**&#x200B;을 선택합니다.

   ![파생 필드 함수 템플릿 만들기](assets/derived-field-create.png)

1. **[!UICONTROL 마케팅 채널]** 템플릿을 빈 캔버스로 드래그합니다.

1. 각 마케팅 채널에 대한 논리를 사용자 정의하여 Adobe Analytics 환경에서 각 채널을 식별하는 데 사용하는 논리와 일치시키십시오.

   출력 채널 이름을 수정하거나 로직을 추가하여 조직 고유의 추가 채널을 식별할 수 있습니다.

1. 오른쪽 열에 마케팅 채널의 이름과 설명을 지정합니다.

1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

   새 파생 필드가 데이터 보기의 왼쪽 레일에 있는 스키마 필드의 일부로서 파생 필드 > 컨테이너에 추가됩니다.

1. [권장된 업그레이드 단계](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) 또는 [동적으로 생성된 업그레이드 단계](https://gigazelle.github.io/cja-ttv/)를 계속 따릅니다.
