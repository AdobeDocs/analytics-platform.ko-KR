---
description: Customer Journey Analytics의 연속 기능 릴리스 전략에 대해 설명합니다.
title: Customer Journey Analytics 기능 릴리스 전략
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
feature: Release Notes
source-git-commit: 39e4c17336d3648cbf20cace535668d14510186f
workflow-type: ht
source-wordcount: '397'
ht-degree: 100%

---

# Customer Journey Analytics 기능 릴리스 전략

Customer Journey Analytics 릴리스는 기능 배포에 대한 확장 가능한 단계별 접근 방식을 고려하는 연속 게재 모델에서 작동합니다.

## 출시 전략

[!UICONTROL Analysis Workspace]는 기능 플래그(“토글”이라고도 함)를 사용하여 새로운 기능의 가시성을 제어하므로 전체 릴리스 전에 통제된 크기 테스트를 수행할 수 있습니다. 이 릴리스 전략에는 다음 단계가 포함됩니다.

* **제한된 테스트**: 단계적인 릴리스는 내부 Adobe 사용자에 의한 테스트부터 시작됩니다. 그런 다음 소수의 고객 계정 그룹에 공개되어 기능이 고객의 요구와 기대를 충족하는지 확인합니다.

* **롤아웃 시작**: 단계적인 릴리스 롤아웃은 제한된 테스트 단계부터 시작됩니다. 그런 다음 고객들에 대한 릴리스의 가용성은 몇 개월 동안 0%에서 100%로 확장됩니다. 단계적 롤아웃은 Experience Cloud 조직 수준에서 발생하므로 조직에서 권한이 있는 모든 사용자는 동일한 경험을 합니다.

* **GA (일반 배포)**: 권한이 있는 Experience Cloud 조직의 100%가 이 기능을 사용할 수 있으며 기능 릴리스가 완료되었습니다.

각 기능 릴리스 시 RTP에서 GA로의 타임라인은 달라질 수 있습니다. 릴리스 시작 (RTP) 2개월 이내에 기능이 GA 상태가 되도록 릴리스를 짧게 유지하는 것이 목표입니다.

## 기능 플래그

기능 플래그는 릴리스 중 새로운 기능의 가시성을 제어하는 데 사용됩니다. Adobe는 릴리스 단계에서 최적의 경험을 위해 귀사의 방화벽을 통해 `app.launchdarkly.com`을 허용할 것을 권장합니다. 이들 플래그는 기능이 모든 사용자에게 릴리스된 후 제거됩니다. 자세한 내용은 [Customer Journey Analytics에서 사용되는 도메인](../technotes/domains.md)을 참조하십시오.

**도움말 > Workspace 정보 > 활성 기능 플래그**&#x200B;에서 언제든지 활성 기능 플래그를 볼 수 있습니다.

## 이점

단계별 릴리스를 통해 Adobe는 소프트웨어 배포 프로세스를 보다 효과적으로 확장할 수 있으며 GA 전에 기능을 완전히 확정할 수 있습니다. 또한 고정된 월별 릴리스 기간에 얽매이지 않고 기능을 개발하자마자 출시할 수 있습니다.

## FAQ

| 질문 | 답변 |
| --- | --- |
| 기능에 대한 조기 액세스를 요청할 수 있습니까? | 아니요. 조기 액세스는 허용되지 않습니다.<br>초기 Analytics 개념을 테스트하려는 경우 [Adobe Analytics Labs](https://experienceleague.adobe.com/kr/docs/analytics/analyze/labs.html?lang=ko-KR)를 사용하여 업계를 선도하는 혁신적인 기술에 대한 피드백을 제공할 것을 권장합니다. |
| 이 릴리스 전략은 기능 액세스에 영향을 줍니까? | 아니요. 기능이 GA에 도달하면 Analytics 패키지에 포함된 경우 이 기능에 액세스할 수 있습니다. |
