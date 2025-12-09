---
title: Customer Journey Analytics에서 Experience Platform 대상 분석
description: Customer Journey Analytics에서 Experience Platform 대상을 분석하는 방법을 알아봅니다.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: f23775342a29d758b478206a77386e18a58312a6
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# Customer Journey Analytics에서 Experience Platform 대상 분석 {#analyze-audiences-RTCDP}

[대상 분석 구성을 만들기](/help/connections/audience-analysis/audience-analysis-configure.md)하면 대상 데이터를 만들도록 구성한 데이터 보기에서 새 차원으로 사용할 수 있게 됩니다. 대상 분석 차원이 추가된 데이터 보기에 액세스할 수 있는 경우 Analysis Workspace의 어느 곳에서든 새 대상 차원을 사용할 수 있습니다.

## 대상 개요 템플릿 사용

대상 개요 템플릿은 Customer Journey Analytics에서 사용할 수 있습니다.

<!-- Can you also use the new audience dimensions in any project, regardless of whether it's a template? I assume so -->

<!-- What are the names of the new dimensions? Are they customized to whatever your audience names are in AEP, or are they always the same? Are they the dimensions available in the Audience overview template? (Audience Name, Audience Origin, Exited Audience Name, Exited Audience Origin; Audience Description, Exited Audience Description). Metrics included (Distinct Audiences) -->

대상 개요 템플릿에 액세스하는 방법에 대한 자세한 내용은 [템플릿 사용](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template)에서 [템플릿 액세스 및 실행](/help/analysis-workspace/templates/use-templates.md)을 참조하십시오.

대상 개요 템플릿에는 다음 패널이 포함되어 있습니다.

## 사용 개요 패널

선택한 데이터 보기와 연결된 사용 이벤트가 있는 모든 대상의 데이터를 표시합니다. 대상자 멤버십 데이터는 매일 Experience Platform에서 업데이트됩니다. 어제 데이터는 항상 표시되므로 패널 날짜 범위를 변경하면 데이터가 부정확해집니다.

이 패널의 표를 사용하여 대상 동작을 더 잘 이해할 수 있습니다. 선택한 데이터 보기에서 대상 설명 차원을 드래그하여 분류로 추가합니다. 또는 다른 상호 작용 차원(예: 페이지, 작업 등)을 분류로 사용합니다.

## 상위 대상 원본 패널

대상이 만들어진 위치, RTCDP, Customer Journey Analytics 등에서 표시합니다.

이 패널의 표를 사용하여 대상자 출처가 다른 요인에 어떻게 영향을 미칠 수 있는지 더 잘 이해하십시오. 선택한 데이터 보기에서 대상 이름 차원을 드래그하여 분류로 추가합니다. 또는 다른 상호 작용 차원(예: 페이지, 작업 등)을 분류로 사용합니다.

## 대상 겹치기 패널

선택한 데이터 보기와 연결된 사용 이벤트가 있는 모든 대상의 데이터를 표시합니다. 어제 데이터는 항상 표시되므로 패널 날짜 범위를 변경하면 데이터가 부정확해집니다.

이 패널의 표에서 최대 3개의 대상을 선택하여 해당 벤 다이어그램에서 대상이 어떻게 겹치는지 확인합니다.

## 종료된 대상자 사용 패널

선택한 데이터 보기와 연결된 사용 이벤트를 사용하여 종료한 모든 대상의 데이터를 표시합니다. 어제 데이터는 항상 표시되므로 패널 날짜 범위를 변경하면 데이터가 부정확해집니다. &quot;종료한 대상자&quot;는 어제 사용 이벤트가 남아 있거나 종료한 사람이 속한 대상입니다.

이 패널의 표를 사용하여 대상 동작을 더 잘 이해할 수 있습니다. 선택한 데이터 보기에서 종료한 대상 설명 차원을 드래그하여 분류로 추가합니다. 또는 다른 상호 작용 차원 또는 지표(예: 페이지, 작업 등)를 분류로 사용합니다.

## 종료한 상위 대상 원본 패널

RTCDP, Customer Journey Analytics 등에서 종료한 각 대상이 원래 만들어진 위치를 표시합니다.

이 패널의 표를 사용하여 대상자 출처가 다른 요인에 어떻게 영향을 미칠 수 있는지 더 잘 이해하십시오. 선택한 데이터 보기에서 종료한 대상 이름 차원을 드래그하여 분류로 추가합니다. 또는 다른 상호 작용 차원 또는 지표(예: 페이지, 작업 등)를 분류로 사용합니다.








