---
title: AEP 대상을 Customer Journey Analytics로 수집
description: 추가 분석을 위해 AEP 대상을 Customer Journey Analytics로 수집하는 방법에 대해 설명합니다.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 9c4869bb632f3d69d8704009744246b975cb5c4a
workflow-type: ht
source-wordcount: '1049'
ht-degree: 100%

---

# AEP 대상을 Customer Journey Analytics(CJA)로 수집

이 사용 사례에서는 Adobe Experience Platform(AEP) 대상을 CJA로 가져오는 임시적이고 수동적인 방법에 대해 알아봅니다. 이러한 대상은 AEP 세그먼트 빌더, Adobe Audience Manager 또는 기타 도구에서 생성되었을 수 있으며 실시간 고객 프로필(RTCP)에 저장됩니다. 대상은 적용 가능한 속성/이벤트 등과 함께 프로필 ID 세트로 구성됩니다. 분석을 위해 이를 CJA 작업 영역으로 가져오고자 합니다.

## 사전 요구 사항

* Adobe Experience Platform에 액세스 (AEP), 특히 실시간 고객 프로필
* AEP 스키마 및 데이터 세트를 만들거나 관리할 수 있는 액세스 권한
* AEP 쿼리 서비스(및 SQL 작성 기능) 또는 일부 가벼운 변환을 수행하기 위한 다른 툴에 액세스
* Customer Journey Analytics에 액세스 CJA 연결 및 데이터 보기를 생성/수정하려면 CJA 제품 관리자여야 합니다.
* Adobe API 사용 기능(세그먼테이션, 기타 옵션)

## 1단계: 실시간 고객 프로필에서 대상 선택 {#audience}

Adobe Experience Platform [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=kr)(RTCP)을 사용하면 온라인, 오프라인, CRM 및 서드파티를 비롯한 여러 채널의 데이터를 결합하여 각 개별 고객에 대한 거시적인 보기를 확인할 수 있습니다.

다양한 소스에서 가져온 RTCP의 대상이 이미 있을 수 있습니다. CJA로 수집할 하나 이상의 대상을 선택합니다.

## 2단계: 내보내기를 위해 Profile Union 데이터 세트 생성

CJA의 연결에 최종적으로 추가될 수 있는 데이터 세트로 대상을 내보내려면 스키마가 프로필 [결합 스키마](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=kr#understanding-union-schemas)인 데이터 세트를 생성해야 합니다.

결합 스키마는 동일한 클래스를 공유하고 프로필에 대해 활성화된 여러 스키마로 구성됩니다. 통합 스키마를 사용하면 동일한 클래스를 공유하는 스키마 내에 포함된 모든 필드의 통합을 표시할 수 있습니다. 실시간 고객 프로필은 통합 스키마를 사용하여 각 개별 고객에 대한 거시적인 보기를 생성합니다.

## 3단계: API 호출을 통해 대상을 Profile Union 데이터 세트로 내보내기 {#export}

대상을 CJA로 가져오려면 먼저 AEP 데이터 세트로 내보내야 합니다. 이는 Segmentation API, 특히 [Export Jobs API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=kr)를 통해서만 수행할 수 있습니다.

선택한 대상 ID를 사용하여 내보내기 작업을 만들고 2단계에서 만든 Profile Union AEP 데이터 세트에 결과를 넣을 수 있습니다. 대상을 위한 다양한 속성/이벤트를 내보낼 수 있지만 활용할 CJA 연결에 사용된 개인 ID 필드와 일치하는 특정 프로필 ID 필드만 내보내면 됩니다(아래 5단계 참조).

## 4단계: 내보내기 출력 편집

내보내기 작업의 결과를 CJA로 수집하려면 별도의 프로필 데이터 세트로 변환해야 합니다. 이 변환은 [AEP 쿼리 서비스](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=kr) 또는 선택한 다른 변환 도구를 사용하여 수행할 수 있습니다. CJA에서 보고하려면 프로필 ID(CJA의 개인 ID와 일치)와 하나 이상의 대상 ID만 있으면 됩니다.

단, 표준 내보내기 작업에는 더 많은 데이터가 포함되어 있으므로 이 출력을 편집하여 관련 없는 데이터를 제거하고 일부 항목을 이동해야 합니다. 또한 변환된 데이터를 추가하기 전에 먼저 스키마/데이터 세트를 생성해야 합니다.

다음은 편집 **전** 프로필 통합 데이터 세트의 내보내기 출력 예입니다.

![편집되지 않은 출력](assets/export-unedited.png)

다음 사항을 참고하십시오.

* 대상 ID는 `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status` 아래에 포함됩니다.
* 상태는 “종료됨”이 아닌 “인식됨” 또는 “입력됨”이어야 합니다.

이는 CJA로 보낼 수 있는 프로필 데이터 세트의 포맷입니다.

![편집된 출력](assets/export-edited.png)

다음은 존재해야 하는 데이터 요소입니다.

* `_aresprodvalidation` 문자열 필드: 조직 ID를 나타냅니다. 사용자 ID는 다를 수 있습니다.
* `personID` 문자열 필드: 이는 사용자를 식별하기 위한 프로필 데이터 세트의 표준 XDM 스키마 필드입니다. 내보내기에서 프로필 ID를 사용합니다.
* `audienceMembershipId` 문자열 필드: 내보내기의 대상 ID입니다. 참고: 이 필드에는 원하는 이름을 지정할 수 있습니다(자체 스키마에서).
* 다음과 같이 대상에 친숙한 이름(`audienceMembershipIdName`)을 추가합니다.

   ![친숙한 대상 이름](assets/audience-name.png)

* 원하는 경우 다른 대상 메타데이터를 추가합니다.

## 5단계: 이 프로필 데이터 세트를 CJA의 기존 연결에 추가

[새 연결을 만들](/help/connections/create-connection.md) 수 있지만 대부분의 고객은 프로필 데이터 세트를 기존 연결에 추가하고자 할 것입니다. 대상 ID는 CJA의 기존 데이터를 “강화”합니다.

## 6단계: 기존 CJA 데이터 보기 수정(또는 새로 만들기)

데이터 보기에 `audienceMembershipId`, `audienceMembershipIdName` 및 `personID`를 추가합니다.

## 7단계: 작업 영역에서 보고

이제 작업 영역에서 `audienceMembershipId`, `audienceMembershipIdName` 및 `personID`에 대해 보고할 수 있습니다.

## 추가 참고 사항

* CJA 내에서 대상 데이터가 지속적으로 새로 고쳐지도록 이 프로세스를 정기적으로 수행해야 합니다.
* 단일 CJA 연결 내에서 여러 대상을 가져올 수 있습니다. 이는 프로세스에 복잡성을 가중시키지만 실행 가능합니다. 이 기능이 작동하려면 위의 프로세스를 몇 가지 수정해야 합니다.
   1. RTCP 내의 대상 컬렉션에서 원하는 각 대상에 대해 이 프로세스를 수행합니다.
   1. 내보내기 작업 출력의 변환을 수행할 때 단일 CJA 개인 ID가 여러 대상에 속할 수 있으므로 `audienceMembershipId(s)`의 목록을 작성해야 합니다. 향후 CJA는 프로필 데이터 세트에서 배열/오브젝트 배열을 지원할 예정입니다. 해당 기능이 지원되면 `audienceMembershipId` 또는 `audienceMembershipIdName`에 대한 오브젝트 배열을 사용하는 것이 가장 적합한 옵션이 될 것입니다. 지원되기 전까지는 내보내기 작업 출력의 각 프로필 ID에 대한 현재 대상 ID를 모두 추출하고(“인식됨” 또는 “입력됨” 상태로) 쉼표로 구분된 값 문자열(예: `<id1>,<id2>,...`)에 넣습니다. 상태가 “종료됨”인 대상 ID가 있는 경우 목록 내에 없는지 확인합니다. ID와 친숙한 이름 연결을 유지하고자 하는 경우 목록의 각 ID 끝에 (다른 메타데이터와 함께) 이름을 첨부할 수 있습니다.
   1. 데이터 보기에서 `audienceMembershipId` 필드의 하위 문자열 변환을 사용하여 새 차원을 만들어 쉼표로 구분된 값 문자열을 배열로 변환합니다. 참고: 현재 배열의 값은 10개로 제한됩니다.
   1. 이제 CJA 작업 영역에서 이 새로운 차원 `audienceMembershipIds`에 대해 보고할 수 있습니다.
