---
title: 파생 필드 지침
description: 성능 및 데이터 정확성을 최적화하기 위한 모범 사례, 보호 기능 및 일반적인 문제를 포함하여 Customer Journey Analytics에서 파생된 필드를 사용하는 지침에 대해 알아봅니다.
solution: Customer Journey Analytics
feature: Derived Fields
exl-id: bcd172b2-cd13-421a-92c6-e8c53fa95936
role: Admin
hide: true
source-git-commit: 4dd1e90a377c0939048397a0ec4af08123d324c1
workflow-type: tm+mt
source-wordcount: '2741'
ht-degree: 1%

---


# 파생 필드 지침

Customer Journey Analytics [파생 필드](./derived-fields.md)를 사용하면 소스 데이터 세트를 수정하지 않고 쿼리 시간에 데이터를 변환, 분류 및 보강할 수 있습니다. 이러한 유연성으로 인해 규율 없이 적용할 경우 복잡성, 성능 문제 및 유지 관리 오버헤드가 발생할 수 있습니다.

이 문서에서는 파생된 필드 작업에 대한 지침(모범 사례, 보호 및 일반적인 위험)을 제공합니다. 의도한 대상은 데이터 설계자, 제품 관리자 및 다음과 같은 작업을 수행하는 분석가입니다.

* **성능 최적화**: 쿼리 실행 속도가 느려지거나 시스템 제한에 도달하는 패턴을 식별하여 작업에 적합한 도구를 선택하십시오.

   * [파생 필드](./derived-fields.md)
   * [데이터 보기 설정](/help/data-views/component-settings/overview.md)
   * [데이터 준비](https://experienceleague.adobe.com/ko/docs/experience-platform/data-prep/home)
   * [계산된 지표](/help/components/calc-metrics/calc-metr-overview.md)
   * [조회 데이터 세트](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)

* **유지 관리 기능 개선**: 명확하고 모듈식이며 업데이트가 용이한 파생된 필드 논리를 빌드합니다.
* **정확성 확인**: 분류, 속성 및 데이터 변환에서 일반적인 논리적 오류를 방지합니다.

이 글의 섹션은 주제별로 구성되어 있습니다. 복잡한 규칙 체인에서 [조회](./derived-fields.md#lookup), [정규 표현식 바꾸기](./derived-fields.md#regex-replace), [다음 또는 이전](./derived-fields.md#next-or-previous)과 같은 함수 오용에 이르기까지. 각 섹션에는 다음이 포함됩니다.

* 감지할 **패턴**: 파생 필드 정의에서 관찰할 수 있는 신호입니다.
* **위험 진단**: 패턴이 문제가 되는 이유. 가능한 원인은 **성능**, **데이터 품질** 또는 **유지 관리**&#x200B;에 부정적인 영향을 미칠 수 있습니다.
* **권장 사항**: 구현을 리팩터링하거나 개선하는 구체적인 단계.

이러한 지침은 Customer Journey Analytics에서 효율적이고 확장 가능하며 의미론적으로 올바른 구현을 만드는 데 도움이 됩니다. 기존 데이터 보기를 감사하거나, 새 파생 필드를 디자인하거나, 거버넌스 도구를 빌드할 때 이 지침을 적용합니다.


## 높은 카디널리티 파생 필드

이 섹션에서는 카디널리티가 높은 파생된 필드를 참조하는 데이터 보기 기본 세그먼트에 대해 설명합니다.

### 패턴

* 높은 카디널리티 차원(약 1백만 개 이상의 고유한 값)을 기반으로 구축된 파생 필드를 참조하는 데이터 보기의 기본 세그먼트입니다. 예: 전체 페이지 URL.
* 페이지 URL에서 [소문자](./derived-fields.md#lowercase), [트리밍](./derived-fields.md#trim) 또는 [사례 확인](./derived-fields.md#case-when)과 같은 간단한 작업은 종종 페이지 이름, 사이트 섹션 또는 URL 그룹과 같은 낮은 카디널리티 필드의 동일한 논리보다 비용이 더 듭니다.

### 위험 진단: 성능

* 페이지 URL 또는 기타 카디널리티가 높은 차원을 터치하는 파생 필드를 필터링하는 기본 세그먼트는 데이터 보기에 대해 모든 쿼리에 지연을 추가합니다.

### 추천 항목

* 데이터 보기 기본 세그먼트에서 전체 페이지 URL 또는 유사하게 카디널리티가 높은 구성 요소를 직접 참조하지 마십시오. 대량 URL 논리(복합 [Case When](./derived-fields.md#case-when), [Regex Replace](./derived-fields.md#regex-replace), 여러 문자열 함수)를 [데이터 준비](https://experienceleague.adobe.com/ko/docs/experience-platform/data-prep/home) 또는 [조회 데이터 세트](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) 업스트림으로 푸시하여 결과 분류는 더 간단하고 카디널리티가 낮은 차원에 도달합니다.
* 표준화된 페이지 이름, 사이트 섹션 또는 사전 분류된 URL 그룹과 같은 하위 카디널리티 키를 선호합니다.
* 카디널리티가 높은 차원(페이지 URL, 캠페인 ID, 원시 쿼리 문자열)에 대한 참조와 정규화되거나 그룹화된 키에 대한 리팩터링을 위해 기존 데이터 보기 기본 세그먼트 및 파생 필드를 정기적으로 감사합니다.

## 규칙 체인이 있는 경우 지나치게 복잡한 경우

이 섹션에서는 [Case When](./derived-fields.md#case-when) 규칙의 복잡한 체인에 대해 설명합니다.

Customer Journey Analytics은 파생 필드당 명시적 [함수 및 연산자 제한](derived-fields.md#limitations)을(를) 적용합니다(예: 유형당 최대 연산자 수, 최대 함수 수). 함수 내에 있는 복잡한 함수와 체인은 유지하기가 더 어렵고 오류가 발생하기 쉽습니다.

### 패턴

* 복잡한 [If](./derived-fields.md#case-when) 및 **[!UICONTROL Else If]** 체인을 사용하는 매우 큰 **[!UICONTROL Case When]** 함수:
   * 많은 조건(예: 20개 이상의 연산자) 또는 딥 중첩(3개 또는 4개 이상의 중첩 [사례 When](./derived-fields.md#case-when) **[!UICONTROL If]** 및 **[!UICONTROL Else If]** 논리).
   * 동일한 필드에 다른 값으로 반복된 조건.
* 상수 문자열 일치를 반복했습니다.

  +++ 예

  ![모범 사례 - 반복되는 상수 문자열 일치의 예](assets/best-practices-over-complex-case-when.png)

  +++


### 위험 진단: 성능, 데이터 품질, 높은 유지 관리

* 유지 관리 및 오류 위험: 단일 규칙 블록으로 인코딩된 논리는 디버그 및 업데이트가 어렵습니다.
* 잠재적인 성능 및 제한 위험: 특히 분류와 유사한 패턴을 사용하여 [연산자 또는 함수 제한](./derived-fields.md#limitations)에 도달하거나 접근할 수 있습니다.

### 추천 항목

* 여러 파생 필드로 분할합니다. 예를 들어, 모든 것을 하나의 큰 규칙으로 결합하는 대신 채널 버킷팅에서 *캠페인 표준화*(일치하지 않는 캠페인 식별자를 표준 값에 매핑)를 분리하십시오.
* 조회 데이터 세트를 사용합니다. 많은 **[!UICONTROL If 값 _값_ 기준 _기준_ Then _값_을(를) 값]**(으)로 설정하는 것이 긴 [Case When](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) 체인을 사용하는 대신 [Lookup](./derived-fields.md#lookup) 함수와 결합된 [조회 데이터 세트](./derived-fields.md#case-when)(으)로 더 잘 구현됩니다.
* 데이터 보기 구성 요소 필터를 사용합니다. 논리의 일부가 단순히 잘못된 값을 필터링하는 경우 파생 필드에 해당 논리를 포함하는 대신 데이터 보기 구성 요소 수준에서 [include exclude](/help/data-views/component-settings/include-exclude-values.md)을(를) 사용하십시오.

## 잘못된 사용

이 섹션에서는 파생 필드의 잘못된 사용에 대해 설명합니다. 특히 대안이 더 나은 해결책인 경우.

>[!NOTE]
>
>파생 필드에서 데이터 보기 구성 요소 설정으로 논리를 이동하는 것 자체로는 쿼리 성능을 향상시킬 수 없습니다. 두 접근 방식은 모두 동일한 기본 파생 논리로 컴파일됩니다. 이 섹션의 권장 사항은 신속성보다는 명확성, 거버넌스 및 재사용에 관한 것입니다.

### 패턴

* 파생 필드는 구성 요소 설정에서 이미 사용 가능한 동작을 복제합니다.
   * 대소문자 표준화, 트리밍 또는 간단한 필터링(예: `unknown`, `undefined` 또는 `null` 제외)을 통해 복잡성을 가중시키지 않습니다.
   * 숫자 범위에 대한 기본 버킷팅.

     +++ 예

     ![잘못된 기본 버킷팅 사용](assets/best-practices-wrong-usage.png)

     +++

     대신 데이터 보기의 차원에서 [값 버킷팅](/help/data-views/component-settings/value-bucketing.md)을 사용하십시오.
   * 데이터 보기 [속성](./derived-fields.md#next-or-previous) 및 [만료](/help/data-views/component-settings/attribution.md) 설정이 충분할 경우 [다음 또는 이전](/help/data-views/component-settings/persistence.md) 또는 수동 시퀀스 논리로 코딩된 지속성 또는 속성 논리입니다.
   * 조건에서 기존 지표를 간단히 계산하는 파생 지표입니다.

     +++ 예

     ![잘못된 조건부 논리 사용](assets/best-practices-wrong-usage-2.png)

     +++

     이렇게 하면 필터링된 지표 또는 [포함/제외 값](/help/data-views/component-settings/include-exclude-values.md)이 달성할 수 있는 결과를 복제합니다.

### 위험 진단: 데이터 품질, 높은 유지 관리

* 중복 복잡성: 파생 필드는 더 단순한 기본 제공 데이터 보기 기능이 있는 곳에서 사용됩니다.
* 거버넌스 위험: 다른 사용자는 기본 설정 대신 파생된 필드가 존재하는 이유를 이해하지 못할 수 있습니다. 파생된 필드 관리에서 패턴이 복잡해집니다.
* 재사용 가능성 감소: 파생 필드로 조건부 플래그를 인코딩하면 프로젝트 간에 서로 다른 필터가 있는 기본 지표를 더 쉽게 재사용할 수 있습니다.

### 추천 항목

* 트리밍/소문자: 결합된 다단계 변환이 필요하지 않은 경우 [하위 문자열](/help/data-views/component-settings/substring.md) 및 [동작](/help/data-views/component-settings/behavior.md) 구성 요소 설정을 사용하십시오.
* 값 제외: 파생 필드가 아닌 데이터 보기 구성 요소 수준에서 지표 또는 차원 값에 [제외 값 포함](/help/data-views/component-settings/include-exclude-values.md)을 사용합니다.
* 속성 및 지속성: [다음 또는 이전](/help/data-views/component-settings/persistence.md) 또는 기타 순차적 논리를 사용하여 파생 필드에서 차원을 시뮬레이션하는 대신 차원에 대한 데이터 보기 **[!UICONTROL 지속성]** 설정(**[!UICONTROL 할당 모델]** 및 [만료](./derived-fields.md#next-or-previous))을 사용합니다.
* 숫자 버킷팅: 파생된 필드를 숫자로 유지하고 데이터 보기에서 [Case When](./derived-fields.md#case-when) 체인에 범위 레이블을 하드 코딩하는 대신 맨 위에 버킷 차원을 만들 수 있도록 합니다.
* 조건부 논리: 단순 0 또는 1 플래그 논리를 다음 중 하나로 변환합니다.
   * Analysis Workspace에 적용된 포함 또는 제외 값이 있는 원래 지표 필터 논리입니다.
   * 데이터 보기 구성 요소 설정 구성을 사용하여 필터링된 지표.

## 지표 및 차원의 잘못된 분류

이 섹션에서는 지표 및 차원의 잘못된 분류에 대해 설명합니다.

### 패턴

* 파생된 필드는 다음을 분명히 생성합니다.
   * 숫자 출력(개수, 비율 또는 산술)이지만 구성 요소는 차원으로 구성됩니다.
   * 범주형 출력(레이블 또는 문자열)이지만 구성 요소는 지표로 구성됩니다.
* 파생된 필드는 0/1 플래그를 문자열로 인코딩합니다.

Customer Journey Analytics을 사용하면 숫자 필드를 차원으로, 문자열 필드를 데이터 보기 수준의 지표로 강제 변환할 수 있지만 잘못 정렬하면 보고에 혼동을 줄 수 있습니다.

### 위험 진단: 데이터 품질

* 의미론적 불일치: 구성 요소 유형이 파생된 결과의 속성과 일치하지 않으므로 구성 요소를 올바르게 분석하거나 집계하기 어렵습니다.

### 추천 항목

* 출력이 숫자인 경우
   * 데이터 보기에서 구성 요소 유형을 **[!UICONTROL 지표]**(으)로 설정하십시오.
   * 구성 요소가 하위 집합 지표를 나타내는 경우(예: **[!UICONTROL 페이지 보기 수 체크아웃]**) 파생 문자열과 맨 위의 계산된 지표가 아닌 데이터 보기 내에서 필터링된 지표를 사용하십시오.
* 출력이 레이블인 경우:
   * 구성 요소 유형을 **[!UICONTROL Dimension]**(으)로 설정하고 그에 따라 [지속성](/help/data-views/component-settings/persistence.md) 설정(**[!UICONTROL 할당 모델]** 및 **[!UICONTROL 만료]**)을 구성하십시오.

## 마케팅 채널 및 캠페인 논리 위험

이 섹션에서는 마케팅 채널 및 캠페인 논리 위험에 대해 설명합니다.

>[!NOTE]
>
>업스트림 간소화를 고려해 보십시오. [데이터 준비](https://experienceleague.adobe.com/ko/docs/experience-platform/data-prep/home), [조회 데이터 세트](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md) 또는 [분류](./derived-fields.md#classify)와 같은 파생 필드 함수를 사용하여 유사한 마케팅 채널 규칙을 통합하고 [Case When](./derived-fields.md#case-when) 논리의 연산자 수를 줄이십시오. 또한 채널 분류 로직에서 참조되는 높은 카디널리티 필드의 수를 제한하십시오(예: 많은 개별 쿼리 매개 변수 키). 이러한 필드는 카디널리티와 쿼리 비용을 모두 증가시킵니다.

### 패턴

* Customer Journey Analytics 마케팅 채널은 종종 파생 필드를 사용하여 구현됩니다.

   * URL 매개 변수, 레퍼러, 랜딩 페이지 등을 기반으로 마케팅 채널 또는 캠페인 버킷을 구현하는 파생 필드입니다.
   * 의심스러운 순서 지정: 더 구체적인 규칙이 적용되기 전에 일반적인 다목적 캐치 규칙이 표시됩니다.
   * 가능한 모든 옵션을 불완전하게 처리합니다. **[!UICONTROL 참조 도메인에 대한 명시적 분기가 설정되지 않았거나]** **[!UICONTROL 쿼리 매개 변수가 설정되지 않았습니다]**.

### 위험 진단: 데이터 품질

* 논리 순서 지정 오류: 특정 채널을 무시할 수 있고 잘못 분류된 트래픽을 초래할 수 있는 체인의 나중 규칙입니다.
* 직접 트래픽 잘못된 레이블 지정: 일치하지 않는 트래픽이 의도하지 않은 채널에 속하거나 `Other`(으)로 레이블이 지정됩니다.

### 추천 항목

* 하향식 우선순위 순서를 적용합니다. 가장 강력한 신호를 먼저 배치합니다(예: 유료 캠페인 매개 변수를 제외하는 내부 도메인).
* 최종 명시적 **[!UICONTROL 을(를) 포함하거나, 그렇지 않으면 값을]** 대/소문자로 설정하십시오. 이전 채널을 덮어쓰지 않도록 하려면 대체 항목을 **[!UICONTROL 값 없음]**(으)로 설정하십시오. 이 catch-all 단계에서는 값을 **[!UICONTROL 사용자 지정 문자열 값]**(으)로 설정한 다음 **[!UICONTROL 사용자 지정 문자열 값]**&#x200B;을(를) `Direct`, `None` 또는 `Unclassified`(으)로 설정하지 마십시오.
* 템플릿을 사용합니다. 가능하면 마케팅 채널 파생 필드 템플릿을 활용하십시오. 또는 적어도 Adobe의 권장 마케팅 채널 모범 사례에 맞게 논리를 조정할 수 있습니다.

## 조회에 사용되는 정규화되지 않은 문자열 키

이 섹션에서는 조회에서 비정규화된 문자열 키를 사용하는 방법에 대해 설명합니다.

### 패턴

* 조회 데이터 집합을 제공하는 이벤트 또는 프로필 필드에 대한 [조회](./derived-fields.md#lookup) 함수입니다.
* 키를 표준화하는 이전 [Lowercase](./derived-fields.md#lowercase), [Trim](./derived-fields.md#trim) 또는 [Regex Replace](./derived-fields.md#regex-replace)가 없습니다.
* 일반적인 후보: URL, 캠페인 ID, 이메일, 계정 ID.

### 위험 진단: 데이터 품질, 높은 유지 관리

* 데이터 품질 위험: 키 대/소문자나 공백이 조회 테이블과 다를 경우 조회가 실패하여 *일치 항목 없음* 값 및 보고 간격이 발생합니다.

### 추천 항목

* 대문자나 소문자를 유지하는 이유가 문서화되어 있지 않은 한 [Lookup](./derived-fields.md#lowercase) 함수 앞에 [Lowercase](./derived-fields.md#trim) 및 [Trim](./derived-fields.md#lookup) 함수를 추가하십시오.
* 여러 변환이 이미 체인 연결되어 있는 경우 순서를 확인합니다. 먼저 정규화한 후 찾습니다.

## 정규 표현식 오용 또는 도달 범위

이 섹션에서는 파생 필드에 대한 정규 표현식 기능의 오용 또는 초과에 대해 설명합니다.

### 패턴

* [Regex 바꾸기](./derived-fields.md#regex-replace) 또는 regex 기반 조건에서는 매우 광범위한 패턴을 사용합니다. [포함](./derived-fields.md#case-when) 또는 **[!UICONTROL 다음으로 시작]**&#x200B;을 사용하는 **[!UICONTROL Case When]** 함수가 더 간단하고 더 나은 대안입니다.

  +++ 예

  ![모범 사례 - Regex 바꾸기 1](assets/best-practices-regex-replace-1.png)

  ![모범 사례 - Regex 바꾸기 1](assets/best-practices-regex-replace-2.png)

  +++

* 여러 정규 표현식 조건이 겹치거나 충돌합니다.
* [URL 구문 분석](./derived-fields.md#url-parse) 함수를 사용하는 대신 URL을 구문 분석하는 대량 정규 표현식 사용입니다.

### 위험 진단: 성능, 데이터 품질, 높은 유지 관리

* 성능 및 유지 관리 위험: 복잡한 정규 표현식 패턴은 디버깅하기 어려우며 속도가 느려질 수 있습니다.
* 정확성 위험: 지나치게 광범위한 정규 표현식은 의도하지 않은 값을 포착할 수 있습니다.

### 추천 항목

* [Regex 바꾸기](./derived-fields.md#url-parse)보다 표준 URL 요소(도메인, 경로, 쿼리 매개 변수)에 대해 [URL 구문 분석](./derived-fields.md#regex-replace)을 선호합니다.
* 간단한 패턴 검사의 경우 [Regex Replace](./derived-fields.md#case-when)를 사용하는 정규 표현식 대신 **[!UICONTROL Case When]** with **[!UICONTROL Contains]**, **[!UICONTROL Starts with]** 또는 [Ends with](./derived-fields.md#regex-replace) 논리를 사용하십시오.
* 간단한 패턴에 대해 여러 중첩 그룹 또는 대체를 사용하는 정규 표현식에 플래그를 지정합니다. 또는 파생된 필드 문자열 함수를 사용하여 바꿀 수 있는 정규 표현식입니다.

## 파생 필드의 계산된 지표 스타일 논리

이 섹션에서는 파생 필드에서 계산된 스타일 논리를 사용하는 방법에 대해 설명합니다.

>[!NOTE]
>
>파생 필드는 집계하기 전에 이벤트(행) 수준에서 평가되지만, Analysis Workspace 계산된 지표는 이미 집계된 값에서 작동합니다. 따라서 비율, 평균 및 개별 스타일 계산은 이러한 계산이 파생 필드로 구현되는지 또는 계산된 지표로 구현되는지에 따라 다른 결과를 산출할 수 있습니다. 산술이 어디에 사는지 숙고해야 한다. 평가의 알맹이가 답을 바꾸기 때문이다.

### 패턴

* 계산된 지표처럼 보이는 파생 필드(합계, 빼기, 나눗셈) 내의 숫자 필드에 대한 순수 산술.

  +++ 예

  ![모범 사례 - 이익 계산](assets/best-practices-profit.png)

  ![모범 사례 - 노출당 주문 수](assets/best-practices-orders-impressions.png).

  +++

* 문자열 조작이나 분류를 사용하지 않습니다. 논리는 순전히 숫자입니다.

### 위험 진단: 데이터 품질

* 거버넌스 및 디자인 질문: 산술을 다음과 같이 배치하는 것이 더 나을 수 있습니다.
   * 파생 필드 지표(파생 필드를 모든 사용자에 대해 관리되는 표준 지표로 하려는 경우).
   * Analysis Workspace의 계산된 지표(계산된 지표가 분석별로 계산된 경우).

### 추천 항목

* 산술 결과가 일반적으로 사용자 및 프로젝트에서 유용한 경우 결과를 파생 필드 지표로 유지하십시오. 구성 요소 유형이 지표이고 서식(통화, 백분율)이 데이터 보기 수준에서 구성되어 있는지 확인합니다.
* 결과가 틈새나 분석가별로 다르면 결과를 계산된 지표로 이동하고 데이터 보기를 단순화합니다.

## 다음 또는 이전 또는 순차적 함수의 과다 사용

이 단원에서는 [다음 또는 이전](./derived-fields.md#next-or-previous) 또는 순차적 함수의 과다 사용에 대해 설명합니다.

### 패턴

* 파생 필드는 [다음 또는 이전](./derived-fields.md#next-or-previous) 함수를 여러 번 사용합니다(필드당 문서화된 제한에 가까움).
* [다음 또는 이전](./derived-fields.md#next-or-previous)은(는) 데이터 보기 지속성을 사용하는 대신 지속성과 유사한 논리(예: 캠페인 전달)를 구현하는 데 사용됩니다.

### 위험 진단: 데이터 품질, 높은 유지 관리

* 복잡성 및 취약성: 무거운 순차적 논리는 추론하기 어렵고 세션화 규칙 또는 순서가 변경되는 경우 중단될 수 있습니다.
* 차원 지속성이 있는 중복성: 일부 사용 사례(예: 세션의 마지막 터치 채널)는 차원의 데이터 보기 [지속성](/help/data-views/component-settings/persistence.md) 설정(**[!UICONTROL 할당 모델]**)에서 더 잘 다룹니다.

### 추천 항목

* 표준 지속성과 유사한 패턴(예: 세션 또는 사용자 간에 값을 전달)의 경우, [다음 또는 이전](/help/data-views/component-settings/persistence.md)으로 이러한 패턴을 시뮬레이션하는 대신 데이터 보기에서 차원의 **[!UICONTROL 지속성]** 설정(**[!UICONTROL 할당 모델]** 및 [만료](./derived-fields.md#next-or-previous))을 사용하십시오.
* 차원 지속성만으로는 달성할 수 없는 고급 다중 단계 경로 또는 funnel 레이블에 대해 [다음 또는 이전](./derived-fields.md#next-or-previous)을(를) 예약합니다(예: 채널 시퀀스 연결).

## 세션 및 사용자 수준 컨텍스트 무시

이 섹션에서는 파생 필드를 정의할 때 세션 및 사용자 수준 컨텍스트를 무시하는 방법에 대해 설명합니다.

>[!NOTE]
>
>경우에 따라 Analysis Workspace의 세션 또는 개인 수준에서 범위가 지정된 세그먼트는 파생 필드보다 더 간단하게 동작을 모델링할 수 있습니다. 적절한 경우 복잡한 교차 범위 파생 필드 대신 세그먼트를 사용하는 것이 좋습니다.

### 패턴

* 파생 필드는 암시적으로 특정 [컨테이너 수준](/help/getting-started/cja-b2b-concepts-features.md#containers)(이벤트, 세션 또는 사용자)을 가정하지만:

   * 파생된 필드는 세션 또는 사용자 수준 특성을 참조하지 않습니다.
   * 데이터 보기 세션 설정이 의도한 논리와 충돌합니다.

### 위험 진단: 데이터 품질

* 개념적 불일치: 파생된 필드 의미 체계는 분석가가 예상하는 집계 수준과 일치하지 않을 수 있습니다(예: 모든 이벤트와 함께 변경할 수 있는 담당자 기반 필드).

### 추천 항목

* 논리를 세션 수준으로 사용하려는 경우: [세션 설정](/help/data-views/session-settings.md)이 적절하게 구성되어 있는지 확인하고 Analysis Workspace 또는 [통합 BI 도구](/help/data-views/bi-extension.md)에서 세션 범위 구성 요소 또는 요약을 사용하는 것이 좋습니다.
* 논리가 개인 수준으로 의도된 경우: 프로필 데이터 세트 또는 조회 데이터 세트를 사용하고 파생된 필드 내에서 이러한 데이터 세트를 참조합니다.
* Analysis Workspace의 세션 범위 세그먼트 또는 사용자 범위 세그먼트가 파생된 필드보다 더 간단하게 동일한 결과를 달성할지 여부를 평가합니다.

## 문서화된 기능 제한에 도달하거나 근접한 경우

이 섹션에서는 문서화된 파생 필드 함수 제한에 도달하거나 근접한 것의 의미에 대해 설명합니다.

>[!NOTE]
>
>가능한 경우 복잡한 파생 필드 내에서 카디널리티가 높은 필드에 대한 의존도를 줄입니다(예: 표준화된 키 또는 그룹화된 분류 사용). 쿼리 비용과 [연산자 또는 함수 제한에 도달할 가능성](./derived-fields.md#limitations)을 모두 제한하십시오.

Customer Journey Analytics [문서](./derived-fields.md#limitations) 파생 필드당 최대 함수 및 연산자(함수 유형별 제한 포함)([조회](./derived-fields.md#lookup), [날짜 계산](./derived-fields.md#date-math), [중복 제거](./derived-fields.md#deduplicate), [계산](./derived-fields.md#math), [분할](./derived-fields.md#split), [URL 구문 분석](./derived-fields.md#url-parse) 등).

### 패턴

* 파생 필드는 많은 [조회](./derived-fields.md#lookup), [계산](./derived-fields.md#math) 작업, [분할](./derived-fields.md#split) 또는 기타 함수를 사용합니다.
* 연산자 수가 [문서화된 제한](./derived-fields.md#limitations)에 가깝습니다(예: 허용된 수의 70% 이상 - 80%).

### 위험 진단: 성능, 높은 유지 관리

* 확장성 위험: 필드가 함수 제한에 도달할 경우 향후 추가가 실패하거나 예기치 않게 동작할 수 있습니다.

### 추천 항목

* 사용량이 임계값을 초과할 때 미리 플래그로 표시합니다(예: 모든 함수 또는 연산자 제한의 70% 이상).
* 논리를 함께 체인 연결된 여러 파생 필드로 분할합니다(예: 조회 키를 정규화하는 파생 필드 A와 Band normalize_key 다음 lookup_label 파생 필드).
* 특히 대규모 분류가 필요한 경우 외부 데이터 준비 또는 조회 데이터 세트를 사용합니다.

## 데이터 보기별 최적화 규칙

이 섹션에서는 파생된 필드에 대한 데이터 보기 특정 최적화 규칙에 대해 설명합니다.

또한 각 파생 구성 요소에 대한 데이터 보기 구성을 확인하십시오.

### 패턴

* 파생 차원에는 기본 속성이 있지만(예: 세션 만료가 있는 마지막 터치) 파생 필드 이름은 다른 의미 체계를 의미합니다(예: `First Campaign of Visit`, `Original Source`).
* 파생 차원에 기본 [지속성](/help/data-views/component-settings/persistence.md) 설정(예: **[!UICONTROL 세션]** 만료와 함께 **[!UICONTROL 가장 최근]** 할당)이 있지만 파생 차원의 이름은 다른 의미 체계(예: `First Campaign of Visit` 또는 `Original Source`)를 의미합니다.


### 위험 진단: 데이터 품질

* 의미론적 불일치: 차원의 레이블은 실제로 구성된 것과 다른 할당 또는 만료 동작(예: 원래 할당 또는 개인 수준 만료)을 제안합니다.
* 이러한 불일치는 분석가가 보고서를 잘못 해석하거나 이름별로 비슷하게 보이지만 서로 다른 배분 모델을 사용하는 구성 요소를 비교하는 위험을 증가시킵니다.

### 추천 항목

* 해당 차원의 [할당 모델 및 만료](/help/data-views/component-settings/persistence.md)을(를) 조정하여 이름과 동작을 조정합니다. 예를 들어, 파생된 필드 차원 `Original Source`은(는) 만료가 Person으로 설정된 첫 번째 터치 속성을 사용해야 합니다.
* 이름과 동작을 맞추려면 차원의 **[!UICONTROL 지속성]** 설정에서 **[!UICONTROL 할당 모델]** 및 [만료](/help/data-views/component-settings/persistence.md)을(를) 조정하십시오. 예를 들어 `Original Source`은(는) **[!UICONTROL 할당 모델]**&#x200B;을(를) **[!UICONTROL 원래]**(으)로 설정해야 합니다. **[!UICONTROL 만료]**&#x200B;은(는) **[!UICONTROL 개인]**(으)로 설정되어 있습니다.

