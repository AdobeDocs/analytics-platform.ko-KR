---
title: 실시간 고객 프로필에 대상 생성 및 게시
description: Customer Journey Analytics에서 대상을 게시하는 방법 알아보기
exl-id: 0221f9f1-df65-4bd6-a31d-33d1a1ba0cfe
source-git-commit: 86998458bd79f1fc17c17e58932b2b8434abf041
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 34%

---

# 대상 생성 및 게시

>[!NOTE]
>
>이 기능은 현재 [제한적 테스트](/help/release-notes/releases.md)가 실시되고 있습니다.

이 항목에서는 Customer Journey Analytics(CJA)에서 식별된 대상을 만들고 게시하는 방법에 대해 설명합니다. [실시간 고객 프로필](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ko-KR?lang=en) Adobe Experience Platform에서 고객 타깃팅 및 개인화를 확인하십시오.

다음 내용 보기 [개요](/help/components/audiences/audiences-overview.md) cja 대상의 개념을 숙지합니다.

## 대상 만들기

1. 대상을 만들려면 다음 세 가지 방법으로 시작할 수 있습니다.

   | 만들기 방법 | 세부 사항 |
   | --- | --- |
   | 기본 **[!UICONTROL 구성 요소] > [!UICONTROL 대상]** 메뉴 | Audiences Manager 페이지가 열립니다. **[!UICONTROL 대상 만들기]**&#x200B;를 클릭하면 [!UICONTROL 대상 빌더]가 열립니다. |
   | 자유 형식 테이블 내에서 | 자유 형식 테이블에서 항목을 마우스 오른쪽 버튼으로 클릭하고 **[!UICONTROL 선택 항목에서 대상 만들기]**&#x200B;를 선택합니다. 이 방법을 사용하면 테이블에서 선택한 차원 또는 차원 항목으로 필터가 미리 채워집니다. |
   | 필터 만들기/편집 UI에서 | **[!UICONTROL 이 필터에서 대상 만들기]** 확인란을 선택합니다. 이 방법을 사용하면 필터가 미리 채워집니다. |

   {style=&quot;table-layout:auto&quot;}

1. 대상자를 빌드합니다.

   대상자를 게시하기 전에 이러한 설정을 구성합니다.

   ![](assets/create-audience.png)

   | 설정 | 설명 |
   | --- | --- |
   | [!UICONTROL 이름] | 대상의 이름입니다. |
   | [!UICONTROL 태그] | 조직용으로 대상에 할당하고자 하는 모든 태그입니다. 기존 태그를 사용하거나 새 태그를 입력할 수 있습니다. |
   | [!UICONTROL 설명] | 해당 대상을 다른 대상과 구별하기 위해 대상에 대한 설명을 추가하십시오. |
   | [!UICONTROL 새로 고침 빈도] | 대상을 새로 고침하는 빈도입니다.<ul><li>새로 고칠 필요가 없는 일회성 대상(기본값)을 만들도록 선택할 수 있습니다. 예를 들어 이 기능은 특정 1회 캠페인에 유용할 수 있습니다.</li><li>다른 새로 고침 주기를 선택할 수 있습니다. 4시간 빈도의 경우 CJA 권한에 따라 75 또는 150명의 대상이 제한됩니다. 다른 간격의 경우 최대 대상자 수가 없습니다.</li></ul> |
   | 만료 날짜 | 대상 새로 고침 중단일 기본 설정은 생성일로부터 1년이 되는 날입니다. 만료 대상은 만료 예약된 보고서와 유사하게 처리됩니다. 관리자가 대상이 만료되기 한 달 전에 이메일을 받게 됩니다. |
   | 전환 확인 기간 새로 고침 | 이 대상을 생성할 때 데이터 창에서 얼마나 오래 적용될 것인지 지정합니다. 최대값은 90일입니다 |
   | [!UICONTROL 일회성 기간] | 일회성 대상을 게시하려는 날짜 범위입니다. |
   | [!UICONTROL 필터] | 필터는 대상의 주요 입력입니다. 최대 20개의 필터를 추가할 수 있습니다. 이러한 필터는 `And` 또는 `Or` 연산자와 결합할 수 있습니다. |
   | [!UICONTROL 샘플 ID 보기] | 이 대상의 ID 샘플입니다. 검색 막대를 사용하여 샘플 ID를 검색합니다. |

   {style=&quot;table-layout:auto&quot;}

1. 데이터 미리보기를 해석합니다.

   대상 미리보기가 오른쪽 레일에 표시됩니다. 이렇게 하면 만든 대상에 대해 요약된 분석을 수행할 수 있습니다.

   ![](assets/data-preview.png)

   | 미리보기 설정 | 설명 |
   | --- | --- |
   | [!UICONTROL 데이터 미리보기 창] | 대상의 기간입니다. |
   | [!UICONTROL 총 사용자 수] | 이 대상의 총 사람 수에 대한 요약 번호입니다. 2억 명의 사람들이 이용할 수 있습니다. 대상자가 2억 명을 초과하는 경우 게시하기 전에 대상 크기를 줄여야 합니다. |
   | [!UICONTROL 대상 크기 제한] | 이 대상이 2억 개의 제한에서 얼마나 멀리 있는지를 보여줍니다. |
   | [!UICONTROL 예상 대상 반환] | 이 설정은 사이트로 돌아온 이 대상의 고객을 재타겟팅하는 데 유용합니다. (다시 말해, 이 데이터 세트에 다시 표시됩니다.) <p>여기에서 돌아올 수 있는 예상 고객 수에 대한 기간(다음 7일, 다음 2주, 다음 달)을 선택할 수 있습니다. |
   | [!UICONTROL 예상 반환] | 이 숫자는 드롭다운 목록에서 선택한 기간 동안 예상 재방문 고객 수를 제공합니다. 이 숫자를 예측하기 위해 이 대상의 이전 이탈률을 살펴봅니다. |
   | [!UICONTROL 지표 미리보기] | 이 설정을 사용하면 특정 지표를 확인하여 이 대상이 이 지표에 &#39;[!UICONTROL 매출]&#39; 또는 &#39;[!UICONTROL 사이트의 평균 시간]&#39; 지표의 합계 카운트와 지표가 나타내는 합계의 백분율을 제공합니다. 데이터 보기에서 사용할 수 있는 지표를 선택할 수 있습니다. |
   | [!UICONTROL 네임스페이스 포함됨] | 대상 내 사람과 연결된 특정 네임스페이스입니다. 예를 들면 ECID, CRM ID, 이메일 주소 등이 있습니다. |
   | [!UICONTROL 샌드박스] | 다음 [Experience Platform 샌드박스](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=ko-KR) 이 대상이 상주하는 객체입니다. 이 대상을 Platform에 게시하면 이 샌드박스의 제한 내에서만 사용할 수 있습니다. |

   {style=&quot;table-layout:auto&quot;}

1. 대상 구성을 두 번 확인하고 를 클릭합니다 **[!UICONTROL 게시]**.

   모든 것이 제대로 작동하면 대상자가 게시되었다는 확인 메시지가 표시됩니다. 이 대상이 Experience Platform에 표시되는 데 1~2분 정도 걸립니다. ( 수백만 명의 구성원이 있는 대상이라도 5분 이내에 완료해야 합니다.)

1. 클릭 **[!UICONTROL AEP에서 대상 보기]** 동일한 메시지 내에서 및 [세그먼트 UI](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=en) Adobe Experience Platform. 자세한 내용은 아래 내용을 참조하십시오.

## Experience Platform에서 CJA 대상 사용

이제 CJA는 게시된 대상에서 모든 네임스페이스 및 ID 조합을 가져와 RTCP(실시간 고객 프로필)로 스트리밍합니다. CJA에서는 연결이 구성되었을 때 개인 ID로 선택된 것으로 기본 ID가 설정된 상태로 Experience Platform으로 대상을 보냅니다.

그런 다음 RTCP는 각 네임스페이스/ID 조합을 검사하고 해당 네임스페이스가 속할 수 있는 프로필을 찾습니다. 프로필은 기본적으로 연결된 네임스페이스, ID 및 장치의 클러스터입니다. 프로필을 찾으면 이 프로필의 다른 ID에 네임스페이스 및 ID를 세그먼트 멤버십 속성으로 추가합니다. 이제, 예를 들어 &quot;user@adobe.com&quot;은 모든 장치 및 채널에서 타깃팅할 수 있습니다. 프로필이 없으면 새 프로필이 만들어집니다.

**[!UICONTROL 세그먼트]** > **[!UICONTROL 세그먼트 만들기]** > **[!UICONTROL 대상]** 탭 > **[!UICONTROL CJA 대상]**&#x200B;으로 이동하여 플랫폼에서 CJA 대상을 볼 수 있습니다.

CJA 대상을 AEP 세그먼트에 대한 세그먼트 정의로 드래그할 수 있습니다.

![](assets/audiences-aep.png)

## 사용자가 CJA에서 더 이상 대상 구성원이 아닌 경우 어떻게 됩니까?

이 경우 종료 이벤트가 CJA의 Experience Platform으로 전송됩니다.

## 다음 단계

* 이 대상자를 관리하려면 [관리 UI](/help/components/audiences/manage.md).
