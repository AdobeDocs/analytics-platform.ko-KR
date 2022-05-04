---
title: 하위 문자열 구성 요소 설정
description: 문자열의 하위 집합을 차원 항목으로 사용합니다.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: a8bdb5b0c00a9dbca2f466452a5d18045b2e9971
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 6%

---

# [!UICONTROL Substring] 구성 요소 설정

[!UICONTROL Substring] 구성 요소 설정을 사용하면 보고서에서 원하는 차원 항목을 얻기 위해 여러 문자열 조작 방법을 수행할 수 있습니다.

[!UICONTROL Substring] 는 차원에서만 사용할 수 있으며, 적용된 데이터로 소급 적용됩니다. 지속성은 필터링이나 다른 분석 작업이 적용되기 전에 발생하는 즉각적인 데이터 변환입니다.

![하위 문자열 설정](../assets/substring-settings.png)

## 왼쪽/오른쪽에서

문자열의 시작 또는 끝까지의 위치를 기반으로 문자열의 일부를 가져옵니다. **[!UICONTROL 왼쪽에서]** 및 **[!UICONTROL 오른쪽에서]** 메서드는 두 가지 드롭다운을 제공합니다. **[!UICONTROL From]** (출력이 시작되는 위치) 및 **[!UICONTROL 종료]** (출력이 끝나는 위치)

* **[!UICONTROL 문자열 시작]**: 문자열의 시작입니다.
* **[!UICONTROL 문자열 끝]**: 문자열의 끝입니다.
* **[!UICONTROL 위치]**: 메서드에 따라 왼쪽 또는 오른쪽에서 정적 수의 문자입니다.
* **[!UICONTROL 문자열]**: 문자열의 시작이나 끝을 나타내는 문자 또는 문자 시퀀스를 일치시킵니다. 이 드롭다운에는 추가 옵션도 표시됩니다.
   * **[!UICONTROL 일치]**: 일치하는 문자열입니다. 입력이 이 필드와 일치하지 않으면, [값 옵션이 없음](no-value-options.md) 적용합니다.
   * **[!UICONTROL 인덱스]**: 다음 **[!UICONTROL 일치]** 기준은 한 문자열에 여러 번 있을 수 있습니다. 이 정수는 메서드에 따라 출력을 시작하거나 종료할 일치 항목을 결정합니다. 예를 들어 `1` 첫 번째 일치를 나타냅니다. 인덱스가 사용 가능한 일치 수보다 큰 경우 [값 옵션이 없음](no-value-options.md) 적용합니다.
   * **[!UICONTROL 문자열 포함]**: 다음을 포함하는 확인란 **[!UICONTROL 일치]** 를 반환합니다.
* **[!UICONTROL 길이]**: 출력의 시작 위치 뒤에 포함할 문자 수를 지정하는 정수입니다. 아래에서만 사용할 수 있습니다. **[!UICONTROL 종료]** 드롭다운.

## 구분 기호

구분 기호를 사용하여 여러 문자열 값을 구분하는 필드에 이 메서드를 사용합니다. 개별 요소를 추출하여 출력으로 사용하거나 문자열을 개체 배열 스키마 요소로 변환할 수 있습니다.

* **[!UICONTROL 기준]**: 구분된 값 목록을 처리하는 방법입니다.
   * **[!UICONTROL 왼쪽에서]**: 구분된 목록의 시작 부분부터 시작하여 앞으로 계산됩니다.
   * **[!UICONTROL 오른쪽에서]**: 구분된 목록의 끝에서 시작하고 뒤로 계산됩니다.
   * **[!UICONTROL 배열로 변환]**: 이 차원을 개체 배열 스키마 요소인 것처럼 취급합니다.
* **[!UICONTROL 구분 기호]**: 필드가 사용하는 구분 기호입니다.
* **[!UICONTROL 인덱스]**: 기준이 왼쪽에서/오른쪽인 경우에만 표시됩니다. 요소 번호가 배열에 있는 것처럼 표시됩니다. 예를 들어 문자열 입력이 `"Fox,Turtle,Rabbit,Wolf"` 인덱스가 3이면 출력은 `"Rabbit"`. 색인이 구분된 요소의 수보다 큰 경우 [값 옵션이 없음](no-value-options.md) 적용합니다.

## URL 구문 분석

URL이 포함된 필드에 사용할 수 있습니다. 예제 URL 사용 `https://example.com/store/index.html?cid=campaign#cart`, 다음 옵션을 사용할 수 있습니다.

* **[!UICONTROL 프로토콜 가져오기]**: URL의 프로토콜을 가져옵니다. (예: `"https://"`)
* **[!UICONTROL 호스트 가져오기]**: URL의 호스트를 가져옵니다. (예: `"example.com"`)
* **[!UICONTROL 경로 가져오기]**: URL의 경로를 가져옵니다. (예: `"store/index.html"`)
* **[!UICONTROL 쿼리 문자열 값 가져오기]**: 단일 쿼리 문자열에서 값을 가져옵니다. 원하는 쿼리 문자열 매개 변수를 **[!UICONTROL 쿼리 키]** 필드. 위의 URL을 `"cid"` 쿼리 키, 출력은 `"campaign"`.
* **[!UICONTROL 해시 값 가져오기]**: URL의 해시 값을 가져옵니다. (예: `"cart"`)

입력이 올바른 URL이 아니거나 원하는 URL 구성 요소가 없으면, [값 옵션이 없음](no-value-options.md) 적용합니다.

## 트리밍

문자열에서 공백 또는 특수 문자를 잘라냅니다.

* **[!UICONTROL 공백 트림]**: 활성화된 경우 문자열의 시작과 끝에서 모든 공백을 제거하는 확인란입니다.
* **[!UICONTROL 특수 문자 재단]**: 다음과 같은 메시지가 표시되는 확인란 **[!UICONTROL 특수 문자]** 활성화된 경우 입력 필드. 이 필드의 모든 문자가 출력에 제거됩니다. 멀티바이트 문자는 지원되지 않습니다.

## Regex

차원에 정규 표현식을 적용하여 원하는 값을 검색합니다.

* **[!UICONTROL Regex]**: 정규 표현식 공식입니다.
* **[!UICONTROL 출력 형식]**: 텍스트를 추가하거나 regex 하위 그룹 출력의 순서를 변경할 수 있는 선택적 필드입니다. 이 필드가 비어 있으면 문자열 출력은 평가된 regex 표현식입니다.
* **[!UICONTROL 대/소문자 구분]**: 활성화된 경우 일반 표현식을 대/소문자를 구분하도록 하는 확인란입니다.

CJA에서는 Perl regex 구문의 하위 집합을 사용합니다. 입력이 정규 표현식과 일치하지 않으면 **[!UICONTROL 출력 형식]** 비어 있는 경우 [값 옵션이 없음](no-value-options.md) 적용합니다. 지원되는 표현식은 다음과 같습니다.

| 표현식 | 설명 |
| --- | --- |
| `a` | 단일 문자 `a`. |
| `a|b` | 단일 문자 `a` 또는 `b`. |
| `[abc]` | 단일 문자 `a`, `b`, 또는 `c`. |
| `[^abc]` | 다음을 제외한 모든 단일 문자 `a`, `b`, 또는 `c`. |
| `[a-z]` | 범위의 모든 단일 문자 `a`-`z`. |
| `[a-zA-Z0-9]` | 범위의 모든 단일 문자 `a`-`z`, `A`-`Z`, 또는 자릿수 `0`-`9`. |
| `^` | 줄의 시작 부분과 일치합니다. |
| `$` | 라인 끝에 일치합니다. |
| `\A` | 문자열 시작. |
| `\z` | 문자열 끝. |
| `.` | 모든 문자와 일치합니다. |
| `\s` | 모든 공백 문자. |
| `\S` | 모든 비공백 문자. |
| `\d` | 모든 숫자. |
| `\D` | 모든 비숫자. |
| `\w` | 모든 문자, 숫자 또는 밑줄입니다. |
| `\W` | 모든 비단어 문자. |
| `\b` | 모든 단어 경계. |
| `\B` | 단어 경계가 아닌 모든 문자 |
| `\<` | 단어 시작. |
| `\>` | 끝. |
| `(...)` | 둘러싸인 모든 항목 캡처. |
| `(?:...)` | 비표시 캡처. 출력 문자열에서 일치 항목을 참조하지 않도록 합니다. |
| `a?` | 0 또는 1 `a`. |
| `a*` | 0개 이상 `a`. |
| `a+` | 하나 더 `a`. |
| `a{3}` | 정확히 3개 `a`. |
| `a{3,}` | 3개 이상 `a`. |
| `a{3,6}` | 3~6 사이 `a`. |

출력 자리 표시자도 지원됩니다. 에서는 이러한 시퀀스를 사용할 수 있습니다 **[!UICONTROL 출력 형식]** 원하는 문자열 출력을 얻기 위해 임의 횟수와 임의 순서로.

| 출력 자리 표시자 시퀀스 | 설명 |
| --- | --- |
| `$&` | 전체 표현식과 일치하는 항목을 출력합니다. |
| `$n` | n번째 하위 표현식과 일치하는 항목을 출력합니다. 예, `$1` 첫 번째 하위 표현식을 출력합니다. |
| ``$` `` | 찾은 마지막 일치 항목의 끝(또는 이전 일치 항목이 없는 경우 텍스트 시작) 및 현재 일치 항목의 시작 사이에 있는 텍스트를 출력합니다. |
| `$+` | 정규 표현식에서 마지막으로 표시된 하위 표현식과 일치하는 항목을 출력합니다. |
| `$$` | 문자열 문자를 출력합니다. `"$"`. |