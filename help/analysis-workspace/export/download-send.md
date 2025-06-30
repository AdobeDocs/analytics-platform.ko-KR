---
description: Analysis Workspace 프로젝트에서 데이터를 다운로드하는 다양한 가능성에 대해 알아봅니다.
title: Analysis Workspace 프로젝트 및 데이터 다운로드
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: 084c995658a5cf698d253f1c15229f621a8c55d5
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 25%

---

# 프로젝트 및 데이터 다운로드

Analysis Workspace 프로젝트 및 데이터를 로컬 장치에 다운로드할 수 있습니다. 이 다운로드는 데이터, CSV(쉼표로 구분된 값 데이터) 파일 또는 PDF(휴대용 문서 형식) 문서를 복사할 수 있습니다.

* 다운로드한 파일에 시각화를 포함하려면 PDF 옵션을 선택합니다.
* 일반 텍스트 데이터만 필요한 경우 CSV 및 복사된 데이터 옵션을 선택합니다.

Customer Journey Analytics 데이터를 내보내는 추가 방법은 [내보내기 개요](/help/analysis-workspace/export/export-project-overview.md)에 설명되어 있습니다.

## CSV 또는 PDF로 다운로드 {#download-project}

![CSV 다운로드 및 PDF 다운로드 옵션이 강조 표시된 프로젝트 드롭다운 메뉴.](assets/download-project.png)

프로젝트를 PDF으로 다운로드할 때는 다음 사항을 고려하십시오.

* 프로젝트가 Adobe 서버에서 다시 실행되어 PDF 형식으로 렌더링되므로 다운로드에 몇 분 정도 걸릴 수 있습니다. 브라우저에서 프로젝트가 다운로드될 때까지 프로젝트를 종료하지 마십시오.  다운로드가 렌더링되는 동안 프로젝트를 계속 변경할 수 있습니다. PDF이 렌더링하는 데 5분 이상 걸리는 경우 대신 [PDF에 전자 메일을 보내십시오](../curate-share/send-schedule-files.md).
* 다운로드는 페이지 매김이 적용되지 않은 단일 페이지로 렌더링됩니다.
* PDF에는 Analysis Workspace의 브라우저 페이지에 표시되는 항목이 포함되어 있습니다. 사용자 지정 크기의 시각화 및 패널의 크기를 자동으로 조정해야 잘린 콘텐츠를 방지할 수 있습니다. 사용자 지정 크기의 시각화 또는 패널의 크기를 자동으로 조정하려면 ![크기 조정](/help/assets/icons/Resize.svg)을 선택하십시오.
* 자유 형식 테이블 내의 [하이퍼링크](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)를 다운로드한 PDF의 하이퍼링크로 설정합니다.



프로젝트를 PDF 파일로 다운로드하려면 다음 작업을 수행하십시오.

1. **[!UICONTROL 프로젝트]** > **[!UICONTROL PDF 다운로드]**를 선택합니다.
녹색 막대에 ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 다운로드가 요청되었습니다. 기다려 주십시오.]**&#x200B;이(가) 표시됩니다.

1. 다운로드가 준비되면 ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL *프로젝트 이름&#x200B;*PDF이 포함된 녹색 막대가 준비됩니다.]**이(가) 나타납니다.
PDF을 다운로드하려면**[!UICONTROL 다운로드]**를 선택하십시오. PDF이 정확히 표시되거나 다운로드되는 방법은 PDF 문서를 처리하기 위한 브라우저 구성에 따라 다릅니다.


프로젝트를 CSV 파일로 다운로드하려면 다음 작업을 수행하십시오.

* **[!UICONTROL 프로젝트]** > **[!UICONTROL CSV 다운로드]**&#x200B;를 선택합니다. 프로젝트는 브라우저 구성의 일부로 구성된 다운로드 폴더로 직접 다운로드됩니다. 파일 이름은 *프로젝트 이름* - *보고서 세트 이름* - *날짜*(예: `Example Project - Omni-Channel - Luma - Jun 30, 2025.csv`)로 구성됩니다.

## 클립보드에 복사 {#copy-data}

컨텍스트 메뉴의 **[!UICONTROL 클립보드에 복사]** 옵션을 사용하면 Analysis Workspace에서 데이터를 빠르게 복사하여 서드파티 도구에 붙여넣을 수 있습니다.

* 표시된 테이블 데이터를 복사하려면 테이블 헤더를 선택하고 컨텍스트 메뉴에서 **클립보드에 데이터 복사**&#x200B;를 선택합니다.
* 데이터의 일부를 복사하려면 테이블에서 선택한 다음 상황에 맞는 메뉴에서 **클립보드에 데이터 복사**&#x200B;를 선택합니다.

>[!TIP]
>
>핫키 **_cmd + c_**(macOS) 또는 **_ctrl + c_**(Windows)을 사용하여 선택 항목을 클립보드에 복사할 수 있습니다. 그런 다음 **_cmd + v_**(macOS) 또는 **_ctrl + v_**(Windows)을 사용하여 데이터를 붙여넣으십시오.


![선택 항목을 클립보드로 복사 옵션. ](assets/copy-clipboard.png){zoomable="yes"}

## CSV로 다운로드 {#download-data}

컨텍스트 메뉴에서 CSV로 다운로드 옵션을 사용하면 데이터 테이블 또는 시각화의 데이터 소스를 CSV로 다운로드할 수 있습니다.

이렇게 하려면 다음 작업을 수행하십시오.

* 테이블 또는 시각화의 헤더에서 컨텍스트 메뉴에서 **[!UICONTROL CSV로 데이터 다운로드]**&#x200B;를 선택합니다. 이렇게 하면 테이블에 표시된 데이터 또는 시각화를 위한 기본 데이터 소스가 CSV로 다운로드됩니다.

<!-- Only relevant as soon as CJA supports Map visualization 
  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.
-->

* 테이블의 상황에 맞는 메뉴에서 **[!UICONTROL 선택 항목을 CSV로 다운로드]**&#x200B;를 선택합니다. 전체 표시된 테이블과는 대조적으로 이 옵션을 사용하면 선택 항목만 다운로드됩니다.

![데이터를 CSV로 다운로드 옵션.](assets/download-data-as-csv.png)

## CSV로 항목 다운로드 {#download-items}

테이블에 있는 400개 이상의 데이터 행을 분석하려면 테이블 머리글 또는 행의 컨텍스트 메뉴에서 **CSV로 항목 다운로드(_Dimension 이름_)**&#x200B;를 선택합니다. 이 옵션은 정렬 옵션과 필터가 적용된 상태에서 선택한 차원에 대해 최대 50,000개의 차원 항목(테이블 정렬 기준)을 내보냅니다. 테이블 상단에서 이 옵션을 선택하면 테이블의 첫 번째 차원이 내보내집니다.

![CSV(페이지)로 항목 다운로드 옵션.](assets/download-items-as-csv.png)

자유 형식 테이블에는 제한이 적용되지 않습니다. 최적의 성능을 보장하려면 열이 20개 미만인 테이블에서 이 옵션을 사용하는 것이 좋습니다.

>[!TIP]
>
> 차원이 50,000개 항목을 초과하는 경우 다른 정렬 지표가 적용된 파일을 다운로드하거나 세그먼트를 적용합니다. 예를 들어 한 번의 다운로드에서 방문 횟수를 기준으로 내림차순으로 정렬한 다음 두 번째 다운로드에서 방문 횟수를 기준으로 오름차순으로 정렬합니다. 이 팁은 롱테일 항목을 검색하는 데 도움이 될 수 있습니다.

프로젝트 내에서 멀티태스킹을 할 수 있으며 다운로드가 진행되는 동안 동일한 탭에서 새 Workspace 프로젝트로 이동할 수도 있습니다. 새 브라우저 탭을 열면 다운로드가 일시 중지됩니다. Workspace를 완전히 종료하거나 브라우저 탭을 닫으면 다운로드가 취소됩니다.


### 다운로드한 항목 파일 {#items-file}

다운로드한 파일에는 자유 형식 테이블의 다음 기능이 적용됩니다.

* 모든 패널 세그먼트가 필터로 적용됩니다.
* 테이블에서 선택한 차원 **위** 분류는 각 열 위에 필터로 적용됩니다.
* 테이블에서 선택한 차원 **아래** 분류는 제거됩니다.

![다운로드한 .csv 파일을 Excel로 열립니다.](assets/download-items-file.png)

### 다운로드 알림 {#notifications}

파일이 다운로드되면 다음 알림이 표시됩니다.

* 파란색 **[!UICONTROL _테이블 이름&#x200B;_-_Dimension _.csv가 요청되었습니다. 진행 상황을 나타내는_x _% 완료]**. 언제든지 다운로드를 취소하려면&#x200B;**[!UICONTROL 다운로드 취소]**를 선택하십시오. 메시지를 닫고 다운로드를 취소하지 않으려면 ![CrossSize100](/help/assets/icons/CrossSize100.svg)을(를) 선택하십시오.
* 파일 다운로드가 완료되면 녹색 **[!UICONTROL _테이블 이름&#x200B;_-_Dimension _.csv가 다운로드되었습니다]**완료 알림이 표시됩니다. 파일이 브라우저에 대해 구성된 다운로드 폴더로 다운로드됩니다.

한 번에 두 개 이상의 다운로드를 요청하면 이전 다운로드가 완료될 때까지 각 추가 다운로드가 대기열에 있음을 알리는 알림을 받게 됩니다.


## 중요한 데이터 다운로드 {#sensitive}

데이터 다운로드를 방지하는 [데이터 거버넌스 정책](/help/data-views/data-governance.md)을 생각해 보십시오. 또한 이 정책이 보고하는 데이터 보기에서 설정됩니다. 그 결과, 프로젝트의 모든 다운로드(예: PDF 파일을 이메일로 보내거나 공유할 때)는 중요한 레이블이 지정된 데이터 필드를 해시합니다. Analysis Workspace에서 이러한 필드에 대한 분석을 수행할 수 있습니다. 이메일을 보내거나 프로젝트를 공유하려고 하면 PDF 또는 CSV 파일에 중요한 데이터 필드가 비어 있는 것으로 표시됩니다.

중요한 레이블이 지정된 데이터 필드가 데이터 보기에 포함된 경우 화면에서 데이터를 선택하고 복사하는 옵션이 데이터 보기의 모든 데이터에 대해 제한됩니다.

## FAQ {#faq}

| 질문 | 답변 |
| --- | --- |
| 다운로드한 PDF이 한 페이지로만 구성되는 이유는 무엇입니까? | [PDF 다운로드](#download-as-csv-or-pdf) 기능은 다운로드한 PDF에 페이지를 매기지 않습니다. |
| **[!UICONTROL CSV로 항목 다운로드]** 옵션을 사용하여 50,000개 이상의 항목을 내보낼 수 있습니까? | 각 다운로드에는 최대 50,000개의 차원 항목이 포함될 수 있지만 테이블의 정렬을 변경하여 롱테일 항목을 검색하거나 필터를 적용하여 더 많은 특정 항목을 다운로드할 수 있습니다. |
| **[!UICONTROL 시각화 복사]**&#x200B;의 기능은 무엇입니까? | [!UICONTROL **클립보드에 데이터 복사**] 또는 [!UICONTROL **클립보드에 선택 항목 복사**]&#x200B;와 달리 **[!UICONTROL 시각화 복사]** 상황에 맞는 메뉴 옵션은 내보내기 옵션이 아닙니다. 이 옵션을 사용하면 Workspace의 한 위치에서 다른 위치로 [시각화를 복사](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu) 또는 [패널을 복사](/help/analysis-workspace/c-panels/panels.md#context-menu)할 수 있습니다. 예를 들어 동일한 프로젝트의 한 패널에서 다른 패널로 또는 한 프로젝트에서 다른 프로젝트로 복사할 수 있습니다. |
