---
title: 제품 사용 개요
description: 조직에서 Customer Journey Analytics을 사용하는 방법에 대한 인사이트 및 보고서를 봅니다.
exl-id: 3806ca7c-ee90-4222-9ffd-2e791c4550e5
source-git-commit: dbf4ff28f693085320c3e496ea99eede2ddb17d2
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 12%

---

# 제품 사용 개요

제품 사용은 조직이 Customer Journey Analytics을 사용하는 방법에 대한 분석 데이터를 볼 수 있는 기능을 조직에 제공합니다. Customer Journey Analytics을 사용하는 모든 조직에서 사용할 수 있습니다. 활성화되면 다음 Adobe Experience Platform 구성 요소가 자동으로 생성되고 연결됩니다. 이러한 구성 요소는 모두 시스템 소유이며 읽기 전용이며 편집할 수 없습니다.

* Adobe Experience Platform의 스키마
* Adobe Experience Platform의 데이터 세트
* Customer Journey Analytics 중인 연결
* Customer Journey Analytics의 데이터 보기

활성화되면 모든 데이터 수집 및 설정이 자동으로 구성됩니다. 사용자가 Analysis Workspace에서 작업을 수행할 때마다 해당 작업이 추적되어 보고에 사용할 수 있습니다.

>[!IMPORTANT]
>
>이 기능은 Adobe Experience Platform의 계약 행 제한에 포함됩니다. 활성화하기 전에 조직에서 이 기능으로 생성된 데이터를 수용할 수 있는지 확인하십시오.

## 제품 사용 활성화

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 도구]** > **[!UICONTROL 제품 사용]**

Customer Journey Analytics에서 인터페이스의 이 섹션으로 이동하면 이 기능을 활성화할 수 있는 [데이터 설정](data-settings.md)(으)로 이동합니다.

## 사용 가능한 차원

제품 사용을 활성화하면 다음 차원을 사용할 수 있습니다. 차원 설정을 변경하려면 시스템 소유 데이터 보기의 복사본을 만들고 Analysis Workspace에서 복사된 데이터 보기를 사용합니다.

* **[!UICONTROL 작업 이름]**: 사용자가 수행한 작업의 유형입니다. 데이터 보기 설정에서 사본을 만들어 이 차원을 원하는 지표로 사용할 수 있습니다. Dimension 항목은 다음과 같습니다.
   * [!UICONTROL 속성 추가]
   * [!UICONTROL 구성 요소 추가]
   * [!UICONTROL 패널 추가]
   * [!UICONTROL 시각화 추가]
   * [!UICONTROL 새로운 가이드 분석 만들기]
   * [!UICONTROL 새 프로젝트 만들기]
   * [!UICONTROL 구성 요소 조정]
   * [!UICONTROL CSV 다운로드]
   * [!UICONTROL PDF 다운로드]
   * [!UICONTROL 안내가 있는 분석 로드]
   * [!UICONTROL 프로젝트 로드]
   * [!UICONTROL 새 스코어카드가 로드됨]
   * [!UICONTROL 데이터 사전 열기]
   * [!UICONTROL 지능형 캡션 열기]
   * [!UICONTROL 프로젝트 공유]
   * [!UICONTROL 실험 패널 실행]
   * [!UICONTROL 프로젝트 저장]
   * [!UICONTROL 스코어카드가 저장됨]
   * [!UICONTROL 파일 보내기]
   * [!UICONTROL 일정에 따라 파일 보내기]
   * [!UICONTROL 모든 사람과 프로젝트 공유]
   * [!UICONTROL Workspace 사용자와 프로젝트 공유]
* **[!UICONTROL 사용된 속성 모델]**: 구성 요소가 사용하는 속성 모델의 유형입니다. Dimension 항목은 다음과 같습니다.
   * [!UICONTROL 마지막 터치]
   * [!UICONTROL 첫 번째 터치]
   * [!UICONTROL 선형]
   * [!UICONTROL 기여도]
   * [!UICONTROL 동일한 터치]
   * [!UICONTROL U자형]
   * [!UICONTROL J 곡선]
   * [!UICONTROL 역 J]
   * [!UICONTROL 시간 감소]
   * [!UICONTROL 사용자 정의]
   * [!UICONTROL 알고리즘]
* **[!UICONTROL 구성 요소 이름]**: 추가, 제거 또는 수정된 구성 요소의 이름입니다.
* **[!UICONTROL 구성 요소 형식]**: 추가, 제거 또는 수정된 구성 요소의 형식입니다. Dimension 항목은 다음과 같습니다.
   * [!UICONTROL 차원]
   * [!UICONTROL 지표]
   * [!UICONTROL 필터]
   * [!UICONTROL 계산된 지표]
   * [!UICONTROL 날짜 범위]
   * [!UICONTROL 주석]
   * [!UICONTROL 경고]
* **[!UICONTROL 로그인 사용자]**: 작업을 수행한 사용자입니다.
* **[!UICONTROL 사용된 패널]**: 구성 요소가 추가, 제거 또는 수정된 패널입니다. Dimension 항목은 다음과 같습니다.
   * [!UICONTROL 속성]
   * [!UICONTROL 빈 패널]
   * [!UICONTROL 실험]
   * [!UICONTROL 자유 형식]
   * [!UICONTROL 다음 또는 이전 항목]
   * [!UICONTROL 빠른 인사이트]
   * [!UICONTROL 트렌드]
   * [!UICONTROL 단계]
   * [!UICONTROL 사용자 성장]
   * [!UICONTROL 영향]
   * [!UICONTROL 사용자 스트림]
   * [!UICONTROL Retention]
   * [!UICONTROL 기능 매트릭스]
* **[!UICONTROL 프로젝트 이름]**: 프로젝트의 이름입니다.
* **[!UICONTROL 프로젝트 형식]**: 프로젝트 형식입니다. Dimension 항목은 다음과 같습니다.
   * `workspace-projects`
   * `guided-analysis`
   * `mobile-scorecard-builder`
* **[!UICONTROL 사용자 ID]**: 이벤트를 트리거한 사용자 ID입니다.
* **[!UICONTROL 사용된 시각화]**: 추가, 제거 또는 수정된 시각화입니다. Dimension 항목은 다음과 같습니다.
   * [!UICONTROL 자유 형식 테이블]
   * [!UICONTROL 코호트 테이블]
   * [!UICONTROL 폴아웃]
   * [!UICONTROL 흐름]
   * [!UICONTROL 여정 캔버스 reportlet]
   * [!UICONTROL 영역]
   * [!UICONTROL 스택 영역]
   * [!UICONTROL 막대]
   * [!UICONTROL 스택 막대]
   * [!UICONTROL 글머리 기호]
   * [!UICONTROL 콤보]
   * [!UICONTROL 도넛]
   * [!UICONTROL 히스토그램]
   * [!UICONTROL 가로 막대형]
   * [!UICONTROL 스택 가로 막대]
   * [!UICONTROL 주요 지표 요약]
   * [!UICONTROL Line]
   * [!UICONTROL 맵]
   * [!UICONTROL 분산]
   * [!UICONTROL 섹션 머리글]
   * [!UICONTROL 요약 변경]
   * [!UICONTROL 요약 번호]
   * [!UICONTROL Text]
   * [!UICONTROL 트리맵]
   * [!UICONTROL 벤]

프로젝트를 단순히 열거나 볼 때 제품 사용량은 개별 프로젝트 구성 요소를 추적하지 않습니다. 그러나 프로젝트를 여는 사용자 작업은 추적됩니다.
