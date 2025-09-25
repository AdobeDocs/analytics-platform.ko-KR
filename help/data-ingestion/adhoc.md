---
title: 임시 데이터 수집 및 사용
description: Customer Journey Analytics에서 Ad Hoc을 수집 및 사용하는 방법 설명
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
exl-id: 17b5842f-dc81-481f-8b21-dc90a133adcf
source-git-commit: e5975a7bb60f4a2386997024c4615f95be648363
workflow-type: tm+mt
source-wordcount: '1623'
ht-degree: 23%

---

# 임시 데이터 수집 및 사용

이 빠른 시작 안내서에서는 임시 데이터를 Experience Platform으로 수집한 다음 Customer Journey Analytics에서 해당 데이터를 사용하는 방법을 설명합니다.

이를 구현하려면 다음 작업을 수행해야 합니다.

- Experience Platform에서 **CSV 파일로 데이터 세트를 만듭니다**. 이 워크플로우는 수집하려는 데이터의 모델(스키마)과 데이터(데이터 세트)를 수집할 위치를 정의합니다.

- Customer Journey Analytics에서 **연결 설정**. 이 연결에는 Experience Platform Ad Hoc 데이터 세트가 포함되어야 합니다.

- Customer Journey Analytics에서 사용할 임시 데이터의 필드에서 지표와 차원을 정의하려면 Analysis Workspace에서 **데이터 보기를 설정합니다**.

- Customer Journey Analytics에서 **프로젝트를 설정**&#x200B;하여 보고서 및 시각화를 빌드합니다.



>[!NOTE]
>
>이 빠른 시작 안내서는 를 사용하여 Experience Platform으로 임시 데이터를 수집하고 Customer Journey Analytics에서 해당 임시 데이터를 사용하는 방법에 대한 간단한 안내서입니다. 추가 정보를 참고하는 경우 연구하는 것이 좋습니다.


## CSV 파일로 데이터 세트 만들기

이 빠른 시작의 경우 조회 데이터를 나타내며 아래에 표시된 것과 유사한 정보를 포함하는 CSV 파일을 사용하려고 합니다.

| _ID | tracking_code | ad_group | campaign_name |
| ---: | :---          | :---        | :---          |
| 1 | abc123 | 광고 그룹 | 123 캠페인 |
| 2 | def123 | def-adgroup | 123 캠페인 |
| 3 | ghi123 | -그룹 | 123 캠페인 |
| 4 | abc456 | 광고 그룹 | 캠페인 |
| 5 | def456 | def-adgroup | 캠페인 |

>[!NOTE]
>
>레코드 기반(조회, 프로필) 데이터에 대해 애드혹 데이터 세트 및 스키마를 사용합니다. 애드혹 데이터 세트 및 스키마는 덜 적합하며 시계열(이벤트, 요약) 데이터에 대해 고려되지 않아야 합니다.

임시 데이터에 대해 XDM 스키마를 만들 필요가 없습니다. Experience Platform에서는 CSV 파일의 데이터를 기반으로 다음과 같은 워크플로우를 지원합니다.

1. 애드혹 스키마를 자동으로 생성합니다. 해당 스키마는 CSV 파일의 열을 준수합니다.
1. CSV 파일의 데이터를 포함하는 데이터 세트를 만듭니다.

워크플로우를 시작하려면 다음을 수행하십시오.

1. Experience Platform 인터페이스의 왼쪽 레일에서 **[!UICONTROL 워크플로]**&#x200B;를 선택합니다.
1. ![DataAdd](/help/assets/icons/DataAdd.svg) **[!UICONTROL CSV 파일에서 데이터 집합 만들기]**&#x200B;를 선택합니다.
1. 오른쪽 창에서 **[!UICONTROL 시작]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL 워크플로]** > **[!UICONTROL CSV 파일에서 데이터 집합 만들기]** 마법사에서:
   1. **[!UICONTROL 데이터 집합 구성]** 단계:
      1. 데이터 집합에 대한 **[!UICONTROL 이름]**&#x200B;을(를) 입력하십시오. 예: `Sample Data From CSV`.
      1. 선택적 **[!UICONTROL 설명]**&#x200B;을(를) 추가합니다. 예: `Sample data from a CSV file`.
      1. 선택적 **[!UICONTROL 태그]**&#x200B;를 하나 이상 추가하거나 기존 **[!UICONTROL 태그]**&#x200B;를 하나 이상 선택하십시오.

         ![임시 데이터 집합 구성](assets/adhoc-dataset-configure.png)

      1. **[!UICONTROL 다음]**&#x200B;을 선택합니다.
   1. **[!UICONTROL 데이터 추가]** 단계:
      1. 컴퓨터 또는 네트워크에서 CSV 파일을 선택하려면 **[!UICONTROL 파일 선택]**&#x200B;을 선택하십시오. 또는 컴퓨터 또는 네트워크의 해당 위치에서 **[!UICONTROL 파일을 드래그 앤 드롭]**&#x200B;합니다. 파일이 업로드되고 **[!UICONTROL 샘플 데이터]**&#x200B;가 표시됩니다.
      1. 기본 설정에 따라 **[!UICONTROL 오류 진단]** 및 **[!UICONTROL 부분 수집 사용]**&#x200B;을 사용하거나 사용하지 않도록 설정하십시오. **[!UICONTROL 부분 수집을 활성화]**&#x200B;할 때 **[!UICONTROL 오류 임계값 %]**&#x200B;을(를) 정의할 수 있습니다.

         ![임시 데이터 집합에 데이터 추가](assets/adhoc-dataset-adddata.png)

      1. **[!UICONTROL 마침]**&#x200B;을 선택합니다.

데이터를 준비하고 업로드하면 Experience Platform 인터페이스의 **[!UICONTROL 데이터 세트]**(으)로 리디렉션됩니다.<br/> 상태가 **[!UICONTROL StatusOrange]** **[!UICONTROL 처리]**&#x200B;인 ![CSV의 샘플 데이터](/help/assets/icons/StatusOrange.svg) 데이터 집합에 대해 **[!UICONTROL 데이터 집합 활동]**&#x200B;이 표시됩니다.

![임시 데이터에 대한 데이터 집합 활동](assets/datasets-dataset-activity.png)

임시 데이터를 검사하려면:

1. Experience Platform 인터페이스의 왼쪽 레일에서 **[!UICONTROL 데이터 세트]**&#x200B;를 선택합니다.
1. **[!UICONTROL 데이터 세트]**&#x200B;에서 **[!UICONTROL 찾아보기]** 탭을 선택하십시오. 데이터 세트가 나열되어 있습니다.
1. **[!UICONTROL 스키마]** 열에서 스키마 이름을 선택하십시오. 예: **[!UICONTROL CSV의 샘플 데이터...]**

   ![임시 데이터 세트에 대한 스키마 선택](assets/adhoc-schema-selection.png)

1. 팝업에서 **[!UICONTROL 스키마 이름]**&#x200B;을(를) 선택합니다. 예: **[!UICONTROL CSV의 샘플 데이터 - 임시 스키마 - XXXXXXXXXXX]**. **[!UICONTROL 스키마]** > **[!UICONTROL CSV의 샘플 데이터 - 임시 스키마 - XXXXXXXXXXX]** 인터페이스로 리디렉션됩니다.

**[!UICONTROL 스키마]** > **[!UICONTROL CSV의 샘플 데이터 - 임시 스키마 - XXXXXXXXXXX]** 인터페이스에서:

- **[!UICONTROL 스키마]** > **[!UICONTROL CSV의 샘플 데이터 - 임시 스키마 - XXXXXXXXXXX]** 아래에서 최상위 테넌트 이름 개체를 선택하여 개체 내의 필드를 표시합니다. 개체 내의 필드는 CSV 파일의 구조를 나타냅니다. 애드혹 데이터의 업로드를 기반으로 스키마가 자동으로 생성됩니다.

  ![임시 스키마](dataset/../assets/adhoc-schema.png)

  >[!NOTE]
  >
  >워크플로는 스키마의 모든 필드를 문자열 유형으로 정의합니다. 이후 단계에서는 이 유형을 변경할 수 없습니다. 임시 스키마를 보다 유연하게 정의해야 하는 경우 [API를 사용하여 임시 스키마를 만들고](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/tutorials/ad-hoc)한 다음 [스키마에서 데이터 집합 만들기](https://experienceleague.adobe.com/ko/docs/experience-platform/catalog/datasets/user-guide#schema) 워크플로우를 사용하십시오.
  > 




## 연결 설정

Customer Journey Analytics에서 Experience Platform 데이터 세트를 사용하려면 [워크플로](#create-a-dataset-with-a-csv-file)에서 생성된 임시 데이터 세트를 포함하는 연결을 만듭니다

연결을 통해 Experience Platform의 데이터 세트를 Workspace에 통합할 수 있습니다. 이러한 데이터 세트에 대해 보고하려면 먼저 Experience Platform과 Workspace의 데이터 세트 간에 연결을 설정해야 합니다.

연결을 만드는 경우:

1. Customer Journey Analytics UI의 상단 메뉴에서 **[!UICONTROL 연결]**(선택 사항: **[!UICONTROL 데이터 관리]**)을 선택합니다.

1. **[!UICONTROL 새 연결 만들기]**&#x200B;를 선택합니다.

1. **[!UICONTROL 제목 없는 연결]** 화면에서:

   1. **[!UICONTROL 연결 설정]**&#x200B;에서 연결의 이름을 지정하고 연결에 대해 설명합니다.

   1. **[!UICONTROL 데이터 설정]**&#x200B;의 **[!UICONTROL 샌드박스 목록에서 올바른 샌드박스]**&#x200B;를 선택하고 **[!UICONTROL 일일 평균 이벤트 수]** 목록에서 일일 이벤트 수를 선택합니다.

      ![연결 설정](./assets/cja-connections-1.png)

   1. **[!UICONTROL 데이터 세트 추가]**&#x200B;를 선택합니다.

1. **[!UICONTROL 데이터 세트 추가]**&#x200B;의 **[!UICONTROL 데이터 세트 선택]** 단계에서:

   1. 이전에 만든 데이터 세트(예: **[!UICONTROL CSV의 샘플 데이터]**)와 연결에 포함할 다른 데이터 세트를 선택하십시오. 임시 데이터 세트에는 **[!UICONTROL 임시]** [!UICONTROL 데이터 세트 유형]이 있습니다.

      ![데이터 세트 추가](./assets/cja-connections-adhoc-2.png)

   1. **[!UICONTROL 다음]**&#x200B;을 선택합니다.

1. **[!UICONTROL 데이터 세트 추가]**&#x200B;의 **[!UICONTROL 데이터 세트 설정]** 단계에서:

   임시 데이터 세트의 경우:

   1. 임시 데이터 세트 유형을 선택합니다. 예: **[!UICONTROL 조회]**.
   1. Ad Hoc 스키마에 정의된 사용 가능한 키 중에서 **[!UICONTROL 키]**&#x200B;을(를) 선택합니다.
   1. 연결의 일부로 추가한 이벤트 데이터 세트에서 **[!UICONTROL 일치하는 키]**&#x200B;를 선택합니다.
   1. **[!UICONTROL 데이터 소스 유형]** 목록에서 올바른 데이터 소스를 선택합니다. **[!UICONTROL 기타]**&#x200B;를 지정한 경우 데이터 소스에 대한 설명을 추가합니다.

   1. 환경 설정에 따라 **[!UICONTROL 새 데이터 모두 가져오기]** 및 **[!UICONTROL 데이터 세트 기존 데이터 채우기]**&#x200B;를 설정합니다.

      ![데이터 세트 구성](./assets/cja-connections-3-adhoc.png)

   1. **[!UICONTROL 데이터 세트 추가]**&#x200B;를 선택합니다.

   1. **[!UICONTROL 저장]**&#x200B;을 선택합니다.

임시 데이터 세트에 사용할 수 있는 설정에 대한 자세한 내용은 [임시 데이터 세트 설정](/help/connections/create-connection.md#adhoc-dataset)을 참조하십시오.

>[!IMPORTANT]
>
>시계열 데이터에 임시 데이터 세트 및 스키마를 사용하지 않는 것이 좋다는 일반적인 권장 사항 외에 시계열 데이터에 **[!UICONTROL CSV에서 데이터 세트 만들기]** 워크플로우를 사용할 수 없습니다. 이 워크플로우는 나중에 수정할 수 없는 문자열 유형의 모든 필드를 정의합니다. 시계열 기반 데이터 세트(이벤트 또는 요약)를 연결에 추가할 때 이 데이터 세트 유형에는 DateTime 유형의 필드를 하나 이상 정의해야 합니다.<br/>임시 시계열 데이터를 사용해야 하는 경우 [API를 사용하여 임시 스키마를 만들고](https://experienceleague.adobe.com/ko/docs/experience-platform/xdm/tutorials/ad-hoc#token_type=bearer&expires_in=43197438)그런 다음 [스키마에서 데이터 집합 만들기](https://experienceleague.adobe.com/ko/docs/experience-platform/catalog/datasets/user-guide#schema) 워크플로우를 사용하십시오.


[연결](/help/connections/overview.md)을 만든 후 [데이터 세트 선택 및 결합](/help/connections/combined-dataset.md), [연결의 데이터 세트 상태 및 데이터 수집 상태 확인](/help/connections/manage-connections.md) 등 다양한 관리 작업을 수행할 수 있습니다.

## 데이터 보기 설정

데이터 보기는 Customer Journey Analytics와 관련된 컨테이너입니다. 이를 통해 연결에서 데이터를 해석하는 방법을 결정할 수 있습니다. Analysis Workspace에서 사용 가능한 모든 차원과 지표를 지정하고, 해당 차원과 지표가 데이터를 얻을 수 있는 열을 지정합니다. 데이터 보기는 Analysis Workspace의 데이터에 대한 보고 준비에 따라 정의됩니다.

데이터 보기를 만드는 경우:

1. Customer Journey Analytics UI의 상단 메뉴에서 **[!UICONTROL 데이터 보기]**(선택 사항: **[!UICONTROL 데이터 관리]**)를 선택합니다.

1. **[!UICONTROL 새 데이터 보기 만들기]**&#x200B;를 선택합니다.

1. **[!UICONTROL 구성]** 단계에서:

   1. [연결](#set-up-a-connection) 목록에서 **[!UICONTROL 연결]**&#x200B;을 선택합니다.

   1. 연결의 이름을 지정하고 (선택 사항) 연결에 대해 설명합니다.

      ![데이터 보기 구성](./assets/cja-dataview-1.png)

   1. **[!UICONTROL 저장 후 계속]**&#x200B;을 선택합니다.

1. **[!UICONTROL 구성 요소]** 단계에서:

   1. 포함할 스키마 필드 및/또는 표준 구성 요소를 **[!UICONTROL METRICS]** 또는 **[!UICONTROL DIMENSIONS]** 구성 요소 상자에 추가하십시오. 임시 데이터가 포함된 데이터 세트에서 관련 필드를 추가해야 합니다. 이러한 필드에 액세스하려면:

      1. **[!UICONTROL 이벤트 데이터 세트]**&#x200B;를 선택하십시오.
      1. **[!UICONTROL 임시 및 모델 기반 필드]**&#x200B;를 선택하십시오.

         ![데이터 보기 - 임시 구성 요소](assets/cja-dataview-components-adhoc.png)

      1. 임시 스키마에서 **[!UICONTROL 지표]** 또는 **[!UICONTROL 차원]**(으)로 필드를 끌어다 놓습니다.



   1. 선택적으로 [파생 필드](/help/data-views/derived-fields/derived-fields.md)를 사용하여 임시 필드를 기본 문자열 형식 및 형식에서 다른 형식 또는 형식으로 수정합니다.

   1. **[!UICONTROL 저장 후 계속]**&#x200B;을 선택합니다.

1. **[!UICONTROL 설정]** 단계에서:

   설정은 그대로 두고 **[!UICONTROL 저장 후 마침]**&#x200B;을 선택합니다.

데이터 보기를 만들고 편집하는 방법에 대한 자세한 내용은 [데이터 보기 개요](../data-views/data-views.md)를 참조하십시오. 데이터 보기에서 사용할 수 있는 구성 요소와 세그먼트 및 세션 설정을 사용하는 방법을 알아봅니다.


## 프로젝트 설정

Analysis Workspace은 데이터를 기반으로 분석을 빠르게 작성하고 통찰력을 공유할 수 있는 유연한 브라우저 도구입니다. 작업 영역 프로젝트를 사용하여 데이터 구성 요소, 테이블 및 시각화를 결합하여 분석을 작성하고 조직의 모든 사람과 공유할 수 있습니다.

프로젝트를 만드는 경우:

1. Customer Journey Analytics UI의 상단 메뉴에서 **[!UICONTROL 프로젝트]**&#x200B;를 선택합니다.

1. 왼쪽 탐색 영역에서 **[!UICONTROL 프로젝트]**&#x200B;를 선택합니다.

1. **[!UICONTROL 프로젝트 만들기]**&#x200B;를 선택합니다.

1. **[!UICONTROL 빈 프로젝트]**&#x200B;를 선택합니다.

1. 목록에서 [데이터 보기](#set-up-a-data-view)를 선택합니다.

1. 첫 번째 보고서를 만들려면 [!UICONTROL 패널]의 [!UICONTROL 자유 형식 테이블]에서 차원 및 지표를 끌어서 놓습니다. 임시 데이터를 기반으로 하는 지표 또는 차원을 포함합니다.

구성 요소, 시각화 및 패널을 사용하여 프로젝트를 만들고 분석을 빌드하는 방법에 대한 자세한 내용은 [Analysis Workspace 개요](../analysis-workspace/home.md)를 참조하십시오.

>[!SUCCESS]
>
>모든 단계가 완료되었습니다. 먼저 수집할 임시 데이터(CSV 파일)를 정의합니다. 워크플로우를 사용하여 해당 CSV 파일에서 임시 데이터 세트 및 스키마를 생성했습니다. 수집된 임시 데이터 및 기타 데이터를 사용하도록 Customer Journey Analytics에서 연결을 정의했습니다. 데이터 보기 정의를 통해 사용할 차원 및 지표를 지정했고 최종적으로 데이터를 시각화 및 분석하는 첫 번째 프로젝트를 제작했습니다.
