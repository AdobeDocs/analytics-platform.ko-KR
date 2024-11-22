---
description: Analysis Workspace에서 기본 템플릿을 사용하는 방법에 대한 개요입니다.
title: 템플릿 사용
feature: Workspace Basics
role: User, Admin
hide: true
hidefromtoc: true
source-git-commit: 96844fae07734e979e9dd4689d5eded6a7a3b926
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 4%

---

# 템플릿 만들기 및 관리

관리자는 템플릿을 만들고 이를 저장하여 로그인 회사의 다른 사용자가 사용할 수 있도록 할 수 있습니다.

[템플릿 사용](/help/analysis-workspace/templates/use-templates.md)에 설명된 대로 로그인 회사의 직원들이 이러한 회사 템플릿을 사용할 수 있습니다.

## 템플릿 만들기

<!-- is this only admins? -->

로그인 회사 직원이 사용할 수 있는 새 템플릿을 만들려면 다음 작업을 수행하십시오.

1. Analysis Workspace에서 프로젝트를 원하는 상태로 빌드합니다.

1. [!UICONTROL **프로젝트**] > **[!UICONTROL 템플릿으로 저장...]**&#x200B;을 선택합니다.

   ![회사 보고서](assets/company-template-save.png)

1. [!UICONTROL 템플릿으로 저장] 대화 상자에서 다음 정보를 지정하십시오.

   | 필드 | 설명 |
   |---------|----------|
   | **[!UICONTROL 이름]** | 템플릿에 대한 수사적 이름을 입력합니다. |
   | **[!UICONTROL 설명]** | 템플릿에 대해 의도된 용도에 대해 설명하는 간단한 설명을 입력합니다. |
   | **[!UICONTROL 이 템플릿을 사용하는 이유]** | 조직의 사용자에게 이 템플릿을 사용할 수 있는 방법을 알려 주는 간단한 설명을 입력하십시오. |
   | **[!UICONTROL 채널]** | 이 템플릿에 적용되는 적용 가능한 채널을 선택합니다. 여러 채널을 선택할 수 있습니다. **[!UICONTROL 웹]**, **[!UICONTROL 모바일]**, **[!UICONTROL 크로스 채널]**, **[!UICONTROL 콜 센터]** 및 **[!UICONTROL 매장]**.<p>선택한 사항에 따라 템플릿 표시 위치와 조직 템플릿 페이지에서 액세스하는 사용자에게 적용되는 필터가 결정됩니다.</p> |
   | **[!UICONTROL 사용 사례]** | 이 템플릿에 적용되는 사용 사례를 선택합니다. **[!UICONTROL 참여]**, **[!UICONTROL 전환]**, **[!UICONTROL 대상]** 및 **[!UICONTROL 획득]**&#x200B;과 같은 여러 사용 사례를 선택할 수 있습니다. <p>선택한 사항에 따라 템플릿 표시 위치와 조직 템플릿 페이지에서 액세스하는 사용자에게 적용되는 필터가 결정됩니다.</p> |
   | **[!UICONTROL 태그]** | 템플릿에 적용할 태그를 지정합니다. 사용자는 추가한 태그로 템플릿 목록을 필터링할 수 있습니다. |

1. [!UICONTROL **템플릿으로 저장**]&#x200B;을 선택합니다.

사용자가 템플릿을 기반으로 프로젝트를 만드는 방법에 대한 자세한 내용은 [템플릿 사용](/help/analysis-workspace/templates/use-templates.md)에서 [템플릿을 기반으로 프로젝트 만들기](/help/analysis-workspace/templates/use-templates.md#create-a-project-based-on-a-template)를 참조하십시오.

## 회사 템플릿 관리

관리자는 회사 템플릿을 삭제, 이름 변경, 태그 지정 및 승인할 수 있습니다.

회사 템플릿을 표시하고 관리하려면 다음 작업을 수행하십시오.

1. Analysis Workspace에서 [!UICONTROL **Workspace**] 탭을 선택한 다음 왼쪽 레일에서 **[!UICONTROL 프로젝트 탭]**&#x200B;을 선택합니다.

1. 필터 아이콘을 선택하여 프로젝트 목록을 필터링합니다.

1. 필터 레일에서 **기타 필터**&#x200B;를 선택한 다음 **회사 템플릿**&#x200B;을 선택합니다.

   회사 템플릿 목록이 표시됩니다. 고정되지 않은 모든 일반 프로젝트는 표시되지 않습니다.

   템플릿 이름 앞에 있는 ![템플릿 아이콘](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg)으로 회사 템플릿을 식별할 수 있습니다.

   <!-- Update screenshot -->

   ![회사 템플릿 필터 표시](assets/company-reports-filter.png)

1. 템플릿 목록에서 하나 이상의 회사 템플릿을 선택합니다.

1. 사용 가능한 옵션을 보려면 템플릿 옆에 있는 **..** 줄임표 아이콘을 클릭합니다.

   <!-- Update screenshot -->

   ![회사 템플릿 작업](assets/company-reports-actions.png)

1. **[!UICONTROL 삭제]**, **[!UICONTROL 이름 바꾸기]**, **[!UICONTROL 태그]** 또는 **[!UICONTROL 승인]**)을 선택합니다.

1. (선택 사항) 필터 레일에서 일반 보기로 돌아가려면 **[!UICONTROL 회사 템플릿]**&#x200B;을 선택 취소합니다.

## 회사 템플릿 액세스

Adobe에서 제공하는 템플릿과 마찬가지로 조직의 직원이 만든 템플릿에 액세스할 수 있습니다.

회사 템플릿에 액세스하는 방법에 대한 자세한 내용은 [템플릿 사용](/help/analysis-workspace/templates/use-templates.md)에서 [템플릿 액세스 및 실행](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template)을 참조하십시오.
