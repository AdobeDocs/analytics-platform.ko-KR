---
title: 데이터 내보내기 사용 사례
description: Customer Journey Analytics을 위한 다양한 데이터 내보내기 사용 사례 이해
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: 40e4c3bd8f3c37e9a6143200b85ffe0ac4bcb2ca
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 0%

---

# 데이터 내보내기 사용 사례

이 섹션에서는 데이터 내보내기 사용 사례와 하나 이상의 Customer Journey Analytics 또는 Experience Platform 기능을 사용하여 이러한 사용 사례를 구현하는 방법을 제공합니다. 각 기능은 별도의 문서에 자세히 설명되어 있습니다.

## 소개

Adobe Analytics과 Customer Journey Analytics 간의 고유한 차이점 중 하나는 속성 및 세션화를 위한 데이터 처리와 관련되어 있습니다. 다음을 참조하십시오 [Adobe Analytics 및 Customer Journey Analytics 간 데이터 처리 비교](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) 추가 정보.

### Adobe Analytics: 컬렉션 시간 속성 및 세션화.

Adobe Analytics에서 모든 이벤트는 장치 ID별로 실시간으로 처리되므로 Adobe은 수집 시 다음을 포함하여 지속되거나 기여되는 값으로 클릭스트림 데이터를 생성, 저장 및 내보낼 수 있습니다.

* Dimension 지속성(예: 90일 후에 만료되는 캠페인 추적 코드).
* 방문 번호 및 세션화.
* 처리 및 VISTA 규칙으로 계산된 Dimension 값.

이는 Adobe Analytics에서 데이터를 내보내는 데 영향을 줍니다.

* 초기 수집 후 데이터 처리는 정적입니다.
* 데이터 피드에는 수집 시간 처리를 반영하는 &quot;이후&quot; 열이 포함됩니다.


### Customer Journey Analytics: 쿼리 시간 속성 및 세션화

Customer Journey Analytics에서 Customer Journey Analytics은 순서대로 수집되지 않고 장치 ID 대신 개인 ID가 사용되므로 보고 시 이벤트가 속성 및 세션화를 업데이트할 수 있습니다. 이러한 유형의 데이터 수집은 다음과 같은 유연성을 제공합니다.

* 결합 캔 _재생_ 익명의 이벤트를 알려진 이벤트와 연결하는 데이터를 매일 또는 매주. 다음을 참조하십시오 [결합](../../stitching/overview.md) 추가 정보.
* 세션 및 지속된 값은 매번 변경됩니다
   * 새 데이터가 수집되거나
   * 결합하면 개인 기록에 이벤트가 추가됩니다.

보고서 처리 시간은 Customer Journey Analytics에서 데이터를 내보내는 데 영향을 줍니다. 지속된 값을 포함하는 내보내기는 Customer Journey Analytics 보고서와 일치하지 않으며 값은 시간이 지남에 따라 사라집니다.

지표의 일관성을 위해 Customer Journey Analytics의 새로운 기능을 사용하는 것이 좋습니다. 일반적으로 Experience Platform 및 Customer Journey Analytics 데이터 내보내기 기능은 Adobe Analytics의 데이터 피드 기능을 초과합니다. Experience Platform 및 Customer Journey Analytics은 다음을 제공합니다.

* 새로운 데이터 소스 및 데이터 내보내기 대상 처리

   * 비디지털 데이터 소스 포함,
   * 비즈니스 규칙에 따라 사용자 지정 속성 및 세션 적용
   * 고객 여정을 계속 업데이트하며 결합합니다.

* 맞춤형 데이터 내보내기 사용 사례 실현

   * Business Intelligence(BI) 도구 및 클라우드 대상을 포함하여 데이터를 필요한 위치로 내보내기
   * bi 도구 통합을 통해 Analysis Workspace과 데이터 동기화 유지,
   * 자체 시스템에서 처리 논리를 복제할 필요가 없습니다.
   * 계산된 지표, 파생 필드 및 세분화에 대한 새로운 지원

* 설계에 의한 보안 및 데이터 거버넌스 고려

   * 사용자 및 대상별로 모든 데이터 내보내기 모니터링,
   * 내보낼 수 있는 데이터에 대한 제한 설정 및
   * 배달 문제에 대한 경고 및 예약된 배달 기간에 대한 제한을 설정합니다.


## 사용 사례 및 기능

일반적으로 데이터 내보내기는 여러 사용 사례를 지원합니다. 각 사용 사례는 필요한 데이터와 해당 데이터에 액세스하고 내보내는 방법에 따라 다릅니다. Experience Platform 및 Customer Journey Analytics은 독립적으로 또는 결합하여 다양한 사용 사례를 해결할 수 있는 다양한 기능을 제공합니다. 아래 표는 식별된 데이터 내보내기 사용 사례와 이러한 사용 사례를 구현하기 위한 Experience Platform 및 Customer Journey Analytics 기능에 대한 개요를 제공합니다.

| 데이터 내보내기 사용 사례 | Experience Platform 및 Customer Journey Analytics 기능 |
|---|---|
| **데이터 백업**<br/>&#x200B;규정 준수 또는 규정 준수를 위해 디지털 데이터의 전체 사본을 보관하십시오. | **Experience Platform**: [**데이터 세트 내보내기**](export-datasets.md)<br/> Experience Platform에서 수집된 데이터를 일정에 따라 또는 임시로 클라우드 대상으로 직접 내보냅니다.<br/>*현재 제한된 릴리스, 2024년 6월에 Customer Journey Analytics 고객을 위한 전체 릴리스가 예정되어 있습니다.* |
| **데이터 유효성 검사**<br/>&#x200B;클릭스트림 데이터를 평가하여 데이터 수집 정확도를 확인합니다. | **Experience Platform**: [**쿼리 서비스(데이터 Distiller) 및 데이터 세트 내보내기**](queryservice-export-datasets.md)<br/> 대화형 PostgreSQL 인터페이스를 통해 즐겨 사용하는 SQL 도구를 사용하여 임시 SQL 쿼리를 실행하여 데이터 세트의 데이터를 확인합니다.<br/><br/>**Customer Journey Analytics**: [**전체 테이블 내보내기**](export-full-table.md)<br/>&#x200B;속성 및 세션화가 적용된 CJA에서 처리된 데이터의 유효성을 검사합니다. |
| **Data Lake, Data Warehouse 또는 BI 도구**<br/>&#x200B;추가 데이터 세트와 함께 사용할 수 있도록 디지털 데이터를 고유한 BI 도구 또는 Data Lake로 가져옵니다. | **Customer Journey Analytics**: [**BI 확장**](bi-extension.md)<br/> Customer Journey Analytics 처리된 지표를 Power BI과 같은 데이터 시각화 도구에 추가하고 사용자 정의 보고서를 위한 추가 데이터와 결합합니다&#x200B;<br/><br/>**Experience Platform**: [**쿼리 서비스(데이터 Distiller) 및 데이터 세트 내보내기**](queryservice-export-datasets.md)<br> SQL을 사용하여 클라우드 대상으로 전달할 사용자 지정된 클릭스트림 데이터를 생성합니다. |
| **AI/ML 준비 완료**<br/> Customer Journey Analytics 데이터를 통해 인공 지능/머신 러닝 모델 및 작업을 개선합니다. | **Customer Journey Analytics**: [**전체 테이블 내보내기**](export-full-table.md)<br/>&#x200B;계산된 지표 및 세분화를 포함하여 Customer Journey Analytics 처리된 차원 및 지표를 클라우드 대상으로 한 번 또는 반복적으로 내보냅니다.<br/><br/>**Experience Platform**: [**쿼리 서비스(데이터 Distiller) 및 데이터 세트 내보내기**](queryservice-export-datasets.md)<br/> SQL을 사용하여 사용자 지정된 클릭스트림 데이터를 생성하여 AI/ML 모델을 보강합니다. |
