---
title: Adobe Experience Platform 대상자를 Customer Journey Analytics로 수집
description: 추가 분석을 위해 Adobe Experience Platform 대상을 Customer Journey Analytics으로 수집하는 방법에 대해 설명합니다.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 51%

---

# Adobe Experience Platform 대상을 Adobe Customer Journey Analytics에 수집

이 사용 사례에서는 Adobe Experience Platform(Adobe Experience Platform) 대상을 Customer Journey Analytics으로 가져오는 임시적이고 수동적인 방법에 대해 알아봅니다. 이러한 대상은 Adobe Experience Platform 세그먼트 빌더, Adobe Audience Manager 또는 기타 도구에서 생성되었을 수 있으며 실시간 고객 프로필(RTCP)에 저장됩니다. 대상자는 적용 가능한 속성/이벤트 등과 함께 프로필 ID 세트로 구성됩니다. 그리고 분석을 위해 Customer Journey Analytics Workspace으로 가져오고자 합니다.

## 사전 요구 사항

* Adobe Experience Platform(Adobe Experience Platform), 특히 실시간 고객 프로필에 액세스합니다.
* Adobe Experience Platform 스키마 및 데이터 세트를 만들고 관리할 수 있는 액세스 권한.
* Adobe Experience Platform 쿼리 서비스(및 SQL 작성 기능) 또는 일부 가벼운 변환을 수행하기 위한 다른 도구에 액세스합니다.
* Customer Journey Analytics에 액세스 Customer Journey Analytics 연결 및 데이터 보기를 생성/수정하려면 Customer Journey Analytics 제품 관리자여야 합니다.
* Adobe API 사용 기능(세그먼테이션, 기타 옵션)

## 1단계: 실시간 고객 프로필에서 대상자 선택 {#audience}

Adobe Experience Platform [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko-KR)(RTCP)을 사용하면 온라인, 오프라인, CRM 및 서드파티를 비롯한 여러 채널의 데이터를 결합하여 각 개별 고객에 대한 거시적인 보기를 확인할 수 있습니다.

다양한 소스에서 가져온 RTCP에 대상자가 이미 있을 수 있습니다. Customer Journey Analytics에 수집할 하나 이상의 대상을 선택합니다.

## 2단계: 내보내기를 위해 Profile Union 데이터 세트 생성

Customer Journey Analytics의 연결에 최종적으로 추가될 수 있는 데이터 세트로 대상을 내보내려면 스키마가 프로필 [결합 스키마](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html#understanding-union-schemas)인 데이터 세트를 만들어야 합니다.

결합 스키마는 동일한 클래스를 공유하고 프로필에 대해 활성화된 여러 스키마로 구성됩니다. 통합 스키마를 사용하면 동일한 클래스를 공유하는 스키마 내에 포함된 모든 필드의 통합을 표시할 수 있습니다. 실시간 고객 프로필은 통합 스키마를 사용하여 각 개별 고객에 대한 거시적인 보기를 생성합니다.

## 3단계: API 호출을 통해 대상자를 Profile Union 데이터 세트로 내보내기 {#export}

대상을 Customer Journey Analytics으로 가져오려면 먼저 Adobe Experience Platform 데이터 세트로 내보내야 합니다. 이는 Segmentation API, 특히 [Export Jobs API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html)를 통해서만 수행할 수 있습니다.

선택한 대상 ID를 사용하여 내보내기 작업을 만들고 2단계에서 만든 Profile Union Adobe Experience Platform 데이터 세트에 결과를 넣을 수 있습니다. 대상을 위한 다양한 속성/이벤트를 내보낼 수 있지만 활용할 Customer Journey Analytics 연결에 사용된 개인 ID 필드와 일치하는 특정 프로필 ID 필드만 내보내면 됩니다(아래 5단계 참조).

## 4단계: 내보내기 출력 편집

내보내기 작업의 결과를 Customer Journey Analytics으로 수집하려면 별도의 프로필 데이터 세트로 변환해야 합니다.  이 변환은 [Adobe Experience Platform 쿼리 서비스](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=ko-KR) 또는 선택한 다른 변환 도구를 사용하여 수행할 수 있습니다. Customer Journey Analytics 보고를 수행하려면 Customer Journey Analytics ID(프로필의 개인 ID와 일치)와 하나 이상의 대상 ID만 있으면 됩니다.

단, 표준 내보내기 작업에는 더 많은 데이터가 포함되어 있으므로 이 출력을 편집하여 관련 없는 데이터를 제거하고 일부 항목을 이동해야 합니다. 또한 변환된 데이터를 추가하기 전에 먼저 스키마/데이터 세트를 생성해야 합니다.

다음은 편집 **전** 프로필 통합 데이터 세트의 내보내기 출력 예입니다.

![편집되지 않은 출력](../assets/export-unedited.png)

다음 사항을 참고하십시오.

* 대상자 ID는 `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status` 아래에 포함됩니다.
* 상태는 “종료됨”이 아닌 “인식됨” 또는 “입력됨”이어야 합니다.

이는 Customer Journey Analytics으로 보낼 수 있는 프로필 데이터 세트의 형식입니다.

![편집된 출력](../assets/export-edited.png)

다음은 존재해야 하는 데이터 요소입니다.

* `_aresprodvalidation` 문자열 필드: 조직 ID를 나타냅니다. 사용자 ID는 다를 수 있습니다.
* `personID` 문자열 필드: 이는 사용자를 식별하기 위한 프로필 데이터 세트의 표준 XDM 스키마 필드입니다. 내보내기에서 프로필 ID를 사용합니다.
* `audienceMembershipId` 문자열 필드: 내보내기의 대상자 ID입니다. 참고: 이 필드에는 원하는 이름을 지정할 수 있습니다(자체 스키마에서).
* 다음과 같이 대상자에 친숙한 이름(`audienceMembershipIdName`)을 추가합니다.

  ![친숙한 대상자 이름](../assets/audience-name.png)

* 원하는 경우 다른 대상자 메타데이터를 추가합니다.

## 5단계: 이 프로필 데이터 세트를 Customer Journey Analytics의 기존 연결에 추가

[새 연결을 만들](/help/connections/create-connection.md) 수 있지만 대부분의 고객은 프로필 데이터 세트를 기존 연결에 추가하고자 할 것입니다. 대상 ID는 Customer Journey Analytics의 기존 데이터를 &quot;강화&quot;합니다.

## 6단계: 기존 Customer Journey Analytics 데이터 보기 수정(또는 새 데이터 보기 만들기)

데이터 보기에 `audienceMembershipId`, `audienceMembershipIdName` 및 `personID`를 추가합니다.

## 7단계: 작업 영역에서 보고

이제 작업 영역에서 `audienceMembershipId`, `audienceMembershipIdName` 및 `personID`에 대해 보고할 수 있습니다.

## 추가 참고 사항

* Customer Journey Analytics 내에서 대상 데이터가 지속적으로 새로 고쳐지도록 이 프로세스를 정기적으로 수행해야 합니다.
* 단일 Customer Journey Analytics 연결 내에서 여러 대상을 가져올 수 있습니다. 이는 프로세스에 복잡성을 가중시키지만 실행 가능합니다. 이 기능이 작동하려면 위의 프로세스를 몇 가지 수정해야 합니다.
   1. RTCP 내의 대상자 컬렉션에서 원하는 각 대상자에 대해 이 프로세스를 수행합니다.
   1. Customer Journey Analytics은 프로필 데이터 세트에서 배열/개체 배열을 지원합니다. audienceMembershipId 또는 audienceMembershipIdName에 대한 [오브젝트 배열](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html?lang=ko-KR)을 사용하는 것이 가장 적합한 옵션이 될 것입니다.
   1. 데이터 보기에서 `audienceMembershipId` 필드의 하위 문자열 변환을 사용하여 새 차원을 만들어 쉼표로 구분된 값 문자열을 배열로 변환합니다. 참고: 현재 배열의 값은 10개로 제한됩니다.
   1. 이제 Customer Journey Analytics Workspace 내에서 이 새 차원 `audienceMembershipIds`에 대해 보고할 수 있습니다.
