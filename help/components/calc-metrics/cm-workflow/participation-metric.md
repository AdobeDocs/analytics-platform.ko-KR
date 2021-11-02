---
description: 계산된 지표 빌더를 사용하여 누구나 기여도 지표를 만들 수 있습니다.
title: 기여도 지표
source-git-commit: 50c56d718ae7a7f6e3d788b9f755831a7522337c
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---

# 기여도 지표

다음은 간단한 사용 사례입니다. 콘텐츠 소유자는 주문이 포함된 방문에 기여한 (즉, 참여한) 페이지를 확인할 수 있습니다.  방법은 다음과 같습니다.

>[!NOTE]
>
>관리자 도구를 통해 이 작업을 수행해야 했습니다. 관리자 도구에서 기여도 지표를 여전히 활성화할 수 있지만, 사용자 지정 이벤트 1 - 100에 대해서만 가능합니다.

다음은 간단한 사용 사례입니다. 콘텐츠 소유자는 이메일 로그인이 포함된 방문에 기여한 (참여한) 페이지를 확인할 수 있습니다. 방법은 다음과 같습니다.

1. 계산된 지표 빌더에서 새 지표를 만듭니다.
1. 성공 이벤트 &quot;주문&quot;을 정의 캔버스로 드래그합니다.
1. 해당 이벤트의 [기여도 분석 모델](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)을 **[!UICONTROL 설정]** 톱니바퀴 아래에 있는 **[!UICONTROL 기여도]**&#x200B;로 변경합니다. **[!UICONTROL 방문]** 전환 확인을 선택합니다. 정의 모양은 다음과 같아야 합니다.

   ![](assets/participation.png)

1. 지표를 저장합니다.
1. **[!UICONTROL 페이지]** 보고서에서 계산된 지표를 사용합니다.

   ![](assets/participation-pages.png)

1.  (선택 사항) 조직의 다른 사용자와 지표를 공유합니다.
