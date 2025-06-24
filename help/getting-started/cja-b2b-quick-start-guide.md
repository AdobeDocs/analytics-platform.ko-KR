---
title: Customer Journey Analytics B2B 빠른 시작 안내서
description: Customer Journey Analytics B2B 에디션에 대한 빠른 시작 안내서.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B 에디션"
exl-id: ff8d419e-5cc6-4e1b-8cf8-9dbaa8054179
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: ht
source-wordcount: '396'
ht-degree: 100%

---


# B2B 에디션 빠른 시작 안내서

Customer Journey Analytics B2B 에디션을 구현하려면 먼저 B2B 특정 개념 및 기능을 이해해야 합니다. 또한 Customer Journey Analytics를 구현하기 위한 기존 워크플로에 익숙해야 합니다.

이 문서는 Customer Journey Analytics 구현에 특화된 워크플로에 중점을 둡니다.

## 사전 요구 사항

Customer Journey Analytics B2B 에디션을 구현하려면 다음 전제 조건이 적용됩니다.

* Customer Journey Analytics에서 관리 작업을 제공하기 위해 필요한 [액세스 제어 및 권한](/help/technotes/access-control.md)을 보유하고 있습니다.
* Customer Journey Analytics B2B 에디션 추가 패키지를 구매하셨습니다.


## 워크플로

| 작업 | 세부 사항 |
| --- | --- |
| **1단계: Experience Platform에 B2B 데이터 수집** | Experience Platform에서 수행되는 이 단계에는 다음과 같은 몇 가지 하위 단계가 포함됩니다.<ul><li>**1a단계: 데이터 스키마 준비**: [Adobe 경험 데이터 모델(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ko)을 사용하여 B2B 데이터를 표준화하고 B2B 데이터에 대한 [스키마 정의](https://experienceleague.adobe.com/ko/docs/experience-platform/rtcdp/schemas/b2b)를 합니다.</li><li>**1b단계: 스키마를 기반으로 데이터 세트 만들기**: 플랫폼의 데이터는 계정 데이터, 기회 데이터, 구매 그룹 데이터, 캠페인 데이터, 마케팅 목록 데이터, 이메일 데이터 세트, CRM 데이터 세트, POS 데이터 세트 등의 데이터 세트로 구성됩니다. 각 데이터 세트는 스키마와 데이터 배치로 구성됩니다. [Experience Platform에서 데이터 세트를 생성](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=ko)할 수 있습니다.</li><li>**1c단계: 데이터를 Experience Platform에 수집**: [몇 가지 옵션](https://experienceleague.adobe.com/ko/docs/experience-platform/ingestion/home)이 있습니다.</li></ul> |
| **2단계: 플랫폼 데이터 세트와 Customer Journey Analytics 간 연결 만들기** | 연결을 통해 Adobe Experience Platform의 데이터 세트를 Workspace에 통합할 수 있습니다. Experience Platform 데이터 세트에 대해 보고하려면 먼저 Experience Platform과 Workspace의 데이터 세트 간에 연결을 설정해야 합니다. B2B 에디션으로 연결을 구성할 때 추가 옵션이 제공됩니다. <br>[연결 만들기 또는 편집](/help/connections/create-connection.md)을 참조하십시오. |
| **3단계: 데이터 보기 만들기** | 데이터 보기는 데이터의 *필터링된* 보기입니다. 방문 제한 시간, 속성 등에 대한 서로 다른 설정을 사용하여 동일한 연결에 대해 다른 데이터 보기를 만들 수 있습니다. 단일 데이터 세트에 대해 여러 데이터 보기를 만들 수 있습니다. B2B 에디션을 사용하는 경우 데이터 보기를 구성하면 추가 옵션이 제공됩니다.<br>[데이터 보기 만들기](/help/data-views/create-dataview.md)를 참조하십시오. |
| **4단계: Analysis Workspace에서 크로스 채널 데이터 보고하기** | 연결 및 데이터 보기를 만든 후 Analysis Workspace의 강력한 기능과 유연성을 사용하여 가져온 B2B 데이터를 분석합니다.<br>[기본 분석 수행](/help/analysis-workspace/perform-basic-analysis.md) 및 [고급 분석 수행](/help/analysis-workspace/perform-adv-analysis.md)을 참조하십시오. |

<!--

## Use Case

The [B2B Use Case ](../data-ingestion/data-ingestion.md) document provides an example use case on how to implement Customer  Journey Analytics B2B Edition.

-->