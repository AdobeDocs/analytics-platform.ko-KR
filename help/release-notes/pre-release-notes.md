---
title: Customer Journey Analytics 프리릴리스 노트
description: 최신 Customer Journey Analytics 프리릴리스 정보 보기
feature: Release Notes
hide: true
hidefromtoc: true
source-git-commit: 71776f8c2ffa3154d85bd837921011e14ec0ea3f
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 65%

---


# Adobe Customer Journey Analytics 프리릴리스 노트

>[!IMPORTANT]
>
>이 문서는 이번 달 릴리스 정보의 **미리 보기**&#x200B;로 작성되었습니다. 릴리스 항목은 변경될 수 있으며 최종 릴리스에서 추가 또는 제거될 수 있습니다.

이번 릴리스 정보에는 2025년 6월 2일 화요일부터 2025년 7월 15일 수요일까지의 릴리스 기간이 포함됩니다. Adobe Customer Journey Analytics 릴리스는 기능 배포에 대한 보다 확장 가능한 단계별 접근 방식을 고려하는 [연속 제공 모델](releases.md)에서 작동합니다.

Adobe Experience Platform 및 기타 애플리케이션의 릴리스 노트는 다음 설명서를 참조하십시오.

* [Adobe Experience Platform](https://experienceleague.adobe.com/ko/docs/experience-platform/release-notes/pre-release-notes)
* [Adobe Journey Optimizer](https://experienceleague.adobe.com/ko/docs/journey-optimizer/using/whats-new/release-notes?lang=en)
* [Adobe Journey Optimizer B2B](https://experienceleague.adobe.com/ko/docs/journey-optimizer-b2b/user/release-notes?lang=en)
* [페더레이션된 대상자 구성](https://experienceleague.adobe.com/ko/docs/federated-audience-composition/using/release-notes?lang=en)
* [Real-Time CDP Collaboration](https://experienceleague.adobe.com/ko/docs/real-time-cdp-collaboration/using/latest?lang=en)

## 새로운 기능 또는 업데이트된 기능

| 기능 | 설명 | [롤아웃 시작](releases.md) | [일반 가용성](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace 왼쪽 패널이 더 이상 마우스를 올려도 열리거나 닫히지 않음** | Analysis Workspace의 왼쪽 패널은 구성 요소, 패널, 시각화와 같은 항목을 프로젝트에 추가하는 데 사용됩니다. 왼쪽에 있는 아이콘 중 하나에 마우스를 올려 놓으면 왼쪽 패널이 일시적으로 열리는 옵션은 더 이상 제공되지 않습니다. 대신 이들 아이콘 중 하나를 클릭하여 패널을 열어 두고, 같은 아이콘을 클릭하여 패널을 닫으십시오. |  | 2025년 6월 2일 <p>(원래 2025년 5월 29일 릴리스로 계획됨)</p> |
| **Customer Journey Analytics B2B 에디션** | Customer Journey Analytics B2B 에디션은 매출 성장을 촉진하는 실행 가능한 계정 인사이트를 제공하여 B2B 기업이 마케팅, 영업 및 제품 팀을 조정할 수 있도록 지원합니다. 데이터 모델의 중심에 계정을 두면 모든 분석은 계정 여정에 집중됩니다. 개인 및 시간 기반 이벤트 위에 새로운 계층의 엔티티(계정, 기회, 구매 그룹)를 추가하면 B2B 마케팅 및 수익 라이프사이클에 대한 전체적인 그림이 만들어집니다. [자세히 알아보기](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025년 6월 18일 |
| **Report Builder에서 보안 대상 지원** | 새로운 내보내기 대상이 Report Builder 추가 기능에 추가되었습니다. 지원되는 클라우드 스토리지 대상은 다음과 같습니다. <ul><li>Amazon S3 Role ARN</li><li>Google Cloud 플랫폼</li><li>Azure SAS</li><li>Azure RBAC</li></ul> |  | 2025년 6월 18일 |
| **새 미리 보기 환경** | 세그먼트, 계산된 지표 등을 미리 보는 데 사용되는 미리보기 패널에서 이제 도넛 시각화 대신 가로 막대 시각화를 사용합니다. |  | 2025년 6월 18일 |
| **수정된 속성 모델 대화 상자** | 이제 속성 모델 대화 상자에서 컨테이너와 기간을 별도로 정의할 수 있습니다. |  | 2025년 6월 18일 |
| **연결 맵** | 새 [연결 맵 인터페이스](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-connections/create-connection#connection-map)를 사용하여 연결 구성을 시각적으로 표시할 수 있습니다. |  | 2025년 6월 18일 |
| **Analysis Workspace 프로젝트에 댓글 추가 및 보기** | Analysis Workspace에 새롭게 추가된 [댓글 기능](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)을 통해 Analysis Workspace 프로젝트의 컨텍스트 내에서 인사이트를 공유하고 질문할 수 있습니다. 이 기능은 논의 중인 데이터의 컨텍스트 내에서 대화를 유지함으로써 데이터 관련 논의를 간소화할 수 있도록 합니다. 다음과 같은 작업을 수행할 수 있습니다. <ul><li>액세스 권한이 있는 Analysis Workspace 프로젝트에서 댓글 달기</li><li>시각화 내 특정 지점에 대해 댓글을 달거나 프로젝트 전반에 대한 일반적인 댓글 달기</li><li>다른 사용자를 태그하여 댓글에 대한 알림 전송</li><li>기존 댓글 관리 (편집, 고정, 해결 등)</li></ul>Customer Journey Analytics의 관리자는 [조직 수준에서 댓글 기능을 비활성화](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences)할 수 있습니다. 프로젝트 소유자는 [프로젝트 수준에서 댓글 기능을 비활성화](https://experienceleague.adobe.com/ko/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects)할 수 있습니다. |  | 2025년 6월 25일 <p>(원래 2025년 5월 29일 릴리스로 계획됨)</p> |

