---
title: 기존 Adobe Analytics의 데이터 수집 및 사용
description: 기존 Adobe Analytics에서 데이터를 수집하는 방법을 설명합니다.
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: f910f8e810c5c5d6f4d43aff2b609d8bf6c131ca
workflow-type: tm+mt
source-wordcount: '1143'
ht-degree: 10%

---


# 기존 Adobe Analytics의 데이터 수집 및 사용

이 빠른 시작 안내서에서는 Customer Journey Analytics에서 Adobe Analytics에서 수집한 데이터를 사용하는 방법을 설명합니다.

>[!PREREQUISITES]
>
>Adobe Analytics에 대해 다음 문서화된 구현 방법을 사용하여 하나 이상의 웹 사이트에 라이선스가 부여되고 배포됩니다.
>
>- [Experience Platform Edge를 사용하여 Analytics 구현](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/overview.html?lang=ko-kr)
>
>- [Adobe Analytics 확장을 사용하여 Analytics 구현](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=ko)
>
>- [Javascript를 사용하여 Analytics 구현](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=en)


이를 위해서는 다음을 수행해야 합니다.

- **Adobe Analytics 소스 커넥터 설정** Adobe Experience Platform. 이렇게 하면 현재 Adobe Analytics 데이터를 Adobe Experience Platform의 데이터 세트에 수집하는 작업이 수행됩니다.

- **연결 설정** Customer Journey Analytics에서 확인하십시오. 이 연결에는 Adobe Experience Platform 데이터 세트가 포함되어야 합니다(최소).

- **데이터 보기 설정** Customer Journey Analytics에서 Analysis Workspace에서 사용할 지표 및 차원을 정의합니다.

- **프로젝트 설정** Customer Journey Analytics에서 보고서 및 시각화를 작성합니다.


>[!NOTE]
>
>Adobe Analytics 소스 커넥터를 사용하여 데이터를 수집하고 Customer Journey Analytics에서 해당 데이터를 사용하는 방법에 대한 간단한 안내서입니다.  참조할 때는 추가 정보를 학습하는 것이 좋습니다.


## Adobe Analytics 소스 커넥터 설정

Adobe Analytics 소스 커넥터를 사용하면 Adobe Analytics 보고서 세트 데이터를 Adobe Experience Platform으로 가져올 수 있습니다.

Adobe Analytics 소스 커넥터를 만들려면 다음을 수행하십시오.

1. 플랫폼 UI에서 **[!UICONTROL 소스]** 왼쪽 레일에서

2. 선택 **[!UICONTROL Adobe 애플리케이션]** 목록 [!UICONTROL 카테고리].

3. 선택 **[!UICONTROL 설정]** 또는 **[!UICONTROL 데이터 추가]** ( Adobe Analytics 타일 ).

   ![소스](./assets/sources-overview.png)

4. 선택 **[!UICONTROL 보고서 세트]**. 보고서 세트 목록에서 사용할 보고서 세트를 선택합니다.

   ![보고서 세트](./assets/report-suites.png)

   **[!UICONTROL 다음]**&#x200B;을 선택합니다.

5. 선택 **[!UICONTROL 기본 스키마]** 로서의 [!UICONTROL Target 스키마]. Adobe Experience Platform은 선택된 Adobe Analytics 보고서 세트의 모든 표준 필드를 매핑하기 위해 자동으로 스키마와 해당 데이터 세트를 만듭니다.

   ![기본 스키마](./assets/default-schema.png)

   **[!UICONTROL 다음]**&#x200B;을 선택합니다.

6. 데이터 흐름 이름을 지정하고 (선택 사항) 설명을 제공합니다.

   ![데이터 흐름 세부 정보](./assets/dataflow-detail.png)

   **[!UICONTROL 다음]**&#x200B;을 선택합니다.

7. 연결을 검토하고 를 선택합니다 **[!UICONTROL 완료]**.

   ![자세한 내용은](./assets/review.png)


연결이 만들어지면 데이터 흐름이 자동으로 생성되어 최대 13개월 동안의 내역 데이터를 수집하여 보고서 세트의 Adobe Analytics 데이터로 데이터 세트를 채웁니다.

초기 수집이 완료되면 Adobe Analytics 보고서 세트 데이터를 Customer Journey Analytics에서 사용할 수 있습니다.

자세한 내용은 [UI에서 Adobe Analytics 소스 연결 만들기](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ko) 를 참조하십시오.


## 연결 설정

Customer Journey Analytics에서 Adobe Experience Platform 데이터를 사용하려면 스키마, 데이터 세트 및 워크플로우를 설정하여 생성되는 데이터가 포함된 연결을 만듭니다.

연결을 통해 Adobe Experience Platform의 데이터 세트를 작업 영역에 통합할 수 있습니다. 이러한 데이터 세트에 대해 보고하려면 먼저 Adobe Experience Platform과 작업 공간의 데이터 세트 간에 연결을 설정해야 합니다.

연결을 만들려면 다음을 수행하십시오.

1. Customer Journey Analytics UI에서 **[!UICONTROL 연결]** 를 클릭합니다.

2. 선택 **[!UICONTROL 새 연결 만들기]**.

3. 에서 [!UICONTROL 제목 없는 연결] 화면:

   연결 이름을 로 지정하고 설명합니다. [!UICONTROL 연결 설정].

   에서 올바른 샌드박스를 선택합니다 [!UICONTROL 샌드박스] 목록 [!UICONTROL 데이터 설정] 및 에서 일별 이벤트 수를 선택합니다 [!UICONTROL 일일 평균 이벤트 수] 목록.

   ![연결 설정](./assets/cja-connections-1.png)

   선택 **[!UICONTROL 데이터 세트 추가]**.

   에서 [!UICONTROL 데이터 세트 선택] 단계 [!UICONTROL 데이터 세트 추가]:

   - Adobe Analytics 소스 커넥터에서 자동으로 만든 데이터 세트와 연결에 포함할 다른 데이터 세트를 선택합니다.

      ![데이터 세트 추가](./assets/cja-connections-2a.png)

   - **[!UICONTROL 다음]**&#x200B;을 선택합니다.
   에서 [!UICONTROL 데이터 세트 설정] 단계 [!UICONTROL 데이터 세트 추가]:

   - 각 데이터 세트에 대해:

      - 선택 [!UICONTROL 개인 ID] Adobe Experience Platform의 데이터 세트 스키마에 정의된 사용 가능한 ID에서 생성합니다.

      - 에서 올바른 데이터 소스를 선택합니다 [!UICONTROL 데이터 소스 유형] 목록. 지정한 경우 **[!UICONTROL 기타]** 그런 다음 데이터 소스에 대한 설명을 추가합니다.

      - 설정 **[!UICONTROL 모든 새 데이터 가져오기]** 및 **[!UICONTROL 데이터 집합 기존 데이터 채우기]** 사용자의 기본 설정에 따라 다릅니다.

      ![데이터 세트 구성](./assets/cja-connections-3.png)

   - 선택 **[!UICONTROL 데이터 세트 추가]**.
   **[!UICONTROL 저장]**&#x200B;을 선택합니다.

자세한 내용은 [연결 개요](../connections/overview.md) 를 참조하십시오.

## 데이터 보기 설정

데이터 보기는 Customer Journey Analytics와 관련된 컨테이너입니다. 이를 통해 연결에서 데이터를 해석하는 방법을 결정할 수 있습니다. Analysis Workspace에서 사용 가능한 모든 차원과 지표를 지정하고, 해당 차원과 지표가 데이터를 얻을 수 있는 열을 지정합니다. 데이터 보기는 Analysis Workspace의 데이터에 대한 보고 준비에 따라 정의됩니다.

데이터 보기를 만들려면 다음을 수행하십시오.

1. Customer Journey Analytics UI에서 **[!UICONTROL 데이터 보기]** 를 클릭합니다.

2. 선택 **[!UICONTROL 새 데이터 보기 만들기]**.

3. 에서 [!UICONTROL 구성] 단계:

   에서 연결을 선택합니다 [!UICONTROL 연결] 목록.

   연결의 이름과 (선택 사항)를 설명합니다.

   ![데이터 보기 구성](./assets/cja-dataview-1.png)

   선택 **[!UICONTROL 저장 후 계속]**.

4. 에서 [!UICONTROL 구성 요소] 단계:

   포함할 스키마 필드 및/또는 표준 구성 요소를 추가합니다 [!UICONTROL 지표] 또는 [!UICONTROL Dimension] 구성 요소 상자

   ![데이터 보기 구성 요소](./assets/cja-dataview-2.png)

   선택 **[!UICONTROL 저장 후 계속]**.

5. 에서 [!UICONTROL 설정] 단계:

   ![데이터 보기 설정](./assets/cja-dataview-3.png)

   설정을 그대로 두고 를 선택합니다 **[!UICONTROL 저장 및 완료]**.

자세한 내용은 [데이터 보기 개요](../data-views/data-views.md) 데이터 보기를 만들고 편집하는 방법, 데이터 보기에서 사용할 수 있는 구성 요소 및 필터 및 세션 설정을 사용하는 방법에 대한 자세한 내용을 참조하십시오.


## 프로젝트 설정

Analysis Workspace은 데이터를 기반으로 분석을 신속하게 구축하고 통찰력을 공유할 수 있는 유연한 브라우저 도구입니다. Workspace 프로젝트를 사용하여 데이터 구성 요소, 테이블 및 시각화를 결합하여 분석을 만들고 조직의 모든 사람과 공유할 수 있습니다.

프로젝트를 만들려면 다음을 수행하십시오.

1. Customer Journey Analytics UI에서 **[!UICONTROL 프로젝트]** 를 클릭합니다.

2. 선택 **[!UICONTROL 프로젝트]** 을 클릭합니다.

3. 선택 **[!UICONTROL 프로젝트 만들기]**.

   ![작업 공간 프로젝트](./assets/cja-projects-1.png)

   선택 **[!UICONTROL 빈 프로젝트]**.

   ![작업 공간 - 빈 프로젝트](./assets/cja-projects-2.png)

4. 목록에서 데이터 보기를 선택합니다.

   ![작업 공간 데이터 보기 선택](./assets/cja-projects-3.png).

5. 차원에서 차원 및 지표 드래그 앤 드롭을 시작합니다 [!UICONTROL 자유 형식 테이블] 에서 [!UICONTROL 패널] 첫 번째 보고서를 만들려면 예를 들어 `Program Points Balance` 및 `Page View` 지표 및 `email` 충성도 포인트를 수집하는 충성도 프로그램의 일부이며 웹 사이트를 방문한 프로필에 대한 빠른 개요를 알 수 있는 차원입니다.

   ![작업 공간 - 첫 번째 보고서](./assets/cja-projects-5.png)

자세한 내용은 [Analysis Workspace 개요](../analysis-workspace/home.md) 구성 요소, 시각화 및 패널을 사용하여 프로젝트를 만들고 분석을 빌드하는 방법에 대한 자세한 내용을 참조하십시오.


>[!SUCCESS]
>
>모든 단계를 완료했습니다. Adobe Analytics 데이터 소스 커넥터를 설정하고 보고서 세트에 대한 해당 커넥터를 구성하면 Adobe Analytics 데이터가 자동으로 Adobe Experience Platform에 업로드됩니다. 수집된 Adobe Analytics 데이터 및 기타 데이터를 사용하기 위해 Customer Journey Analytics에서 연결을 정의했습니다. 데이터 보기 정의를 사용하여 사용할 차원 및 지표를 지정하고 최종적으로 데이터를 시각화하고 분석하는 첫 번째 프로젝트를 만들 수 있습니다.







