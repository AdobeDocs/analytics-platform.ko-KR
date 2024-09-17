---
description: 프로젝트 구성 요소가 특정 임계값에 도달하면 경고를 받습니다.
title: 경고 만들기(Analysis Workspace)
feature: Workspace Basics
role: User, Admin
source-git-commit: 4155f486c8398b75c2bed41d93562483d35c1477
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 22%

---

# 경고 만들기

>[!NOTE]
>
>지능형 경고는 모든 고객이 사용할 수 있습니다. 그러나 지능형 경고 내에서 예외 항목 탐지를 사용하려면 Select, Prime 또는 Ultimate Customer Journey Analytics이 있어야 합니다.

Customer Journey Analytics의 지능형 경고(또는 &quot;경고&quot;)를 사용하면 데이터에서 비정상 이벤트가 발생할 때 즉시 알림을 받을 수 있습니다.

지능형 경고에 대한 자세한 개요 정보는 [지능형 경고 개요](/help/components/c-intelligent-alerts/intelligent-alerts.md)를 참조하십시오.

경고를 만들려면 다음 작업을 수행하십시오.

1. 경고 빌더에 액세스하여 경고 만들기를 시작합니다. <!-- add this back in after the other methods are available like in AA and make a bulleted list: "You can access the alert builder in any of the following ways:" --> Customer Journey Analytics에서 **[!UICONTROL 구성 요소]** > [!UICONTROL **경고**] > **[!UICONTROL 새 경고 만들기]**&#x200B;를 선택합니다.

   경고 빌더가 표시됩니다. 이 인터페이스는 Analytics에 세그먼트 또는 계산된 지표를 만든 사용자에게 익숙합니다.

   ![](assets/alert-builder.png)

1. 다음 옵션을 지정하여 경고를 구성합니다.

   | 옵션 | 설명 |
   |---------|----------|
   | [!UICONTROL **제목**] | 경고 이름을 지정합니다. 경고 이름에는 보고서 또는 지표 임계값 이름이 포함될 수 있습니다. |
   | [!UICONTROL **설명(선택 사항)**] | 경고에 대한 설명을 지정합니다. |
   | [!UICONTROL **시간 세부기간**] | 지표를 확인할 빈도(일별, 주별 또는 월별)를 선택합니다.<p><b>참고:</b>사용자 지정 달력이 있는 데이터 보기의 경우 경고 빌더에서 월별 세부기간을 지원하지 않습니다.<!--true?--></p> |
   | [!UICONTROL **수신자**] | 경고를 전송할 대상을 지정합니다. 경고는 Analytics 사용자, Analytics 그룹, 원시 이메일 주소 또는 전화번호에 보낼 수 있습니다.<p><b>중요:</b>전화 번호 앞에는 &quot;+&quot;와 [국가 코드](https://countrycode.org/)가 있어야 합니다.</p><p>경고가 트리거된 후 사용자가 받는 이메일은 다음과 유사합니다.</p><p>![경고 전자 메일](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **만료 날짜**] | 경고가 만료될 날짜 및 시간을 설정합니다. |
   | [!UICONTROL **지연**] | 데이터가 완료되고 Customer Journey Analytics에서 보고할 수 있기까지 필요한 시간은 조직에 따라 다르며, 일반적으로 데이터 이벤트 시간보다 3~9시간 정도 지난 시간입니다. 경고가 정확하게 표시되려면 지정된 이벤트 범위에 대한 이벤트 데이터가 완료되어야 합니다. 즉, Adobe은 더 이상 지정된 이벤트 범위에 대한 이벤트 데이터를 받지 않습니다.<p>이러한 수집 시간 지연을 감안하기 위해 경고는 전송되기 전에 기본 지연 시간인 9시간을 갖습니다.</p><p>9시간의 기본 지연을 0에서 24시간 사이의 어느 곳으로든 조정할 수 있습니다. 그러나 지연 시간을 9시간 미만으로 줄이면 불완전한 데이터에 대해 보고하고 있으며, 이로 인해 경고 정보가 부정확해질 수 있습니다.</p><p>지연 시간을 줄일 때는 다음 사항을 고려하십시오.</p><ul><li>**데이터 가용성과 데이터 완전성 비교**: 일부 데이터는 더 빨리 보고할 수 있지만 모든 일괄 처리 데이터는 3~9시간 후에 Platform 데이터 세트로 수집됩니다. 경고가 정확하려면 데이터 세트에서 사용 가능한 모든 일괄 처리 데이터를 사용하여 데이터 수집을 완료해야 합니다.</li><li>**데이터 집합에서 데이터를 완료하고 사용할 수 있는 데 걸리는 시간을 결정합니다**: 조직별로 데이터 수집 시간이 다릅니다. 경고 게재를 위해 선택한 지연 시간이 Platform 데이터 집합 <!--add link? -->에서 배치 데이터를 사용할 수 있는 데 걸리는 시간과 동일하거나 덜 빈번한지 확인하십시오.</li><p>**팁:** 모든 일괄 처리 데이터를 완료하여 Platform 데이터 세트로 수집하는 데 필요한 시간을 가장 정확하게 파악하는 방법은 조직의 데이터 엔지니어와 상담하는 것입니다.</p><p>또는 Analysis Workspace에서 다음 자유 형식 테이블을 만들어 조직의 배치 배달을 Platform 데이터 세트에서 사용할 수 있는 데 걸리는 시간에 대한 일반적인 아이디어를 얻을 수 있습니다.</p><ol><li>Analysis Workspace의 자유 형식 테이블에서 [!UICONTROL **이벤트**] 지표와 [!UICONTROL **일**] 차원을 추가합니다.</li><li>[!UICONTROL **시간**] 차원을 사용하여 [!UICONTROL **일**] 차원을 분류합니다.<p>데이터가 없는 시간은 0으로 표시됩니다.</p></li></ol><li>**계산에서 오류 고려**: 기본 지연 시간을 줄이는 경우 데이터 수집의 완전성을 위해 조직에서 걸리는 시간보다 최소 1시간 이상 지연하도록 구성하는 것이 좋습니다. 예를 들어 데이터 수집이 완료되기 전에 3시간이 지연되는 경우 지연을 4시간으로 설정해야 합니다.</li></ul><p>자세한 내용은 문서 [지능형 경고 기능 비교: Customer Journey Analytics 및 Adobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)에서 [데이터 수집 시간이 Customer Journey Analytics에 따라 다름](/help/components/c-intelligent-alerts/alerts-feature-comparison.md#data-ingestion-times-vary-in-customer-journey-analytics)을(를) 참조하십시오. |
   | [!UICONTROL **다음 경우에 경고 보내기**] | [!UICONTROL **다음 지표 트리거 중 하나**]: 여기에 지표(계산된 지표 포함)를 끌어다 놓아 경고에 대한 트리거를 만듭니다.<p>경고에 있는 일부 지표, 차원 또는 세그먼트가 현재 선택한 데이터 보기와 호환하지 않을 경우 **&quot;호환되지 않는 구성 요소&quot;** 메시지가 표시됩니다.</p><p>경고를 설정하기 전에 지표가 초과되는 임계값을 결정합니다. 이 값을 임계값으로 설정한 후 다음 조건 중 하나로 설정할 수 있습니다.</p><ul><li>예외 항목이 있음</li><li>예외 항목이 예상 이상임</li><li>예외 항목이 예상 미만임</li><li>위 또는 같음</li><li>아래 또는 같음</li><li>변경</li><li>90%, 95%, 99%, 99.75% 및 99.9%의 임계값을 설정할 수 있습니다.</li></ul><p>[!UICONTROL **다음 필터 사용**]: 세그먼트 또는 차원을 끌어서 놓아 필터를 추가합니다. 예를 들어 &quot;모바일 디바이스만&quot; 세그먼트를 추가한다는 것은 모바일 디바이스에 대해서만 규칙이 트리거됨을 의미합니다. AND 문을 사용하여 필터를 추가할 수 있습니다. 톱니바퀴 아이콘을 클릭하여 AND 또는 OR 규칙을 추가할 수 있습니다.</p><p>사용 사례에 대해서는 [지능형 경고 - 사용 사례](/help/components/c-intelligent-alerts/alerts-use-cases.md)를 참조하십시오.</p> |
   | [!UICONTROL **미리보기**] | 대화형 경고 미리보기에서는 경고가 과거의 경험을 기반으로 얼마나 자주 표시되는지를 근사적으로 보여 줍니다.<p>예를 들어 시간 세부 기간을 매일로 설정하는 경우, 미리보기에서는 경고가 지난 30 또는 31일 동안 특정 지표 x 배수에 대해 트리거됨을 알 수 있습니다.</p><p>너무 많은 경고가 트리거될 것 같으면 [경고 관리자](/help/components/c-intelligent-alerts/alert-manager.md)에서 임계값을 조정할 수 있습니다.</p><p>![](assets/alert_preview.png)</p> |

1. [!UICONTROL **저장**]&#x200B;을 선택합니다.

