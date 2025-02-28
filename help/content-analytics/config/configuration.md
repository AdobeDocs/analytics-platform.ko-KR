---
title: 콘텐츠 분석 구성
description: 콘텐츠 분석 구성 방법에 대한 개요
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 596e54a559bac69214e1de3ea37da6177f110b7a
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 2%

---

# 콘텐츠 분석 구성

>[!WARNING]
>
>이 문서는 예정된 최종 버전의 임시 비공식 초안 버전이며 Content Analytics 설명서의 일부입니다. 모든 내용은 변경될 수 있으며 이 문서의 현재 버전에서 파생될 수 있는 법적 의무는 없습니다.
>

{{release-limited-testing}}

Content Analytics의 구성은 다음 단계로 구성됩니다.

![콘텐츠 분석 구성](../assets/aca-configuration.svg)

1. 콘텐츠 분석 [구성 가이드](guided.md) 마법사를 사용하여 콘텐츠 분석 구성에 대한 필수 구성 요소를 설정하는 데 필요한 모든 단계를 안내합니다. 구성을 저장하고 나중에 다시 돌아갈 수 있습니다.
1. 구성 값에 익숙해지면 구성을 구현할 수 있습니다. 이 구현은 마법사에서 구성한 내용을 기반으로 필요한 모든 아티팩트를 만듭니다. 다음 가공물이 생성, 업데이트 또는 선택됩니다.
   * 사용자 지정 여정 분석
      * [데이터 보기](/help/data-views/data-views.md)를 선택했습니다.
      * 선택한 데이터 보기에서 자동으로 파생된 [연결](/help/connections/overview.md)이(가) 선택되었습니다.
   * Experience Platform
      * 연결을 통해 자동으로 파생되는 샌드박스가 선택됩니다. 샌드박스에서 필요한 워크플로우 및 서비스를 사용할 수 있습니다.
      * 샌드박스에서 콘텐츠 Analytics 스키마가 선택됩니다. 사용할 수 없는 경우 필요한 스키마가 생성됩니다.
      * 샌드박스에서 선택된 Content Analytics 데이터 세트. 사용할 수 없는 경우 필요한 데이터 세트가 만들어집니다.
   * 데이터 수집
      * 데이터 스트림이 생성되고 데이터 스트림 내에 Experience Platform 서비스가 구성되어 데이터를 Content Analytics 경험 이벤트 데이터 세트로 스트리밍합니다.
      * 태그 속성은 구성 마법사에서 올바른 샌드박스, 데이터스트림 및 기타 구성 옵션에 대해 구성된 Adobe Content Analytics 확장으로 만들어집니다.
1. 태그 속성을 수동으로 게시하는 경우에만 콘텐츠 분석이 효과적으로 배포되고 활성화됩니다.
1. [안내가 있는 구성](guided.md) 마법사를 사용하여 구현된 구성에 대해 일부 제한적으로만 변경할 수 있습니다. 예를들어 [데이터 보기](/help/data-views/data-views.md)를 변경합니다.
1. 연결된 Tag 속성의 [Adobe Content Analytics 확장](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)을 통해 구현된 구성에 다른 변경 작업을 수행할 수 있습니다.
1. Tag 속성을 수동으로 다시 게시하는 경우에만 4단계와 5단계의 구성 수정 사항이 효과적으로 배포 및 활성화됩니다.


Content Analytics를 구성하기 전에 다음 전제 조건이 충족되는지 확인하십시오.


>[!PREREQUISITES]
>
>* 콘텐츠 분석에 사용되는 기능 서비스에 대한 사용자 에이전트 및 IP 주소를 허용 목록에 추가했습니다. 사용자 에이전트 문자열은 `AdobeFeaturization/1.0`입니다.
>* 연결을 관리하고 데이터 컬렉션을 관리할 수 있는 추가 권한이 있는 Customer Journey Analytics 제품 관리자 역할이 있습니다. 필요한 Experience Platform 권한은 다음과 같습니다.
>  
>   | 카테고리 | 사용 권한 | 설명 |
>   |---|---|---|
>   | [!UICONTROL 데이터 수집] | 데이터스트림 보기 | 데이터스트림에 대한 읽기 전용 액세스 권한. |
>   | [!UICONTROL 데이터 수집] | 데이터 스트림 관리 | 데이터 스트림을 읽기, 만들기, 편집 및 삭제할 수 있습니다. |
>   | [!UICONTROL 데이터 모델링] | [!UICONTROL 스키마 보기] | 스키마 및 관련 리소스에 대한 읽기 전용 액세스 권한. |
>   | [!UICONTROL 데이터 모델링] | [!UICONTROL 스키마 관리] | 스키마 및 관련 리소스를 읽고, 만들고, 편집하고, 삭제할 수 있는 액세스 권한. |
>   | [!UICONTROL 데이터 관리] | [!UICONTROL 데이터 세트 보기] | 데이터 세트 및 스키마에 대한 읽기 전용 액세스 권한. |
>   | [!UICONTROL 데이터 관리] | [!UICONTROL 데이터 세트 관리] | 데이터 세트 읽기, 만들기, 편집 및 삭제에 대한 액세스 권한. 스키마에 대한 읽기 전용 액세스 권한. |
>   | [!UICONTROL 데이터 수집] | [!UICONTROL 소스 관리] | 소스를 읽고, 만들고, 편집하고, 비활성화할 수 있는 액세스 권한. |
>   | [!UICONTROL Identity Management] | [!UICONTROL ID 네임스페이스 보기] | ID 네임스페이스에 대한 읽기 전용 액세스 권한. |
>
>* 다음과 같은 중요한 구성 옵션을 신중하게 고려했습니다.
>
>   * 사이트가 경험 보고에 적합합니까? 적절한 경험 보고는 다음 조건이 충족될 때만 가능합니다.
>   * 사이트 콘텐츠는 URL에 의해서만 구동됩니다.
>   * 사이트의 페이지는 페이지 URL을 사용하여 재현할 수 있으며 어떤 선택적 URL 매개 변수가 경험을 유도하는지 이해합니다.
>* 컨텐츠 참여 분석 및 통찰력을 캡처할 페이지를 명확하게 이해하고 있습니다.
>* 컨텐츠 참여 분석 및 통찰력을 캡처할 (유형) 에셋을 명확히 이해하고 있습니다.
>


>[!MORELIKETHIS]
>
>* [구성 가이드](guided.md)
>* [수동 구성](manual.md)
>* [액세스 제어](/help/technotes/access-control.md)
>


