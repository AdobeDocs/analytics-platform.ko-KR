---
title: CJA 액세스 제어
description: CJA에서 3가지 수준의 액세스 제어 요구 사항에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: ed1885b4dd560bdbce66a1fa2bad1bcd822a3ea3
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 46%

---

# CJA 액세스 제어

CJA(Customer Journey Analytics)은 세 가지 액세스 수준 또는 세 가지 역할의 적용을 받습니다. 제품 관리자 역할, 제품 프로필 관리자 역할 및 사용자 수준 액세스. 이 항목에서는 이러한 역할에 대해 자세히 설명합니다.

## 제품 관리자 역할

제품 관리자는 CJA 내에서 필요한 작업을 완료할 수 있는 권한이 있습니다. 에 제품 관리자로 추가되어야 합니다 **Customer Journey Analytics 제품 프로필** 에서 [Admin Console](https://adminconsole.adobe.com/enterprise/) Customer Journey Analytics > 관리자 탭 > 관리자 추가에서 관리 추가 를 클릭합니다. 제품 관리자에게는 다음 권한이 부여됩니다.

* 연결 또는 데이터 보기 만들기/업데이트/삭제
* 다른 사용자가 만든 프로젝트, 필터, 계산된 지표 또는 필터 업데이트/삭제
* 모든 사용자에게 작업 영역 프로젝트 공유

Customer Journey Analytics에서 제품 관리자가 되는 것만으로는 연결을 생성, 업데이트 또는 삭제할 수 없습니다. Experience Platform 데이터 세트에 대한 연결을 만들려면 Experience Platform 권한도 필요합니다. 특히 다음 권한을 부여하는 **Experience Platform 제품 프로필**&#x200B;의 일부여야 합니다.

* 데이터 모델링: 스키마 보기, 스키마 관리
* 데이터 관리: 데이터 세트 보기, 데이터 세트 관리
* 데이터 수집: 소스 관리
* ID 네임스페이스 보기

Experience Platform 권한에 대한 자세한 내용은 [Adobe Experience Platform의 액세스 제어](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ko)를 참조하십시오.

## 제품 프로필 관리자 역할

이 역할은 제품 관리자와 비슷하지만, 범위가 더 제한됩니다. 제품 프로필은 권한 세트입니다. 예를 들어 제품 프로필 관리자는 제품 프로필의 구성원에게 모든 또는 특정 데이터 보기에 대한 액세스 권한을 제공할 수 있습니다. 보고 도구의 경우 이러한 관리자가 다음 권한을 추가할 수 있습니다.

![admin console 권한](assets/permissions.png)

## 사용자 수준 액세스

Customer Journey Analytics의 제품 관리자가 아닌 사용자(사용자)는 데이터 보기 또는 연결을 만들거나, 편집하거나, 볼 수 없습니다. 사용자는 Admin Console에서 특수 권한이 있는 필터, 프로젝트, 대상 및 계산된 지표를 만들 수 있습니다.

## 작업 공간 프로젝트 큐레이션

Workspace 프로젝트 수준에서 구성 요소(차원, 지표, 세그먼트, 날짜 범위)를 제한하는 방법 및 큐레이션이 데이터 보기에 연결된 방법에 대한 자세한 내용은 [프로젝트 조정](/help/analysis-workspace/curate-share/curate.md).

## 개별 지표 또는 차원에 대한 액세스 권한 부여

Customer Journey Analytics에서는 기존의 Adobe Analytics에서와 같이 개별 지표 또는 차원을 거부하거나 허용할 수 없습니다. 지표와 차원은 [데이터 보기](/help/data-views/data-views.md)에서 변경할 수 있으므로 보고도 소급 변경하는 CJA의 변경으로부터 영향을 받습니다.

