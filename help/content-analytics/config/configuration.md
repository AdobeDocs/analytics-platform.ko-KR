---
title: 콘텐츠 분석 구성
description: 콘텐츠 분석 구성 방법에 대한 개요
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: ec0ea74df83bbd07b7e026d7b9d7114c7dc595ab
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 2%

---

# 콘텐츠 분석 구성

>[!WARNING]
>
>이 문서는 예정된 최종 버전의 임시 비공식 초안 버전이며 Content Analytics 설명서의 일부입니다. 모든 내용은 변경될 수 있으며 이 문서의 현재 버전에서 파생될 수 있는 법적 의무는 없습니다.
>

{{release-limited-testing}}


조직의 콘텐츠 분석을 구성하려면 콘텐츠 분석 [안내 구성](guided.md)을 사용합니다. 구성 마법사는 Content Analytics의 자동 구성을 위한 사전 요구 사항을 설정하는 데 필요한 모든 단계를 안내합니다.

구현이 성공하면 안내가 있는 구성 마법사를 사용하여 몇 가지 사항을 변경할 수 있습니다. 그러나 그 외에 [수동 변경](manual.md)이 필요할 수 있습니다.

## 사전 요구 사항

Content Analytics를 구성하기 전에 다음 전제 조건이 충족되는지 확인하십시오.

* 콘텐츠 분석에 사용되는 기능 서비스에 대한 사용자 에이전트 및 IP 주소를 허용 목록에 추가했습니다. 사용자 에이전트 문자열은 `AdobeFeaturization/1.0`입니다.
* 연결을 관리하고 데이터 컬렉션을 관리할 수 있는 추가 권한이 있는 Customer Journey Analytics 제품 관리자 역할이 있습니다. 필요한 Experience Platform 권한은 다음과 같습니다.

  | 카테고리 | 사용 권한 | 설명 |
  |---|---|---|
  | [!UICONTROL 데이터 수집] | 데이터스트림 보기 | 데이터스트림에 대한 읽기 전용 액세스 권한. |
  | [!UICONTROL 데이터 수집] | 데이터 스트림 관리 | 데이터 스트림을 읽기, 만들기, 편집 및 삭제할 수 있습니다. |
  | [!UICONTROL 데이터 모델링] | [!UICONTROL 스키마 보기] | 스키마 및 관련 리소스에 대한 읽기 전용 액세스 권한. |
  | [!UICONTROL 데이터 모델링] | [!UICONTROL 스키마 관리] | 스키마 및 관련 리소스를 읽고, 만들고, 편집하고, 삭제할 수 있는 액세스 권한. |
  | [!UICONTROL 데이터 관리] | [!UICONTROL 데이터 세트 보기] | 데이터 세트 및 스키마에 대한 읽기 전용 액세스 권한. |
  | [!UICONTROL 데이터 관리] | [!UICONTROL 데이터 세트 관리] | 데이터 세트 읽기, 만들기, 편집 및 삭제에 대한 액세스 권한. 스키마에 대한 읽기 전용 액세스 권한. |
  | [!UICONTROL 데이터 수집] | [!UICONTROL 소스 관리] | 소스를 읽고, 만들고, 편집하고, 비활성화할 수 있는 액세스 권한. |
  | [!UICONTROL Identity Management] | [!UICONTROL ID 네임스페이스 보기] | ID 네임스페이스에 대한 읽기 전용 액세스 권한. |

* 다음과 같은 중요한 구성 옵션을 신중하게 고려했습니다.

   * 사이트가 경험 보고에 적합합니까? 적절한 경험 보고는 다음 조건이 충족될 때만 가능합니다.
      * 사이트 콘텐츠는 URL에 의해서만 구동됩니다.
      * 사이트의 페이지는 페이지 URL을 사용하여 재현할 수 있으며 어떤 선택적 URL 매개 변수가 경험을 유도하는지 이해합니다.
   * 컨텐츠 참여 분석 및 통찰력을 캡처할 페이지를 명확하게 이해하고 있습니다.
   * 컨텐츠 참여 분석 및 통찰력을 캡처할 (유형) 에셋을 명확히 이해하고 있습니다.


>>
[!MORELIKETHIS]
>>
* [구성 가이드](guided.md)
* [수동 구성](manual.md)
* [액세스 제어](/help/technotes/access-control.md)
>


