---
title: Web SDK 확장 기능용 로더 태그 구현
description: Web SDK 확장 기능용 로더 태그 구현 방법에 대해 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 471ecd60-6e1e-4889-93bd-c654b35d40dc
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '283'
ht-degree: 100%

---

# Web SDK 확장 기능용 로더 태그 구현 {#upgrade-tag-loader}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tag-loader"
>title="사이트에 로더 태그 구현"
>abstract="웹 사이트 개발 팀과 협력하여 사이트의 모든 페이지에 로더 태그를 설치합니다.<br><br>이 작업의 완료 시간은 코드 배포를 위해 협력하는 엔지니어링 팀의 응답 시간에 따라 크게 달라집니다. 적응력이 뛰어난 엔지니어링 팀을 보유한 일부 조직은 며칠 만에 이 단계를 완료할 수 있으며, 업무가 많이 쌓인 엔지니어링 팀은 한 달 이상 걸릴 수 있습니다."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

추적하려는 웹 사이트에 태그를 설치해야 하며, 이는 웹 사이트 템플릿의 헤더 태그에 코드를 넣는 것을 의미합니다.

다음 프로세스는 태그를 참조하는 코드를 가져오는 방법을 설명합니다. 추가 정보는 Experience Platform 설명서의 [태그 및 이벤트 전달 구현 가이드](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/get-started/implementation-guides)를 참조하십시오.

태그를 참조하는 코드를 가져오는 경우:

1. Adobe ID 자격 증명을 사용하여 experience.adobe.com에 로그인합니다.

1. Adobe Experience Platform에서 **[!UICONTROL 데이터 수집]** > **[!UICONTROL 태그]**&#x200B;로 이동합니다.

1. **[!UICONTROL 태그 속성]** 페이지에서 속성 목록에서 새로 만든 태그를 선택하여 엽니다.

1. 왼쪽 레일에서 **[!UICONTROL 환경]**&#x200B;을 선택합니다.

1. 환경 목록에서 올바른 설치(상자) 버튼을 선택합니다.

   [!UICONTROL 웹 설치 지침] 대화 상자에서 다음과 유사한 스크립트 코드 옆에 있는 복사 버튼을 선택합니다.

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
   ```

   ![환경](assets/environment.png)

1. **[!UICONTROL 닫기]**&#x200B;를 선택합니다.

   개발 환경의 코드 대신 Adobe Experience Platform Web SDK 배포 과정을 기준으로 다른 환경(스테이징, 프로덕션)을 선택할 수 있습니다.

   자세한 내용은 [환경](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=ko&)을 참조하십시오.

{{upgrade-final-step}}
