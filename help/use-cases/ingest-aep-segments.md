---
title: AEP 대상을 Customer Journey Analytics에 수집
description: 추가적인 분석을 위해 AEP 대상을 Customer Journey Analytics에 수집하는 방법을 설명합니다.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 490a754270922481ebd893514c530a0667d9d6e4
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 2%

---

# AEP 대상을 Customer Journey Analytics(CJA)에 수집

이 사용 사례에서는 AEP(Adobe Experience Platform) 대상을 CJA로 가져오는 중간 수동 방법을 설명합니다. 이러한 대상은 AEP 세그먼트 빌더, Adobe Audience Manager 또는 기타 도구에서 생성되었으며 실시간 고객 프로필(RTCP)에 저장되었을 수 있습니다. 대상은 적용 가능한 속성/이벤트 등과 함께 프로필 ID 세트로 구성됩니다. 분석을 위해 CJA Workspace로 가져오려고 합니다.

## 전제 조건

* Adobe Experience Platform에 액세스 (AEP), 특히 실시간 고객 프로필.
* AEP 스키마 및 데이터 세트를 생성/관리하기 위한 액세스 권한.
* AEP 쿼리 서비스(및 SQL 쓰기 기능)나 다른 도구에 액세스하여 일부 간단한 변환을 수행합니다.
* Customer Journey Analytics에 액세스. CJA 연결 및 데이터 보기를 만들거나 수정하려면 CJA 제품 관리자여야 합니다.
* Adobe API 사용 기능(세그먼테이션, 선택적으로 기타)

## 1단계: 실시간 고객 프로필에서 대상 선택 {#audience}

Adobe Experience Platform [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko) (RTCP)를 사용하면 온라인, 오프라인, CRM 및 타사 등 여러 채널의 데이터를 결합하여 각 개별 고객을 전체적으로 볼 수 있습니다.

RTCP에 다양한 소스에서 온 대상이 이미 있을 수 있습니다. CJA에 수집할 대상을 한 개 이상 선택합니다.

## 2단계: 내보낼 프로필 결합 데이터 세트 만들기

CJA에서 연결에 최종 추가할 수 있는 데이터 세트로 대상을 내보내려면 스키마가 프로필인 데이터 세트를 만들어야 합니다 [결합 스키마](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).

결합 스키마는 동일한 클래스를 공유하고 프로필에 대해 활성화된 여러 스키마로 구성됩니다. 결합 스키마를 사용하면 동일한 클래스를 공유하는 스키마에 포함된 모든 필드를 통합할 수 있습니다. 실시간 고객 프로필은 결합 스키마를 사용하여 각 개별 고객에 대한 전체적인 보기를 만듭니다.

## 3단계: API 호출을 통해 프로필 조합 데이터 세트로 대상 내보내기 {#export}

CJA로 대상자를 가져오려면 먼저 AEP 데이터 세트로 내보내야 합니다. 이 작업은 세그먼테이션 API, 특히 [내보내기 작업 API 끝점](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en).

원하는 대상 ID를 사용하여 내보내기 작업을 만들고, 그 결과를 2단계에서 만든 프로필 조합 AEP 데이터 세트에 넣을 수 있습니다. 대상에 대해 다양한 속성/이벤트를 내보낼 수 있지만, 활용할 CJA 연결에 사용된 개인 ID 필드와 일치하는 특정 프로필 ID 필드만 내보내면 됩니다(5단계의 아래 참조).

## 4단계: 내보내기 출력 편집

CJA로 수집하려면 내보내기 작업 결과를 별도의 프로필 데이터 세트로 변환해야 합니다.  이러한 변환은 AEP 쿼리 서비스 또는 원하는 다른 변환 도구로 수행할 수 있습니다.  CJA에서 보고를 수행하려면 프로필 ID(CJA의 개인 ID와 일치함)와 하나 이상의 대상 ID만 필요합니다. 하지만 표준 내보내기 작업에는 더 많은 데이터가 포함되어 있으므로 이 출력을 편집하여 외부 데이터를 제거하고 몇 가지 사항을 이동해야 합니다.  또한 변환된 데이터를 추가하기 전에 먼저 스키마/데이터 세트를 만들어야 합니다.

다음은 프로필 결합 데이터 세트에 있는 내보내기 출력의 예입니다. **이전** 모든 편집:

![편집되지 않은 출력](assets/export-unedited.png)

다음 사항을 참고하십시오.

* 대상 ID는 `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* 상태는 &quot;실현&quot; 또는 &quot;입력됨&quot;이어야 하지만 &quot;종료됨&quot;은 아니어야 합니다.

CJA에 보낼 수 있는 프로필 데이터 세트 형식입니다.

![편집된 출력](assets/export-edited.png)

다음은 있어야 하는 데이터 요소입니다.

* `_aresprodvalidation` 문자열 필드: 조직 ID를 나타냅니다. 당신 것은 다를 거예요
* `personID` 문자열 필드: 개인을 식별하는 프로필 데이터 세트의 표준 XDM 스키마 필드입니다. 내보내기에서 프로필 ID를 사용합니다.
* `audienceMembershipId` 문자열 필드: 내보내기의 대상 ID입니다.  참고: 이 필드의 이름은 원하는 대로 지정할 수 있습니다(자체 스키마에서).
* 대상자에 대한 친숙한 이름 추가(`audienceMembershipIdName`), 예

   ![친숙한 대상 이름](assets/audience-name.png)

* 원할 경우 다른 대상 메타데이터를 추가합니다.

## 5단계: 이 프로필 데이터 세트를 CJA의 기존 연결에 추가합니다

새 연결을 만들 수 있지만 대부분의 고객은 기존 연결에 연결을 추가하려고 합니다. 대상 ID는 CJA의 기존 데이터를 &quot;보강&quot;합니다.

[연결 만들기](/help/connections/create-connection.md)

## 6단계: 기존 CJA 데이터 보기 수정(또는 새 만들기)

추가 `audienceMembershipId`, `audienceMembershipIdName` 및 `personID` 를 클릭합니다.

## 7단계: Workspace의 보고서

이제 다음에 대해 보고할 수 있습니다. `audienceMembershipId`, `audienceMembershipIdName` 및 `personID` 작업 공간.

## 추가 참고 사항

* 대상 데이터를 CJA 내에서 항상 새로 고치도록 일반 케이던스에서 이 프로세스를 수행해야 합니다.
* 단일 CJA 연결 내에서 여러 대상을 가져올 수 있습니다. 이렇게 하면 프로세스에 더 많은 복잡성이 추가되지만, 가능합니다. 이를 수행하려면 위의 프로세스를 몇 가지 수정해야 합니다.
   1. RTCP 내에서 대상 컬렉션의 원하는 각 대상에 대해 이 프로세스를 수행합니다.
   1. 내보내기 작업 출력의 변환을 수행할 때 목록을 만들어야 합니다 `audienceMembershipId(s)`, 단일 CJA 개인 ID가 여러 대상에 속할 수 있으므로 . 향후 어느 시점에서 CJA는 프로필 데이터 세트의 배열/개체 배열을 지원합니다. 이러한 기능이 지원되면 `audienceMembershipId` 또는 `audienceMembershipIdName` 이 가장 좋은 선택입니다. 그 사이에 내보내기 작업 출력에서 각 프로필 ID에 대한 현재 대상 ID를 모두 추출하여(&quot;실현됨&quot; 또는 &quot;입력됨&quot; 상태) 쉼표로 구분된 값 문자열(예: `<id1>,<id2>,...`).  종료됨 상태인 대상 ID가 있는 경우 목록에 없는지 확인합니다.  친숙한 이름 연결을 유지하려는 경우 목록의 각 ID 끝(다른 메타데이터와 함께)에 첨부할 수 있습니다.
   1. 데이터 보기에서 `audienceMembershipId` 쉼표로 구분된 값 문자열을 배열로 변환하는 필드입니다. 참고: 현재 배열에 10개 값 제한이 있습니다.
   1. 이제 이 새 차원에 대해 보고할 수 있습니다 `audienceMembershipIds` CJA Workspace 내에서 사용할 수 있습니다.
