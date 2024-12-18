---
title: 제품 사용 개요
description: 조직에서 Customer Journey Analytics을 사용하는 방법에 대한 인사이트 및 보고서를 봅니다.
source-git-commit: 7d22c512e8e96963b288567704d2245e64411b10
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 6%

---

# 제품 사용 개요

{{release-limited-testing}}

제품 사용은 조직이 Customer Journey Analytics을 사용하는 방법에 대한 분석 데이터를 볼 수 있는 기능을 조직에 제공합니다. Customer Journey Analytics을 사용하는 모든 조직에서 사용할 수 있습니다. 활성화되면 다음 Adobe Experience Platform 구성 요소가 자동으로 생성되고 연결됩니다. 이러한 구성 요소는 모두 시스템 소유이며 읽기 전용이며 편집할 수 없습니다.

* Adobe Experience Platform의 스키마
* Adobe Experience Platform의 데이터 세트
* Customer Journey Analytics 중인 연결
* Customer Journey Analytics의 데이터 보기

활성화되면 모든 데이터 수집 및 설정이 자동으로 구성됩니다. 사용자가 Analysis Workspace에서 작업을 수행할 때마다 해당 작업이 추적되어 보고에 사용할 수 있습니다.

>[!IMPORTANT]
>
>이 기능은 Adobe Experience Platform의 계약 행 제한에 포함됩니다. 활성화하기 전에 조직에서 이 기능으로 생성된 데이터를 수용할 수 있는지 확인하십시오.

## 사용 가능한 차원

제품 사용을 활성화하면 다음 차원을 사용할 수 있습니다. 차원 설정을 변경하려면 시스템 소유 데이터 보기의 복사본을 만들고 Analysis Workspace에서 복사된 데이터 보기를 사용합니다.

| 차원 | 설명 |
| --- | --- |
| 동작 이름 | 사용자가 수행한 작업 유형입니다. 데이터 보기 설정에서 사본을 만들어 이 차원을 원하는 지표로 사용할 수 있습니다. |
| 사용된 속성 모델 | 구성 요소가 사용하는 속성 모델의 유형입니다. |
| 구성 요소 | 구성 요소 유형과 구성 요소 이름을 포함하는 파생된 필드. |
| 구성 요소 유형 | 추가, 제거 또는 수정된 구성 요소의 유형입니다. |
| 로그인 사용자 | 작업을 수행한 사용자입니다. |
| 사용된 패널 | 구성 요소가 추가, 제거 또는 수정된 패널입니다. |
| 프로젝트 이름 | 프로젝트에 대한 알기 쉬운 이름. |
| 프로젝트 유형 | 프로젝트 유형. |
| 사용자 ID | 이벤트를 트리거한 사용자 ID입니다. |
| 사용된 시각화 | 추가, 제거 또는 수정된 시각화입니다. |

프로젝트를 단순히 열거나 볼 때 제품 사용량은 개별 프로젝트 구성 요소를 추적하지 않습니다. 그러나 프로젝트를 여는 사용자 작업은 추적됩니다.
