---
title: Customer Journey Analytics로 업그레이드할 때 내역 데이터 보관
description: Customer Journey Analytics로 업그레이드할 때 내역 데이터 보관 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 73%

---

# 4단계: 업그레이드 시 내역 데이터 보관

+++이 섹션을 확장하여 이 페이지의 정보가 더 큰 업그레이드 프로세스에서 어떻게 적용되는지 참조하십시오. 이전 업그레이드 단계가 모두 완료되었는지 확인합니다.

이 섹션을 계속 진행하기 전에 먼저 이전 업그레이드 작업을 모두 완료했는지 확인합니다.

이 페이지의 정보는 아래 테이블에 강조 표시된 대로 업그레이드 프로세스의 4단계에 대한 내용을 다룹니다.

| 업그레이드 작업 | 세부 사항 |
|---------|----------|
| **1단계: [업그레이드 시작](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Customer Journey Analytics로 업그레이드하는 이점과 기본적인 업그레이드 프로세스에 대해 알아봅니다. |
| **2단계: [업그레이드 경로 선택](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Customer Journey Analytics으로 업그레이드할 수 있는 방법은 다양합니다. 조직의 현재 Adobe Analytics 환경과 장기적인 목표에 따라 조직에 가장 적합한 방법을 선택합니다. |
| **3단계: [Adobe Experience Platform으로 데이터 보내기](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Adobe Experience Platform으로 데이터를 전송하는 프로세스는 2단계에서 선택한 업그레이드 경로에 따라 다릅니다. |
| <span class="preview">**4단계: 내역 데이터 보관**</span> | <span class="preview">대부분의 조직에서는 특정 기간 동안 Adobe Analytics 내역 데이터를 보관해야 합니다. 이를 달성하기 위해 다양한 옵션을 사용할 수 있습니다.</span> |
| **5단계: [추가 구현 작업 수행](/help/getting-started/cja-getting-started.md)** | 업그레이드 프로세스의 이 시점에서는 Customer Journey Analytics 환경을 사용할 준비가 되기 전에 다양한 작업을 수행해야 합니다.<p>이러한 추가 작업은 Adobe Analytics의 업그레이드뿐 아니라 새로운 Customer Journey Analytics 구현에도 적용됩니다.</p><p>이러한 작업에는 다음이 포함됩니다.</p><ul><li>다른 데이터를 Experience Platform으로 가져오기</li><li>Platform 데이터 세트와 Customer Journey Analytics 간 연결 만들기</li><li>데이터 보기 만들기</li><li>보고 API 사용량 이식</li><li>데이터 피드 및 Data Warehouse 확인</li><li>프로젝트 및 구성 요소 마이그레이션</li><li>사용자 온보딩 계획 수립</li></ul> <p>자세한 내용은 [Customer Journey Analytics 시작하기](/help/getting-started/cja-getting-started.md)를 참조하십시오. |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>이 페이지의 정보는 다음과 같은 보다 포괄적인 업그레이드 정보로 대체됩니다. <ul><li>**권장된 업그레이드 단계**<p>자세한 내용은 [Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)를 참조하십시오.</p></li><li>**Customer Journey Analytics 업그레이드 안내서**<p>조직 및 고유한 환경에 맞게 조정된 업그레이드 단계를 동적으로 생성하는 새로운 업그레이드 가이드를 사용할 수 있습니다.</p><p>Customer Journey Analytics에서 가이드에 액세스하려면 **[!UICONTROL Workspace]** 탭을 선택한 다음 왼쪽 패널에서 **[!UICONTROL Customer Journey Analytics으로 업그레이드]**&#x200B;를 선택합니다. 화면에 표시되는 안내를 따릅니다.</p></li></ul>

Adobe Analytics에서 Customer Journey Analytics로 이동할 때 내역 데이터를 보관하려면 다음 옵션 중 하나를 선택합니다.

>[!IMPORTANT]
>
>내역 데이터를 보관하는 방법을 선택할 때는 Adobe 계정 담당자에게 문의하여 가격을 확인하십시오.

## Analytics 소스 커넥터 사용

[Analytics 원본 커넥터](/help/data-ingestion/analytics.md)를 사용하여 이전 데이터를 유지할 수 있습니다. 선택한 업그레이드 경로에 관계없이(웹 SDK을 사용하여 업그레이드한 경우에도) Analytics 소스 커넥터를 사용하여 Adobe Analytics 환경의 내역 데이터를 유지할 수 있습니다.

Analytics 소스 커넥터를 사용하면 이전 데이터를 현재 데이터와 별도로 전용 위치로 가져와서 이전 데이터를 유지할 수 있습니다.

내역 데이터에 액세스해야 하는 한 Analytics 소스 커넥터가 작동하고 있어야 합니다.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## 기존 Adobe Analytics 구현 유지

기존 Adobe Analytics 구현을 새로운 Customer Journey Analytics 구현과 함께 특정 기간(예: 1년) 동안 유지할 수 있습니다. 이 옵션을 선택할 때 다음 사항을 고려하십시오.

* Experience Platform에서는 데이터를 사용할 수 없습니다.

* Customer Journey Analytics에서 충분한 데이터를 수집한 후에는 Adobe Analytics 구현을 중단 계획을 세워야 합니다.

## 이후 추가 구현 작업 수행

업그레이드 프로세스의 이 시점에서는 Customer Journey Analytics 환경을 사용할 준비가 되기 전에 다양한 구현 작업을 수행해야 합니다.

이러한 추가 작업은 Adobe Analytics의 업그레이드뿐 아니라 새로운 Customer Journey Analytics 구현에도 적용됩니다.

이러한 작업에는 다음이 포함됩니다.

* 다른 데이터를 Experience Platform으로 가져오기

* Platform 데이터 세트와 Customer Journey Analytics 간 연결 만들기

* 데이터 보기 만들기

* 보고 API 사용량 이식

* 데이터 피드 및 Data Warehouse 사용 사례 확인

* 프로젝트 및 구성 요소 마이그레이션

* 사용자 온보딩 계획 수립

자세한 내용은 [Customer Journey Analytics 시작하기](/help/getting-started/cja-getting-started.md)의 2단계부터 확인하십시오.
