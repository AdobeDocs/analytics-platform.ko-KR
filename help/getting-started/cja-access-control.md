---
title: CJA 액세스 제어
description: 연결 생성, 데이터 세트 추가, 데이터 보기 생성 등에 대한 액세스 제어 요구 사항에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: c80c10e1e4887bfe7fdc3b59d0dfe415b1b0d5eb
workflow-type: ht
source-wordcount: '241'
ht-degree: 100%

---

# CJA 액세스 제어

Customer Journey Analytics에서 작업에 액세스하고 작업을 수행하려면 [Admin Console](https://adminconsole.adobe.com/enterprise/)에서 **Customer Journey Analytics 제품 프로필**&#x200B;에 관리자로 추가되어 있어야 합니다. 제품 관리자에게는 다음 권한이 부여됩니다.

* 연결 또는 데이터 보기 만들기/업데이트/삭제
* 다른 사용자가 만든 프로젝트, 필터, 계산된 지표 또는 필터 업데이트/삭제
* 모든 사용자에게 작업 영역 프로젝트 공유

## 필요한 Adobe Experience Platform 권한

Customer Journey Analytics에서 제품 관리자가 되는 것만으로는 연결을 생성, 업데이트 또는 삭제할 수 없습니다. Experience Platform 데이터 세트에 대한 연결을 만들려면 Experience Platform 권한도 필요합니다. 특히 다음 권한을 부여하는 **Experience Platform 제품 프로필**&#x200B;의 일부여야 합니다.

* 스키마 보기
* 스키마 관리
* ID 네임스페이스 보기
* 데이터 세트 보기

Experience Platform 권한에 대한 자세한 내용은 [Adobe Experience Platform의 액세스 제어](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ko)를 참조하십시오.

## 개별 지표 또는 차원에 대한 액세스 권한 부여

Customer Journey Analytics에서는 기존의 Adobe Analytics에서와 같이 개별 지표 또는 차원을 거부하거나 허용할 수 없습니다. 지표와 차원은 [데이터 보기](/help/data-views/data-views.md)에서 변경할 수 있으므로 보고도 소급 변경하는 CJA의 변경으로부터 영향을 받습니다.

## 사용자 액세스

Customer Journey Analytics의 제품 관리자가 아닌 사용자(사용자)는 데이터 보기 또는 연결을 볼 수 없지만 필터, 프로젝트 및 계산된 지표를 만들 수 있습니다.

