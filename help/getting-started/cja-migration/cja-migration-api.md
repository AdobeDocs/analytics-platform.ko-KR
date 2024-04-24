---
title: Customer Journey Analytics으로 마이그레이션할 때 Reporting API 사용을 포트합니다.
description: API 사용을 Adobe Analytics에서 Customer Journey Analytics으로 포팅하는 방법에 대해 알아봅니다.
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d26a6956-870f-44f2-9c32-f732bff17737
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# 7단계: Customer Journey Analytics으로 마이그레이션할 때 Reporting API 사용을 포트합니다.

+++이 섹션을 확장하여 이 페이지의 정보가 대규모 마이그레이션 프로세스에 맞는 위치를 확인합니다. 이전 마이그레이션 단계가 모두 완료되었는지 확인합니다.

이 섹션을 계속하기 전에 먼저 이전 마이그레이션 작업을 모두 완료했는지 확인하십시오.

이 페이지의 정보는 아래 표에 강조 표시된 대로 7단계를 다룹니다.

| 마이그레이션 작업 | 세부 사항 |
|---------|----------|
| **1단계: [마이그레이션 시작](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analytics으로 마이그레이션하는 것의 이점 및 기본 마이그레이션 프로세스에 대해 알아봅니다. |
| **2단계: [마이그레이션 경로 선택](/help/getting-started/cja-migration/cja-migration-path.md)** | Customer Journey Analytics으로 마이그레이션하는 데 다양한 방법을 사용할 수 있습니다. 조직의 현재 Adobe Analytics 환경 및 장기 목표에 따라 조직에 가장 적합한 방법을 선택합니다. |
| **3단계: [Adobe Experience Platform으로 데이터 보내기](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platform으로 데이터를 보내는 프로세스는 2단계에서 선택한 마이그레이션 경로에 따라 다릅니다. |
| **4단계: [이전 데이터 유지](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | 대부분의 조직은 특정 시간 동안 이전 Adobe Analytics 데이터를 유지해야 합니다. 이를 수행하기 위한 다양한 옵션을 사용할 수 있습니다. |
| **5단계: [추가 구현 작업 수행](/help/getting-started/cja-getting-started.md)** | 마이그레이션 프로세스의 이 시점에서 Customer Journey Analytics 환경을 사용하기 전에 다양한 작업을 수행해야 합니다.<p>이러한 추가 작업은 Adobe Analytics에서의 마이그레이션뿐만 아니라 새로운 Customer Journey Analytics 구현에 적용됩니다.</p><p>이러한 작업에는 다음이 포함됩니다.</p><ul><li>다른 데이터를 Experience Platform 상태로 가져오기</li><li>플랫폼 데이터 세트와 Customer Journey Analytics 간 연결 만들기</li><li>데이터 보기 만들기</li><li>보고 API 사용 포팅</li><li>데이터 피드 및 Data Warehouse 계정</li><li>프로젝트 및 구성 요소 마이그레이션</li><li>Planning 사용자 온보딩</li></ul> <p>자세한 내용은 [Customer Journey Analytics 시작](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Adobe Analytics 보고 API의 보고 API 사용을 Customer Journey Analytics 보고 API로 포팅합니다.

Customer Journey Analytics 보고 API는 형식은 동일하지만 다른 하위 도메인을 사용합니다.

Adobe Analytics 및 Customer Journey Analytics에 대한 엔드포인트 안내서 를 참조하십시오.

대부분의 API 호출은 Adobe Analytics에서 Customer Journey Analytics으로 쉽게 변환할 수 있습니다.

Customer Journey Analytics API를 해당 API 프로젝트에 추가합니다.

API 호출 헤더에 IMS 조직 ID를 추가합니다.

cja.adobe.io와 analytics.adobe.io 비교

추가 헤더

## 다음으로, 데이터 피드 및 Data Warehouse 바꾸기

Customer Journey Analytics에서 사용할 수 있는 내보내기 옵션을 사용하여 [데이터 피드 및 Data Warehouse 기능 바꾸기](/help/getting-started/cja-migration/cja-migration-export-options.md) Adobe Analytics에서 를 사용 중이었습니다.
