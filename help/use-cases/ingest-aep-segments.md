---
title: AEP 대상을 Customer Journey Analytics에 수집
description: 추가적인 분석을 위해 AEP 대상을 Customer Journey Analytics에 수집하는 방법을 설명합니다.
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: cd1d639ad698c188c506881b2b17103b0a3559f2
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 4%

---


# AEP 대상을 Customer Journey Analytics(CJA)에 수집

(Brandon, fyi, &#39;Unified Profile&#39;은 &#39;Real-time Customer Profile&#39;의 오래된 용어입니다. AEP 문서 관리자에 따르면 AEP 문서 세트에서 UP에 대한 문서를 찾을 수 없습니다.)

이 사용 사례에서는 AEP(Adobe Experience Platform) 대상을 CJA로 가져오는 중간 수동 방법을 설명합니다. 이러한 대상은 AEP 세그먼트 빌더, Adobe Audience Manager 또는 기타 도구에서 생성되었으며 실시간 고객 프로필(RTCP)에 저장되었을 수 있습니다. 대상은 개인 ID, 프로필 ID 등으로 구성됩니다. 분석을 위해 CJA Workspace로 가져오려고 합니다.

## 전제 조건

* Adobe Experience Platform에 액세스 (AEP), 특히 실시간 고객 프로필.
* Customer Journey Analytics에 액세스
* 사용자 지정 코드를 작성할 수 있습니까?
* 그 밖에 필요한 것이 있습니까.

## 1단계: 실시간 고객 프로필에서 대상 선택 {#audience}

Adobe Experience Platform [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko) (RTCP)를 사용하면 온라인, 오프라인, CRM 및 타사 등 여러 채널의 데이터를 결합하여 각 개별 고객을 전체적으로 볼 수 있습니다. RTCP에 다양한 소스에서 온 대상이 이미 있을 수 있습니다. 하나 이상의 대상을 선택합니다.

## 2단계: 내보낼 프로필 결합 데이터 세트 만들기

대상자를 CJA에 연결할 수 있는 데이터 세트로 내보내려면 스키마가 프로필인 데이터 세트를 만들어야 합니다 [결합 스키마](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).
결합 스키마는 동일한 클래스를 공유하고 프로필에 대해 활성화된 여러 스키마로 구성됩니다. 결합 스키마를 사용하면 동일한 클래스를 공유하는 스키마에 포함된 모든 필드를 통합할 수 있습니다. 실시간 고객 프로필은 결합 스키마를 사용하여 각 개별 고객에 대한 전체적인 보기를 만듭니다.

## 3단계: API 호출을 통해 데이터를 데이터 세트에 내보내기 {#export}

CJA로 대상자를 가져오려면 먼저 AEP의 데이터 세트로 내보내야 합니다. 이 작업은 세그먼테이션 API, 특히 [내보내기 작업 API 끝점](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en). 내보내기 작업을 만들고, 그 결과를 2단계에서 만든 프로필 조합 AEP 데이터 세트에 넣을 수 있습니다.

## 4단계: 내보내기 출력 편집

대상에 대한 내보내기 작업을 만들 때 CJA에서 보고를 수행하려면 개인 ID와 대상 ID만 필요합니다. 그러나 표준 내보내기 작업에는 더 많은 데이터가 포함되어 있으므로 이 출력을 편집하여 외부 데이터를 제거해야 합니다.

다음은 프로필 결합 데이터 세트에 있는 내보내기 출력의 예입니다. **이전** 모든 편집:

![편집되지 않은 출력](assets/export-unedited.png)

다음 사항을 참고하십시오.

* 대상 ID는 `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* 상태는 &quot;실현&quot; 또는 &quot;입력됨&quot;이어야 하지만 &quot;종료됨&quot;은 아니어야 합니다. &quot;종료한&quot;를 &quot;공백&quot;으로 바꿉니다.

CJA에 보낼 수 있는 프로필 데이터 세트 형식입니다.

![편집된 출력](assets/export-edited.png)

다음은 있어야 하는 데이터 요소입니다.

* `_aresprodvalidation`: 조직 ID를 나타냅니다. 당신 것은 다를 거예요
* `personID`: 이 경우 친숙한 이름입니다
* `audienceMembershipIdList` 문자열 필드: 대상 ID
* 대상자에 대한 친숙한 이름 추가(`audienceMembershipIdName`), 예

   ![친숙한 대상 이름](assets/audience-name)

## 5단계: CJA에서 이 프로필 데이터 세트에 대한 연결 만들기

[연결 만들기](/help/connections/create-connection.md)

## 6단계: 데이터 뷰 만들기

추가 `audienceMembershipIdName` 및 `personID` dataview로 이동합니다.

## 7단계: Workspace의 보고서

이제 다음에 대해 보고할 수 있습니다. `audienceMembershipIdName` 및 `personID` 작업 공간.
스크린샷이 좋겠네요.

방법:

여러 대상의 구성원인 사용자를 처리할 때 더 많은 단계를 작성합니다.




