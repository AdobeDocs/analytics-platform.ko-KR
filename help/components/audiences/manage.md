---
title: Customer Journey Analytics에서 생성된 대상 관리
description: Customer Journey Analytics에서 대상을 관리하는 방법 알아보기
exl-id: 0cc50f64-40b5-4245-a9bb-a60fc90f507a
source-git-commit: 86998458bd79f1fc17c17e58932b2b8434abf041
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 67%

---

# Customer Journey Analytics에서 생성된 대상 관리

>[!NOTE]
>
>이 기능은 현재 [제한적 테스트](/help/release-notes/releases.md)가 실시되고 있습니다.

이전에 생성된 대상을 관리하면 다음과 같은 작업을 수행할 수 있습니다.

* 자동 대상 새로 고침/업데이트를 **예약하거나 예약을 취소**&#x200B;합니다. 일정의 최대 만료 기간은 1년입니다.
* 곧 만료될 예정인 **대상의 새로 고침 일정을 갱신**&#x200B;합니다. 만료될 예정인 대상은 만료될 예정인 예약된 보고서와 유사하게 처리됩니다. 관리자는 일정이 만료되기 한 달 전에 이메일을 수신합니다.
* 보기 **새로 고침 간격** 그리고 **마지막으로 대상이 업데이트됨**
* Customer Journey Analytics(CJA)에서 **대상을 생성하는 데 걸린 시간**&#x200B;과 활성화 목적을 위해 실시간 고객 프로필에 대상을 표시하는 데 걸린 시간에 대한 통찰력을 얻으십시오.
* CJA의 대상이 **실시간 고객 프로필** 또는 (이상적으로) CJA에서 생성한 대상을 소비하는 모든 Experience Platform 애플리케이션에서 활발히 사용되고 있는지 확인하십시오.

## 관리 UI

![](assets/manage.png)

| UI 설정 | 정의 |
| --- | --- |
| 필터 숨기기/표시 | 왼쪽 레일에서 다음 필터를 표시하거나 숨길 수 있습니다. <ul><li>[!UICONTROL 데이터 보기]</li><li>[!UICONTROL 소유자]</li><li>[!UICONTROL 새로 고침 빈도]</li><li>[!UICONTROL 태그]</li></ul> |
| [!UICONTROL 제목 및 설명] | 대상자를 만들 때 대상자에게 제공된 제목 및 설명입니다. |
| [!UICONTROL 데이터 보기] | 이 대상자를 만든 데이터 보기입니다. |
| [!UICONTROL 대상 크기] | 이 대상의 총 사람 수입니다. |
| [!UICONTROL 소유자] | 대상자의 소유자 - 대상자를 만든 사용자입니다. |
| [!UICONTROL 새로 고침 빈도] | 대상자를 만들 때 구성된 새로 고침 간격입니다. |
| [!UICONTROL 태그] | 이 대상자에 적용되는 모든 태그. |
| [!UICONTROL 퍼블리싱 상태] | 표시 가능 [!UICONTROL 준비], [!UICONTROL 진행 중], 또는 [!UICONTROL 오류]. |
| [!UICONTROL  마지막으로 새로 고침] | 대상을 마지막으로 새로 고침했을 때. |
| [!UICONTROL 마지막 수정일] | 대상을 마지막으로 편집하거나 수정한 경우 |

{style=&quot;table-layout:auto&quot;}
