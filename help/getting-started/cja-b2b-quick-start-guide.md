---
title: Customer Journey Analytics B2B 빠른 시작 안내서
description: Customer Journey Analytics B2B 버전에 대한 빠른 시작 안내서.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B 에디션"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: d7ee16c64761440989f2850d72b8159799bb8479
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 22%

---

# B2B Edition 빠른 시작 안내서

{{draft-b2b}}

Customer Journey Analytics B2B Edition을 구현하려면 먼저 B2B 특정 개념과 기능을 이해해야 합니다. 또한 Customer Journey Analytics 를 구현하려면 기존 작업 과정 기법을 잘 알고 있어야 합니다.

이 문서는 Customer Journey Analytics 구현과 관련된 작업 과정에 중점을 둡니다.

## 사전 요구 사항

Customer Journey Analytics B2B Edition을 구현하려면 다음 전제 조건이 적용됩니다.

* Customer Journey Analytics 에서 관리 작업을 제공하는 데 필요한 [액세스 제어 및 권한이](/help/technotes/access-control.md) 있습니다.
* Customer Journey Analytics B2B Edition 추가 기능 패키지를 구매했습니다.


## 워크플로

| 작업 | 세부 사항 |
| --- | --- |
| **1단계: B2B 데이터를 Experience Platform** | Experience Platform 에서 수행되는 이 단계에는 다음과 같은 몇 가지 하위 단계가 포함됩니다.<ul><li>**1a단계: 데이터 스키마** 준비: Adobe Systems Experience Data Model(XDM) [&#128279;](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ko-KR)을 사용하여 [&#128279;](https://experienceleague.adobe.com/ko/docs/experience-platform/ingestion/home)B2B 데이터를 표준화하고 [B2B 데이터에 대한 스키마](https://experienceleague.adobe.com/ko/docs/experience-platform/rtcdp/schemas/b2b)를 정의합니다.</li><li>**1b단계: 스키마**&#x200B;를 기반으로 데이터 세트 만들기: Platform의 데이터는 계정 데이터, 기회 데이터, 구매 그룹 데이터, 캠페인 데이터, 마케팅 목록 데이터, 이메일 데이터 세트, CRM 데이터 세트, POS 데이터 세트 등과 같은 데이터 세트로 구성됩니다. 각 데이터 세트는 스키마와 데이터 배치로 구성됩니다. [Experience Platform에서 데이터 세트를 생성](https://experienceleague.adobe.com/kr/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=ko-KR)할 수 있습니다.</li><li>**1c단계: Experience Platform**&#x200B;로 데이터 수집: 몇 가지 옵션이 있습니다.</li></ul> |
| **2단계: 플랫폼 데이터 세트와 Customer Journey Analytics 간 연결 만들기** | 연결을 통해 Adobe Experience Platform의 데이터 세트를 작업 영역에 통합할 수 있습니다. Experience Platform 데이터 세트에 대해 보고하려면 먼저 Experience Platform 및 작업 영역의 데이터 세트 간에 연결을 설정해야 합니다. B2B 버전과의 연결을 구성할 때 추가 옵션이 있습니다. <br>[연결 만들기 또는 편집](/help/connections/create-connection.md)을 참조하십시오. |
| **3단계: 데이터 보기 만들기** | 데이터 보기는 필터링된&#x200B;*데이터 보기입니다*. 방문 시간 초과, 기여도 분석 등에 대해 서로 다른 설정을 사용하여 동일한 연결에 대해 서로 다른 데이터 보기를 만들 수 있습니다. 단일 데이터 세트에 대해 여러 데이터 보기를 만들 수 있습니다. B2B Edition이 있는 경우 데이터 보기를 구성할 때 추가 옵션이 있습니다.<br>[데이터 보기 만들기](/help/data-views/create-dataview.md)를 참조하십시오. |
| **4단계: Analysis Workspace에서 크로스 채널 데이터 보고하기** | 연결 및 데이터 보기를 만든 후에는 Analysis Workspace의 강력한 기능과 유연성을 사용하여 가져온 B2B 데이터를 분석합니다.<br>[기본 분석 수행](/help/analysis-workspace/perform-basic-analysis.md) 및 [고급 분석 수행](/help/analysis-workspace/perform-adv-analysis.md)을 참조하십시오. |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->