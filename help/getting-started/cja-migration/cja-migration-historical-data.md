---
title: Customer Journey Analytics으로 마이그레이션할 때 이전 데이터 유지
description: Customer Journey Analytics으로 마이그레이션할 때 이전 데이터를 유지하는 방법 알아보기
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 2d35e49ca9afe37ed53d7c5da5aafd31dd2da632
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# 4단계: 마이그레이션 시 내역 데이터 유지

+++이 섹션을 확장하여 이 페이지의 정보가 대규모 마이그레이션 프로세스에 맞는 위치를 확인합니다. 이전 마이그레이션 단계가 모두 완료되었는지 확인합니다.

이 섹션을 계속하기 전에 먼저 이전 마이그레이션 작업을 모두 완료했는지 확인하십시오.

이 페이지의 정보는 다음 중 4단계를 다룹니다. **마이그레이션**&#x200B;아래 표에 강조 표시된 대로

| 마이그레이션 작업 | 세부 사항 |
|---------|----------|
| **1단계: [마이그레이션 시작](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analytics으로 마이그레이션하는 것의 이점 및 기본 마이그레이션 프로세스에 대해 알아봅니다. |
| **2단계: [마이그레이션 경로 선택](/help/getting-started/cja-migration/cja-migration-path.md)** | Customer Journey Analytics으로 마이그레이션하는 데 다양한 방법을 사용할 수 있습니다. 조직의 현재 Adobe Analytics 환경 및 장기 목표에 따라 조직에 가장 적합한 방법을 선택합니다. |
| **3단계: [Adobe Experience Platform으로 데이터 보내기](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platform으로 데이터를 보내는 프로세스는 2단계에서 선택한 마이그레이션 경로에 따라 다릅니다. |
| <span class="preview">**4단계: 내역 데이터 유지**</span> | <span class="preview">대부분의 조직은 특정 시간 동안 이전 Adobe Analytics 데이터를 유지해야 합니다. 이를 수행하기 위한 다양한 옵션을 사용할 수 있습니다.</span> |
| **5단계: [추가 구현 작업 수행](/help/getting-started/cja-getting-started.md)** | 마이그레이션 프로세스의 이 시점에서 Customer Journey Analytics 환경을 사용하기 전에 다양한 작업을 수행해야 합니다.<p>이러한 추가 작업은 Adobe Analytics에서의 마이그레이션뿐만 아니라 새로운 Customer Journey Analytics 구현에 적용됩니다.</p><p>이러한 작업에는 다음이 포함됩니다.</p><ul><li>다른 데이터를 Experience Platform 상태로 가져오기</li><li>플랫폼 데이터 세트와 Customer Journey Analytics 간 연결 만들기</li><li>데이터 보기 만들기</li><li>보고 API 사용 포팅</li><li>데이터 피드 및 Data Warehouse 계정</li><li>프로젝트 및 구성 요소 마이그레이션</li><li>Planning 사용자 온보딩</li></ul> <p>자세한 내용은 [Customer Journey Analytics 시작](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Adobe Analytics에서 Customer Journey Analytics으로 이동할 때 내역 데이터를 유지하려면 다음 옵션 중 하나를 선택하십시오.

>[!IMPORTANT]
>
>내역 데이터를 유지하는 방법을 선택할 때는 Adobe 계정 담당자에게 문의하여 가격을 결정하십시오.

## Analytics 소스 커넥터 사용

다음을 사용할 수 있습니다. [Analytics 소스 커넥터](/help/data-ingestion/analytics.md) 기록 데이터를 유지합니다. 선택한 마이그레이션 경로에 관계없이(Web SDK를 사용하여 마이그레이션하는 경우에도) Analytics 소스 커넥터를 사용하여 Adobe Analytics 환경의 내역 데이터를 유지할 수 있습니다.

Analytics 소스 커넥터를 사용하면 이전 데이터를 현재 데이터와 별도로 고유한 전용 위치로 가져와서 이전 데이터를 유지할 수 있습니다.

내역 데이터에 액세스해야 하는 한 Analytics 소스 커넥터가 작동하고 있어야 합니다.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## 기존 Adobe Analytics 구현 유지

특정 기간(예: 1년) 동안 새 Customer Journey Analytics 구현과 함께 기존 Adobe Analytics 구현을 유지할 수 있습니다. 이 옵션을 선택할 때는 다음 사항을 고려하십시오.

* Experience Platform에서 데이터를 사용할 수 없습니다.

* Customer Journey Analytics에 충분한 데이터가 있는 경우 Adobe Analytics 구현을 서비스 해제할 계획이어야 합니다.

## 그런 다음 추가 구현 작업을 수행합니다

마이그레이션 프로세스의 이 시점에서 Customer Journey Analytics 환경을 사용하기 전에 다양한 구현 작업을 수행해야 합니다.

이러한 추가 작업은 Adobe Analytics에서의 마이그레이션뿐만 아니라 새로운 Customer Journey Analytics 구현에 적용됩니다.

이러한 작업에는 다음이 포함됩니다.

* 다른 데이터를 Experience Platform 상태로 가져오기

* 플랫폼 데이터 세트와 Customer Journey Analytics 간 연결 만들기

* 데이터 보기 만들기

* 보고 API 사용 포팅

* 데이터 피드 및 Data Warehouse 사용 사례 계정

* 프로젝트 및 구성 요소 마이그레이션

* Planning 사용자 온보딩

자세한 내용은 의 2단계로 시작하십시오. [Customer Journey Analytics 시작](/help/getting-started/cja-getting-started.md).