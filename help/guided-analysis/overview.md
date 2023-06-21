---
title: 안내식 분석 개요
description: 제품 팀이 보고서와 통찰력을 쉽게 생성할 수 있도록 하는 Customer Journey Analytics의 데이터 분석 방법입니다.
exl-id: 6a8a92db-f030-424e-af9b-f8f6502084f6
source-git-commit: e2020d9194f7885f80671214829f06245bbab328
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 1%

---

# 안내식 분석 개요

{{release-limited-testing}}

가이드 분석은 제품 팀이 데이터 요구 사항을 신속하게 자체 처리할 수 있는 보고 형식으로, 이를 통해 더 많은 데이터 중심의 제품 결정을 내릴 수 있습니다. 다양한 분야의 사람들과 일하는 팀은 이러한 보고서를 사용하고 이해할 수 있도록 실시간으로 연결할 수 있습니다.

Analysis Workspace 및 모바일 스코어카드와 마찬가지로, 안내식 분석 보고서는 [데이터 보기](../data-views/data-views.md): 를 통해 Adobe Experience Platform의 데이터를 참조합니다. [연결](../connections/overview.md). 가이드 분석에서 만든 모든 보고서는 추가 조사를 위해 Analysis Workspace으로 원활하게 전송할 수 있습니다.

안내식 분석 보고서에는 현재 세 가지 분석 유형이 있습니다. [단계](analysis-types/funnel.md), [트렌드](analysis-types/trends.md), 및 [사용자 증가](analysis-types/user-growth.md). 이러한 각 분석 유형에는 이러한 각 보고서에 추가적인 통찰력을 제공하는 여러 보기 유형이 있습니다.

## 인터페이스

분석 유형에 관계없이 안내식 분석을 위한 인터페이스는 다음 기본 UI 요소로 구성됩니다.

1. **쿼리 레일**: 왼쪽의 이 레일을 사용하여 분석을 빌드합니다.
1. **차트**: 원하는 이벤트, 사람 또는 단계를 선택하면 데이터를 시각화하는 차트가 오른쪽에 표시됩니다.
1. **표**: 시각화에 사용된 숫자를 보여 주는 차트 아래의 표입니다.
1. **설정 및 인사이트**: 반환된 데이터를 사용자 정의할 수 있는 차트 위의 몇 가지 UI 요소입니다.

[UI 스크린샷]

안내식 분석에는 다음과 같은 인터페이스 부품이 포함됩니다.

| 인터페이스 미리 보기 | UI 요소 | 설명 |
| --- | --- | --- |
| [쿼리 레일의 스크린샷] | 쿼리 레일 | 보고서를 구성하는 원하는 구성 요소를 구성합니다. 서로 다른 분석 유형은 여러 쿼리 옵션을 공유합니다. 두 분석 유형이 쿼리 옵션을 공유하는 경우 분석 유형을 전환할 때 이월됩니다. 다음을 참조하십시오 [분석 유형](analysis-types/overview.md) 각 분석 유형의 쿼리 옵션에 대한 자세한 내용을 보려면 를 참조하십시오. |
| [차트의 스크린샷] | 차트 | 쿼리 레일 및 설정의 입력을 기반으로 반환되는 데이터의 시각화입니다. 표시되는 시각화는 차트 위의 보기 유형에 따라 다릅니다. 사용 가능한 보기 유형은 [분석 유형](analysis-types/overview.md) 쿼리 레일 위에 놓습니다. |
| [표의 스크린샷] | 표 | 쿼리 레일 및 설정의 입력을 기반으로 반환되는 데이터의 테이블 표현입니다. 테이블의 열은 차트 위의 보기 유형에 따라 다릅니다. 사용 가능한 보기 유형은 [분석 유형](analysis-types/overview.md) 쿼리 레일 위에 놓습니다. |
| [설정 스크린샷] | 설정 | 차트 및 테이블이 데이터를 반환하는 방법을 사용자 지정할 수 있는 차트 위의 몇 가지 옵션입니다.<ul><li>**보기 유형**: 제공된 에 대한 데이터를 제공할 수 있는 드롭다운 선택기 [분석 유형](analysis-types/overview.md) 다른 방식으로. 각 분석 유형에는 적어도 두 개의 보기 유형이 있습니다.</li><li>**차트 설정**: 차트의 모양과 사용할 이벤트를 세밀하게 조정합니다. 사용 가능한 옵션은 선택한 보기 유형에 따라 다릅니다.</li><li>**날짜 범위**: 보고서의 날짜 범위를 결정할 수 있는 달력 선택기입니다. 일부 분석 유형은 일별, 주별 또는 월별 등의 간격도 허용합니다.</li><li>**Insights**: 사용자가 보는 보고서에 따라 상황에 맞는 통찰력을 제공합니다. 오른쪽 상단의 전구 아이콘을 사용하여 이러한 통찰력을 표시하거나 숨길 수 있습니다.</li></ul> |
| [분석 메뉴의 스크린샷] | 분석 메뉴 | 중요한 작업을 제공하는 안내식 분석의 오른쪽 상단에 있는 명령입니다.<ul><li>**데이터 보기 선택기**: 이 분석에서 사용하는 데이터 보기를 변경합니다. 데이터 보기를 변경하면 쿼리 레일에서 사용할 수 있는 구성 요소도 변경됩니다.</li><li>**저장**: 분석을 저장합니다. 새 분석을 저장하는 경우 이름과 설명을 요청하는 모달 창이 나타납니다.</li><li>**다른 이름으로 저장**: 현재 분석과 별도로 분석을 저장하고 복사본을 만듭니다. 새 이름과 설명을 요청하는 모달 창이 나타납니다.</li><li>**Workspace에서 열기**: Analysis Workspace에서 현재 안내가 있는 분석을 다시 만듭니다. 작업 영역 프로젝트는 새 탭에서 만들어지므로 안내식 분석 내에서 작업하는 동안 중단이 발생하지 않습니다. 안내식 분석이 찾고 있는 융통성이나 특정 통찰력을 제대로 제공하지 못하는 경우 이 명령을 사용합니다. 예를 들어 [트렌드](analysis-types/trends.md) 한 세그먼트에 대한 세션 을 사용하고 다른 세그먼트에 대한 사람 을 사용하는 보고서입니다.</li><li>**PNG 다운로드**: 차트 그래픽을 로 다운로드 `.png`. 쿼리 레일 및 테이블은 그래픽에 포함되지 않습니다.</li><li>**SVG 다운로드**: 차트 그래픽을 로 다운로드 `.svg`. 쿼리 레일 및 테이블은 그래픽에 포함되지 않습니다.</li></ul> |

{style="table-layout:auto"}

## 프로비저닝

안내식 분석은 Adobe Product Analytics에 대한 유료 추가 기능인 Customer Journey Analytics의 일부입니다. 조직에서 이 기능을 사용하려면 Adobe 계정 팀에 문의하십시오.

Adobe은 향후 가이드 분석에 대한 권한을 제공할 계획입니다.

<!-- Once your organization is provisioned to use Guided analysis, product profile administrators can grant access to it in the Adobe Admin Console.

1. Log in to the [Adobe admin console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile to edit permissions.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Drag **[!UICONTROL Guided analysis]** from the list of [!UICONTROL Available Permission Items] to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**. -->
