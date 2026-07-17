---
title: Customer Journey Analytics에서 동의 정책 데이터 분석
description: 동의 정책 차원, 지표 및 템플릿을 사용하여 Analysis Workspace에서 방문자 동의 정책 멤버십을 보고하는 방법을 알아봅니다.
solution: Customer Journey Analytics
feature: Privacy
role: Admin, User
hold: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: 91cd8d3d5c290f52e4ae15713693be1fc83baa92
workflow-type: tm+mt
source-wordcount: 388
ht-degree: 2%

---

# 동의 정책 데이터 분석

Experience Platform 프로필 데이터 세트의 동의 정책 데이터를 Customer Journey Analytics 연결로 수집할 수 있습니다.

[동의 보고 및 필터링 구성을 만들고](/help/connections/consent-reporting-filtering/consent-configure.md)보고를 사용하면 구성된 연결의 데이터 보기에서 동의 정책 데이터를 새 구성 요소로 사용할 수 있습니다. 이러한 구성 요소가 있는 데이터 보기에 액세스할 수 있는 경우 Analysis Workspace의 어디에서나 이러한 구성 요소를 사용할 수 있습니다.

## 동의 정책 구성 요소

동의 보고는 데이터 보기에 다음 구성 요소를 추가합니다. 이러한 구성 요소는 프로필 데이터 세트의 `consentPoliciesIDMap` 필드에서 읽으며 정책 이름 및 설명은 동의 정책 조회 데이터 세트에서 가져옵니다.

### 차원

| 차원 | 설명 |
|---------|----------|
| **[!UICONTROL 동의 정책 ID]** | 방문자가 일치하는 동의 정책의 식별자입니다. |
| **[!UICONTROL 정책 이름]** | 동의 정책 조회 데이터 세트에서 동의 정책에 대한 친숙한 이름. |
| **[!UICONTROL 정책 설명]** | 동의 정책 조회 데이터 세트의 동의 정책에 대한 설명입니다. |

### 지표

| 지표 | 설명 |
|---------|----------|
| **[!UICONTROL 동의하는 방문자]** | 동의 정책과 일치하는 방문자의 수입니다. |
| **[!UICONTROL 동의가 있는 이벤트]** | 동의 정책과 일치하는 방문자와 연결된 이벤트 수입니다. |
| **[!UICONTROL 고유 동의 정책]** | 보고 기간에 표시되는 고유 동의 정책 수. |

### 파생 필드

파생 필드가 동의 정책 ID를 추출하기 위해 `consentPoliciesIDMap` 필드를 참조합니다. 이 파생 필드를 추가 동의 기반 차원의 기반으로 사용할 수 있습니다. 파생 필드에 대한 자세한 내용은 [파생 필드](/help/data-views/derived-fields/derived-fields.md)를 참조하십시오.

## Analysis Workspace에서 동의 정책 구성 요소 사용

동의 정책 멤버십을 보고하려면

1. Analysis Workspace에서 동의 보고에 대해 구성된 데이터 보기를 사용하는 프로젝트를 엽니다.

1. 구성 요소 패널에서 **[!UICONTROL 정책 이름]**&#x200B;과 같은 동의 정책 차원을 자유 형식 테이블로 끌어서 놓습니다.

1. **[!UICONTROL 동의를 받은 방문자]**&#x200B;와 같은 동의 지표를 테이블에 추가합니다.

1. 결과를 페이지 또는 채널과 같은 다른 차원으로 분류하여 동의를 얻은 방문자의 행동을 파악합니다.

## 동의 정책 분석 템플릿 사용

동의 보고를 위해 데이터 보기가 구성된 경우, Customer Journey Analytics은 동의 정책 분석 템플릿을 Analysis Workspace에서 자동으로 사용할 수 있도록 합니다. 이 템플릿은 방문자 동의 정책 멤버십에 대한 보고의 시작점을 제공합니다.

템플릿에 액세스하는 방법에 대한 자세한 내용은 [템플릿 액세스 및 실행](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template)을 참조하십시오.
