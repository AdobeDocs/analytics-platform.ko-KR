---
title: 범위 구성 요소 설정
description: 전체 모집단 보고를 위해 구성 요소의 범위가 지정되는 방법을 구성합니다.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
    internal-label: Data views
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 18%
---

# 범위 구성 요소 설정 {#scope-component-settings}

>[!CONTEXTUALHELP]
>id="dataview_component_metric_scope"
>title="범위"
>abstract="보고서에서 사용될 때 구성 요소의 범위가 설정되는 방법을 결정합니다. 이벤트 기반, 프로필 기반 또는 합계 기반 중에서 선택할 수 있습니다."

지표 구성 요소의 범위는 구성 요소가 보고서에서 사용되는 방식을 결정합니다.

| 범위 | 설명 |
|---|---|
| 이벤트 기반 | 지표 구성 요소의 범위는 이벤트를 기반으로 합니다. |
| 프로필 기반 | 지표 구성 요소의 범위는 프로필을 기반으로 합니다. 구성 요소를 보고에 사용하면 지표는 패널에 적용되는 날짜 범위와 관계없이 프로필 데이터에서 모집단을 반환합니다. 날짜 필터 및 날짜 범위 비교는 이 지표의 보고에 영향을 주지 않습니다. |
| 총계 기반 | 지표 구성 요소의 범위는 프로필 및 이벤트를 기반으로 합니다. 구성 요소를 보고에 사용하면 지표는 패널에 적용되는 날짜 범위와 관계없이 프로필 및 이벤트 데이터의 모집단을 반환합니다. 날짜 필터 및 날짜 범위 비교는 이 지표의 보고에 영향을 주지 않습니다. |

