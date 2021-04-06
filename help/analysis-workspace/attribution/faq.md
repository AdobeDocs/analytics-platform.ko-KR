---
title: 속성 FAQ
description: 속성과 관련하여 자주 묻는 질문에 대한 답변을 얻습니다.
exl-id: 3153d8c9-4ca8-4189-8a2f-511a87e8ac17
translation-type: tm+mt
source-git-commit: 93f4f65a3b321d16a37ed21339ef811e1f55f9ca
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 88%

---

# 속성 FAQ

>[!NOTE]
>
>Customer Journey Analytics의 Analysis Workspace 설명서를 보고 계십니다. 이 기능은 [기존 Adobe Analytics의 Analysis Workspace](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html)와 약간 다릅니다. [추가 정보...](/help/getting-started/cja-aa.md)

**속성을 사용할 때 &quot;없음&quot; 라인 항목은 무엇입니까?**

&#39;없음&#39; 라인 항목은 전환 확인 기간 내에 터치 포인트 없이 발생한 모든 전환을 나타내는 잡동사니 주머니입니다. 보고 기간에 더 긴 시간 범위를 포함해 보십시오.

**기여도 분석 모델을 사용할 때때로 보고 기간 밖의 날짜가 표시되는 이유는 무엇입니까?**

이러한 추가적인 날짜는 방문자 보고 전환 확인 기간으로 인한 것입니다. 자세한 내용은 Analytics KB의 [보고 기간을 벗어나서 나타나는 데이터](https://helpx.adobe.com/kr/analytics/kb/data-appearing-outside-reporting-window.html)를 참조하십시오. Adobe에서는 향후 릴리스에서 이러한 추가 행을 필터링할 계획입니다.

**언제 방문과 방문자 기여도 분석 전환 확인을 사용해야 합니까?**

기여도 분석 전환 확인의 선택은 사용 사례에 따라 다릅니다. 일반적으로 전환 시간이 단일 방문보다 오래 걸리는 경우 방문자 전환 확인을 권장합니다. 더 긴 방문 정의를 사용하여 데이터 보기를 만드는 것도 잠재적 솔루션입니다.

**속성을 사용할 때 prop 및 eVar는 어떻게 비교합니까?**

속성은 보고서 런타임 시 다시 계산되며 따라서 속성 모델링을 위한 prop 또는 eVar(또는 다른 차원) 간 차이점은 없습니다. Prop은 모든 전환 확인 기간 또는 속성 모델을 사용하여 지속될 수 있으며 eVar 할당/만료 설정은 무시됩니다.

**지원되지 않는 차원 및 지표는 무엇입니까?**

속성 패널은 모든 차원을 지원합니다. 지원되지 않는 지표는 다음과 같습니다.

* 고유 방문자 수
* 방문 횟수
* 발생
* 페이지 보기 횟수
* A4T 지표
* 체류 시간 지표
* 바운스 수
* 바운스 비율
* 항목
* 종료
* 페이지를 찾을 수 없음
* 검색 결과
* 단일 페이지 방문 횟수
* 단일 액세스

**필터는 어떻게 작동합니까?**

속성은 항상 필터 전에 실행되며 다른 보고서 필터가 적용되기 전에 세그먼테이션이 실행됩니다.
