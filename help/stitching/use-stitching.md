---
title: 결합 요청
description: 결합 요청 방법
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: 9ace0679796c3a813b1fbd97c62c20faf64db211
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 5%

---

# 결합 요청


>[!IMPORTANT]
>
>Adobe을 통한 요청 결합은 더 이상 필요하지 않으며 이 방법은 더 이상 사용되지 않습니다. [연결 UI에서 연결을 사용하도록 설정](use-stitching-ui.md).
>



조직이 모든 [필수 구성 요소](overview.md#prerequisites)를 충족하고 일반적인 [제한 사항](overview.md#limitations) 및 연결 방법별 제한 사항([필드 기반](fbs.md#limitations) 및 [그래프 기반](gbs.md#limitations))을 이해하면 다음 단계에 따라 Customer Journey Analytics에서 연결을 요청하고 사용할 수 있습니다.

## 옵션 선택

권한이 있는 Customer Journey Analytics 패키지는 사용 가능한 결합 방법, 초기 채우기 기간, 전환 확인 기간, 재생 빈도 및 결합이 허용되는 최대 데이터 세트 수를 결정합니다. 자세한 내용은 [Customer Journey Analytics 제품 설명](https://helpx.adobe.com/kr/legal/product-descriptions/customer-journey-analytics.html)을 참조하세요. 지원을 요청하기 전에 사용 가능한 옵션을 결정하십시오.

| | Customer Journey Analytics<br/>선택 | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| 사용 가능한 결합 방법 | 필드 기반 결합 | 필드 기반 결합<br/>그래프 기반 결합 | 필드 기반 결합<br>그래프 기반 결합</li> |
| 1회 스티칭 채우기 기간 | 13개월 | 13개월 | 25개월 |
| 전환 확인 기간 및 재생 빈도 | 1일, 매일<br/>최대 7일, 매주 | 1일, 매일<br/>최대 14일, 매주 | 1일, 매일<br/>최대 30일, 매주 |
| 결합에 허용되는 최대 데이터 세트 수 | 5 | 15 | 50 |

## 지원 요청

1. 다음과 관련된 질문이 있는 경우 Adobe 고객 지원 센터에 문의하십시오.

   - 결합 활성화 요청.
   - 다시 입력할 데이터 세트에 대한 데이터 세트 ID입니다.
   - 원하는 데이터 세트(모든 행에 표시되는 식별자)에 대한 영구 ID의 열 이름(ID 경로 및 네임스페이스)입니다.
   - 데이터 집합이 `identityMap`을(를) 지원하는 경우:
      - 필드 기반 결합의 경우 영구 ID와 개인 ID 모두에 대한 네임스페이스를 지정합니다.
      - 그래프 기반 결합의 경우 ID 그래프 쿼리에 사용할 영구 ID의 네임스페이스와 ID 네임스페이스를 지정하십시오.
   - 데이터 집합에서 `identityMap`을(를) 지원하지 않는 경우:
      - 필드 기반 결합의 경우, 원하는 데이터 세트에 대한 개인 ID의 열 이름 (연결 컨텍스트에서 데이터 세트 간 링크 역할도 하는 개인 식별자).
      - 그래프 기반 결합의 경우 ID 그래프 쿼리에 사용할 ID 네임스페이스입니다.
   - 전환 확인 기간 및 재생 빈도에 대한 사용자 기본 설정입니다. 사용 가능한 [옵션](#options)은 Customer Journey Analytics 패키지를 참조하세요.
   - 샌드박스 이름


2. Adobe 고객 지원 팀은 Adobe 엔지니어링과 함께 작동하여 요청을 받으면 결합을 활성화합니다. 활성화되면 결합된 ID 열이 포함된 재입력된 데이터 세트가 Adobe Experience Platform에 나타납니다. Adobe 고객 지원 센터에서 새 데이터 세트의 ID를 제공할 수 있습니다.
3. 처음 켜면 Adobe에서 결합된 데이터의 채우기를 제공합니다. 사용 가능한 [옵션](#options)은(는) Customer Journey Analytics 패키지를 참조하세요.

4. 크로스 채널 분석에서 결합된 데이터 세트를 사용하려면 결합된 데이터 세트를 Customer Journey Analytics의 [연결](../connections/overview.md)에 추가해야 합니다. 그런 다음 크로스 채널 분석에 필요한 다른 데이터 세트를 추가하고 각 데이터 세트에 대한 올바른 개인 ID를 선택합니다.

5. 연결을 기반으로 [데이터 보기를 만듭니다](/help/data-views/create-dataview.md).

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

데이터 보기가 설정되면 채널 및 디바이스 간에 Customer Journey Analytics 보고 분석을 실행할 수 있습니다.
