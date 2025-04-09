---
title: Customer Journey Analytics B2B 빠른 시작 안내서
description: Customer Journey Analytics B2B edition에 대한 빠른 시작 안내서입니다.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: true
hidefromtoc: true
badgePremium: label="B2B edition"
source-git-commit: 0e4e52cfd42db321c4a7a18a9b1473a67f87e785
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 22%

---

# B2B edition 빠른 시작 안내서

{{draft-b2b}}

Customer Journey Analytics B2B edition을 구현하려면 먼저 B2B 관련 개념과 기능을 이해해야 합니다. 또한 Customer Journey Analytics을 구현하는 기존 워크플로에 익숙해야 합니다.

이 문서는 Customer Journey Analytics 구현과 관련된 워크플로에 중점을 둡니다.

## 사전 요구 사항

Customer Journey Analytics B2B edition을 구현하려면 다음 전제 조건이 적용됩니다.

* Customer Journey Analytics에서 관리 작업을 제공하는 데 필요한 [액세스 제어 및 권한](/help/technotes/access-control.md)이 있습니다.
* Customer Journey Analytics B2B edition 추가 기능 패키지를 구매했습니다.


## 워크플로

| 작업 | 세부 사항 |
| --- | --- |
| **1단계: B2B 데이터를 Experience Platform에 가져오기** | Experience Platform에서 수행되는 이 단계에는 다음과 같은 몇 가지 하위 단계가 포함됩니다.<ul><li>**1a 단계: 데이터 스키마 준비**: [Adobe XDM(Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ko-KR)을 사용하여 B2B 데이터를 표준화하고 B2B 데이터에 대한 [스키마를 정의](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b)할 수 있습니다.</li><li>**1b 단계: 스키마를 기반으로 데이터 세트 만들기**: 플랫폼의 데이터는 계정 데이터, 영업 기회 데이터, 구매 그룹 데이터, 캠페인 데이터, 마케팅 목록 데이터, 이메일 데이터 세트, CRM 데이터 세트, POS 데이터 세트 등과 같은 데이터 세트로 구성됩니다. 각 데이터 세트는 스키마와 데이터 배치로 구성됩니다. [Experience Platform에서 데이터 세트를 생성](https://experienceleague.adobe.com/kr/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=ko-KR)할 수 있습니다.</li><li>**1c 단계: Experience Platform에 데이터 수집**: [몇 가지 옵션이 있습니다](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home).</li></ul> |
| **2단계: 플랫폼 데이터 세트와 Customer Journey Analytics 간 연결 만들기** | 연결을 통해 Adobe Experience Platform의 데이터 세트를 작업 영역에 통합할 수 있습니다. Experience Platform 데이터 세트에 대해 보고하려면 먼저 Experience Platform과 Workspace의 데이터 세트 간에 연결을 설정해야 합니다. B2B edition과의 연결을 구성할 때 추가 옵션이 제공됩니다. <br>[연결 만들기 또는 편집](/help/connections/create-connection.md)을 참조하십시오. |
| **3단계: 데이터 보기 만들기** | 데이터 보기는 데이터의 *필터링된* 보기입니다. 방문 시간 초과, 속성 등에 대한 서로 다른 설정을 사용하여 동일한 연결에 대해 서로 다른 데이터 보기를 만들 수 있습니다. 단일 데이터 세트에 대해 여러 데이터 보기를 만들 수 있습니다. B2B edition이 있을 때 데이터 보기를 구성할 때 추가 옵션이 있습니다.<br>[데이터 보기 만들기](/help/data-views/create-dataview.md)를 참조하십시오. |
| **4단계: Analysis Workspace에서 크로스 채널 데이터 보고하기** | 연결 및 데이터 보기를 만든 후 Analysis Workspace의 강력한 기능과 유연성을 사용하여 가져온 B2B 데이터를 분석합니다.<br>[기본 분석 수행](/help/analysis-workspace/perform-basic-analysis.md) 및 [고급 분석 수행](/help/analysis-workspace/perform-adv-analysis.md)을 참조하십시오. |

## 사용 사례

[B2B 사용 사례](../data-ingestion/data-ingestion.md) 문서에서는 Customer Journey Analytics B2B edition 구현 방법에 대한 사용 사례의 예를 제공합니다.
