---
title: 보고 활동 관리자에서 보고 요청 취소
description: 보고 활동 관리자를 사용하여 최대 보고 시간 동안 용량 문제를 진단하고 해결하는 방법에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 1680e6115a75a0dd78f07aa0bb409b19b3585a78
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 8%

---

# 보고 활동 관리자에서 보고 요청 취소

{{release-limited-testing}}

다음 [!UICONTROL 활동 관리자 보고] 관리자가 보고 요청을 신속하게 진단 및 취소하여 최대 보고 시간 동안의 보고 용량 문제를 해결할 수 있습니다.

보고 요청을 취소할 때는 다음 사항을 고려하십시오.

* 특정 요청을 취소하거나 특정 사용자의 모든 요청을 취소하거나 특정 프로젝트와 관련된 모든 요청을 취소할 수 있습니다.

* 요청을 취소할 때 주어진 기간 동안 후속 요청을 제한하도록 선택할 수도 있습니다.

  후속 요청을 제한하면 작업이 다음에 기록됩니다. [감사 로그](/help/privacy/audit-log.md) EMBARGO의 작업 이름으로.

* 다음과 같은 경우에는 요청을 취소할 수 없습니다. [!UICONTROL **사용자**] 요청의 열이 다음으로 표시됨 [!UICONTROL **인식되지 않음**]. 이 경우 사용자가 관리 권한이 없는 로그인 회사에 속해 있음을 의미합니다.

주요 이점 및 권한 요구 사항을 포함하여 보고 활동 관리자에 대한 자세한 내용은 다음을 참조하십시오. [보고 활동 관리자 개요](/help/reporting-activity-manager/reporting-activity-overview.md).

## 특정 요청 취소

보고 용량이 큰 개별 요청을 취소할 수 있습니다. 요청을 취소할 때 주어진 기간 동안 추가로 제한하도록 선택할 수 있습니다.

1. Customer Journey Analytics에서 **[!UICONTROL 도구]** > **[!UICONTROL 활동 관리자 보고]**.

1. 보고 요청을 취소할 연결을 선택합니다. <!--double-check this step-->

   이 페이지에서 사용할 수 있는 데이터에 대한 자세한 내용은 [보고 활동 관리자에서 보고 활동 보기](/help/reporting-activity-manager/reporting-activity.md).

1. 다음 항목 선택 [!UICONTROL **요청**] 탭을 선택한 다음 하나 이상의 요청을 선택합니다.

   <!-- add screenshot -->

1. 선택 [!UICONTROL **요청 취소**].

   다음 [!UICONTROL **취소 _x_ 보고서 요청**] 대화 상자가 표시됩니다.

1. 취소 메시지 필드에는 요청이 취소될 때 사용자에게 표시되는 메시지가 표시됩니다. 기본 메시지가 제공됩니다. 기본 메시지를 업데이트하여 추가 세부 정보를 제공할 수 있습니다.

1. (선택사항) 지정된 기간 동안 미래 요청을 제한하려면

   1. 옵션을 활성화한 대상 [!UICONTROL **후속 요청 제한**].

      ![후속 요청 제한](assets/restrict-subsequent-requests.png)

   1. 다음 선택 사항 중 하나를 선택합니다.

      | 옵션 | 함수 |
      |---------|----------|
      | [!UICONTROL **사용자 및 프로젝트**] | 선택한 요청과 연결된 사용자의 경우 연결된 프로젝트에 대한 보고 요청 실행이 일시적으로 제한됩니다. |
      | [!UICONTROL **사용자**] | 선택한 요청과 관련된 사용자가 보고 요청 제출에서 일시적으로 사용이 제한됩니다. |
      | [!UICONTROL **프로젝트**] | 선택한 요청과 관련된 프로젝트가 모든 보고 요청에서 일시적으로 사용이 제한됩니다. |
      | [!UICONTROL **다음에 대해 제한**] | 요청이 제한되는 기간을 선택합니다. 1분(기본값), 5분, 10분, 15분 또는 30분을 선택할 수 있습니다. <!-- double-check this --><p>제한을 설정한 후에는 조기에 제거할 수 없습니다.</p> |

      {style="table-layout:auto"}

1. 선택 [!UICONTROL **취소 상태로 계속 진행**].

   요청이 취소되었음을 사용자에게 알리는 알림이 Analysis Workspace에 표시됩니다. Analysis Workspace에서 표시되는 방법에 대한 자세한 내용은 [사용자가 취소된 보고서에 액세스할 때의 경험](#experience-when-users-access-a-cancelled-report).

## 사용자별 요청 취소

한 명 이상의 사용자와 연결된 모든 요청을 취소할 수 있습니다. 사용자와 연결된 요청을 취소할 때 지정된 기간 동안 해당 사용자의 요청을 추가로 제한할 수 있습니다.

1. Customer Journey Analytics에서 **[!UICONTROL 도구]** > **[!UICONTROL 활동 관리자 보고]**.

1. 보고 요청을 취소할 연결을 선택합니다. <!--double-check this step-->

   이 페이지에서 사용할 수 있는 데이터에 대한 자세한 내용은 [보고 활동 관리자에서 보고 활동 보기](/help/reporting-activity-manager/reporting-activity.md).

1. 다음 항목 선택 [!UICONTROL **사용자**] 탭을 누른 다음 사용자를 한 명 이상 선택합니다.

   <!-- add screenshot -->

1. 선택 [!UICONTROL **요청 취소**].

   다음 [!UICONTROL **취소 _x_ x 사용자의 보고서 요청**] 대화 상자가 표시됩니다.

1. 취소 메시지 필드에는 요청이 취소될 때 사용자에게 표시되는 메시지가 표시됩니다. 기본 메시지가 제공됩니다. 기본 메시지를 업데이트하여 추가 세부 정보를 제공할 수 있습니다.

1. (선택사항) 지정된 기간 동안 미래 요청을 제한하려면

   1. 옵션을 활성화한 대상 [!UICONTROL **후속 요청 제한**]

      ![사용자별 후속 요청 제한](assets/restrict-subsequent-requests-user.png)

   1. 다음 선택 사항 중 하나를 선택합니다.

      | 옵션 | 함수 |
      |---------|----------|
      | [!UICONTROL **사용자 및 프로젝트**] | 선택한 사용자는 연결된 프로젝트에 대한 보고 요청을 수행할 수 없도록 일시적으로 제한됩니다. <p>이것은 가장 덜 제한적인 옵션입니다.</p> |
      | [!UICONTROL **사용자**] | 선택한 사용자의 보고 요청이 일시적으로 제한됩니다. |
      | [!UICONTROL **프로젝트**] | 선택한 사용자와 관련된 프로젝트는 모든 사용자의 보고 요청에서 제한됩니다. |
      | [!UICONTROL **다음에 대해 제한**] | 요청이 제한되는 기간을 선택합니다. 1분(기본값), 5분, 10분, 15분 또는 30분을 선택할 수 있습니다. <!--double-check this--> <p>제한을 설정한 후에는 조기에 제거할 수 없습니다.</p> |

      {style="table-layout:auto"}

1. 선택 [!UICONTROL **취소 상태로 계속 진행**].

   요청이 취소되었음을 사용자에게 알리는 알림이 Analysis Workspace에 표시됩니다. Analysis Workspace에서 표시되는 방법에 대한 자세한 내용은 [사용자가 취소된 보고서에 액세스할 때의 경험](#experience-when-users-access-a-cancelled-report).

## 프로젝트별 요청 취소

하나 이상의 프로젝트와 연결된 모든 요청을 취소할 수 있습니다. 프로젝트와 연결된 요청을 취소할 때 지정된 기간 동안 해당 프로젝트와 연결된 요청을 추가로 제한할 수 있습니다.

1. Customer Journey Analytics에서 **[!UICONTROL 도구]** > **[!UICONTROL 활동 관리자 보고]**.

1. 보고 요청을 취소할 연결을 선택합니다. <!--double-check this step-->

   이 페이지에서 사용할 수 있는 데이터에 대한 자세한 내용은 [보고 활동 관리자에서 보고 활동 보기](/help/reporting-activity-manager/reporting-activity.md).

1. 다음 항목 선택 [!UICONTROL **프로젝트**] 탭을 누른 다음 하나 이상의 프로젝트를 선택합니다.

   <!-- add screenshot -->

1. 선택 [!UICONTROL **요청 취소**].

   다음 [!UICONTROL **취소 _x_ x 프로젝트의 보고서 요청**] 대화 상자가 표시됩니다.

1. 취소 메시지 필드에는 요청이 취소될 때 사용자에게 표시되는 메시지가 표시됩니다. 기본 메시지가 제공됩니다. 기본 메시지를 업데이트하여 추가 세부 정보를 제공할 수 있습니다.

1. (선택사항) 지정된 기간 동안 미래 요청을 제한하려면

   1. 옵션을 활성화한 대상 [!UICONTROL **후속 요청 제한**].

      ![프로젝트별로 후속 요청 제한](assets/restrict-subsequent-requests-project.png)

   1. 다음 선택 사항 중 하나를 선택합니다.

      | 옵션 | 함수 |
      |---------|----------|
      | [!UICONTROL **사용자 및 프로젝트**] | 선택한 프로젝트는 연결된 사용자의 보고 요청에서 일시적으로 제한됩니다.<p>이것은 가장 덜 제한적인 옵션입니다.</p> |
      | [!UICONTROL **사용자**] | 선택한 프로젝트와 연결된 사용자의 보고 요청이 제한됩니다. |
      | [!UICONTROL **프로젝트**] | 선택한 프로젝트는 모든 사용자의 보고 요청에서 일시적으로 제한됩니다. |
      | [!UICONTROL **다음에 대해 제한**] | 요청이 제한되는 기간을 선택합니다. 1분(기본값), 5분, 10분, 15분 또는 30분을 선택할 수 있습니다. <!--double-check this--> <p>제한을 설정한 후에는 조기에 제거할 수 없습니다.</p> |

      {style="table-layout:auto"}

1. 선택 [!UICONTROL **취소 상태로 계속 진행**].

   요청이 취소되었음을 사용자에게 알리는 알림이 Analysis Workspace에 표시됩니다. Analysis Workspace에서 표시되는 방법에 대한 자세한 내용은 [사용자가 취소된 보고서에 액세스할 때의 경험](#experience-when-users-access-a-cancelled-report).

## 애플리케이션별 요청 취소

하나 이상의 애플리케이션과 연결된 모든 요청을 취소할 수 있습니다. 응용 프로그램과 연관된 요청을 취소할 때 지정된 기간 동안 해당 응용 프로그램과 연관된 요청을 추가로 제한할 수 있습니다.

애플리케이션에는 다음이 포함됩니다.

* Analysis Workspace UI
* Workspace 예약된 프로젝트
* Report Builder
* 빌더 UI: 세그먼트, 계산된 지표, 주석, 대상자 등
* 2.0 API의 API 호출
* 지능형 경고
* 전체 테이블 내보내기
* 모든 사람과 공유 링크
* 안내식 분석
* Analytics 보고 엔진을 쿼리하는 다른 모든 애플리케이션

응용 프로그램별 요청을 취소하려면 다음을 수행합니다.

1. Customer Journey Analytics에서 **[!UICONTROL 도구]** > **[!UICONTROL 활동 관리자 보고]**.

1. 보고 요청을 취소할 연결을 선택합니다. <!--double-check this step-->

   이 페이지에서 사용할 수 있는 데이터에 대한 자세한 내용은 [보고 활동 관리자에서 보고 활동 보기](/help/reporting-activity-manager/reporting-activity.md).

1. 다음 항목 선택 [!UICONTROL **애플리케이션**] 탭을 누른 다음 하나 이상의 응용 프로그램을 선택합니다.

   <!-- add screenshot -->

1. 선택 [!UICONTROL **요청 취소**].

   다음 [!UICONTROL **취소 _x_ x 프로젝트의 보고서 요청**] 대화 상자가 표시됩니다.

1. 취소 메시지 필드에는 요청이 취소될 때 사용자에게 표시되는 메시지가 표시됩니다. 기본 메시지가 제공됩니다. 기본 메시지를 업데이트하여 추가 세부 정보를 제공할 수 있습니다.

1. (선택사항) 지정된 기간 동안 미래 요청을 제한하려면

   1. 옵션을 활성화한 대상 [!UICONTROL **후속 요청 제한**]

      ![애플리케이션별로 후속 요청 제한](assets/restrict-subsequent-requests-application.png)

   1. 다음 선택 사항 중 하나를 선택합니다.

      | 옵션 | 함수 |
      |---------|----------|
      | [!UICONTROL **사용자 및 프로젝트**] | 선택한 응용 프로그램은 연결된 사용자 및 프로젝트에 의한 모든 보고 요청에서 일시적으로 제한됩니다.<p>이것은 가장 덜 제한적인 옵션입니다.</p> |
      | [!UICONTROL **사용자**] | 선택한 애플리케이션과 연결된 사용자의 보고 요청이 제한됩니다. |
      | [!UICONTROL **프로젝트**] | 선택한 애플리케이션과 연결된 프로젝트는 모든 사용자의 보고 요청에서 제한됩니다. |
      | [!UICONTROL **다음에 대해 제한**] | 요청이 제한되는 기간을 선택합니다. 1분(기본값), 5분, 10분, 15분 또는 30분을 선택할 수 있습니다. <!--double-check this--> <p>제한을 설정한 후에는 조기에 제거할 수 없습니다.</p> |

      {style="table-layout:auto"}

1. 선택 [!UICONTROL **취소 상태로 계속 진행**].

   요청이 취소되었음을 사용자에게 알리는 알림이 애플리케이션에 표시됩니다(예: Analysis Workspace). Analysis Workspace에서 표시되는 방법에 대한 자세한 내용은 [사용자가 취소된 보고서에 액세스할 때의 경험](#experience-when-users-access-a-cancelled-report).

## 사용자가 취소된 보고서에 액세스할 때의 경험

Analysis Workspace에서 사용자가 취소의 영향을 받는 보고서 또는 시각화에 액세스하려고 하면 다음 메시지가 표시됩니다.

### 프로젝트에 대한 메시지

사용자가 취소의 영향을 받는 프로젝트에 액세스하려고 하면 보고서가 일시적으로 제한되었음을 알리는 메시지가 표시됩니다.

![프로젝트 취소 메시지](assets/workspace-canceled-report.png)

### 시각화에 대한 메시지

사용자가 취소의 영향을 받는 시각화에 액세스하려고 하면 보고서에 대한 데이터 처리가 일시적으로 제한됨을 알리는 메시지가 표시됩니다.

![시각화 취소 메시지](assets/workspace-cancelled-visualization.png)