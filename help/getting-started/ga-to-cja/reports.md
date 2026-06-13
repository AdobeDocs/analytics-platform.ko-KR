---
title: Customer Journey Analytics의 GA4 보고서
description: 모든 GA4 보고서 섹션에 해당하는 Customer Journey Analytics을 찾습니다.
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: c2d8f4a1-7b3e-4c9f-a5d2-8e1b6c3f9072
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 2125f1a16ffed79f77757120c5679dd4defa1638
workflow-type: tm+mt
source-wordcount: 3200
ht-degree: 0%

---


# Customer Journey Analytics의 GA4 보고서

보고 있는 GA4 보고서를 알고 있고 Analysis Workspace에서 거의 동일한 보고서를 다시 만들려는 경우 이 페이지를 조회 참조로 사용하십시오. 보고서는 GA4의 탐색 섹션별로 구성됩니다. GA 데이터를 Customer Journey Analytics으로 마이그레이션한 후 사용할 수 있게 되는 고급 크로스 채널 보고 시나리오에 대해서는 [Google Analytics 데이터에 대한 보고](/help/use-cases/third-party/ga/report.md)를 참조하십시오.

## 실시간

+++실시간

GA4의 실시간 보고서는 지난 30분 동안의 활동(활성 사용자, 실행되는 이벤트, 사용자, 트래픽을 유도하는 항목 및 진행 중인 페이지)을 보여 줍니다.

Customer Journey Analytics에는 별도의 실시간 보고서 영역이 없습니다. 대신 Analysis Workspace에서 패널을 빌드하고 **[!UICONTROL 실시간 새로 고침]** 토글(**Ultimate** 패키지의 일부)을 활성화하여 시각화가 매분마다 업데이트됩니다.

1. 모니터링할 차원 및 지표를 사용하여 [자유 형식](/help/analysis-workspace/c-panels/freeform-panel.md) 패널([Blank](/help/analysis-workspace/c-panels/blank-panel.md), [속성](/help/analysis-workspace/c-panels/attribution.md) 및 [다음 또는 이전 항목](/help/analysis-workspace/c-panels/next-previous.md) 패널에서도 작동)을 빌드합니다. GA4의 실시간 카드를 미러링하려면 **[!UICONTROL 페이지]**, **[!UICONTROL 이벤트 유형]**, **[!UICONTROL 참조 도메인]** 또는 **[!UICONTROL 국가]**&#x200B;를 차원으로 사용하고, **[!UICONTROL 세션]**&#x200B;을 지표로 사용합니다.
2. **[!UICONTROL 실시간 새로 고침]** 토글을 사용하도록 설정하고 **[!UICONTROL 최근 15분]**&#x200B;부터 **[!UICONTROL 최근 24시간]**&#x200B;까지의 기간을 선택하세요. 데이터는 롤링 24시간 창으로 제한되며, 패널은 최대 30분 동안 매분마다 새로 고쳐집니다.

실시간 보고는 이벤트 및 세션 수준 데이터를 선호하며 결합을 사용할 수 없으므로 **[!UICONTROL 사람]**&#x200B;보다 **[!UICONTROL 세션]**&#x200B;을 선호합니다. 전체 프로시저는 [실시간 보고 사용](/help/components/real-time/use-real-time.md)을, 권한 및 지연 세부 사항은 [실시간 보고 개요](/help/components/real-time/real-time.md)를 참조하십시오.

+++

## 획득

+++사용자 확보(첫 번째 터치)

GA4의 사용자 확보 보고서는 첫 번째 터치 속성을 사용하여 각 사용자를 처음으로 사이트로 가져온 채널, 소스 및 미디어에 대해 속성을 지정합니다.

Analysis Workspace에서 **[!UICONTROL 마케팅 채널]** 차원에 **[!UICONTROL 첫 번째 터치]** 속성 모델을 적용합니다. 사용하기 전에 마케팅 채널을 구성해야 합니다. [마케팅 채널 파생 필드 만들기](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)를 참조하십시오.

1. **[!UICONTROL 마케팅 채널]** 차원을 [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)(으)로 끌어서 놓습니다.
2. 지표 열 헤더를 마우스 오른쪽 단추로 클릭하고 **[!UICONTROL 기본값이 아닌 속성 모델 사용]**&#x200B;을 선택합니다.
3. 분석에 적합한 전환 확인 기간이 있는 **[!UICONTROL 첫 번째 터치]**&#x200B;를 선택하십시오.

또는 첫 번째 접점 및 마지막 접점 채널 성능을 나란히 비교하려면 [[!UICONTROL 속성] 패널](/help/analysis-workspace/c-panels/attribution.md)을 사용하십시오.

+++

+++트래픽 획득(세션 기반)

GA4의 트래픽 획득 보고서는 세션 기반 속성을 사용하여 각 세션을 시작한 채널, 소스 및 미디어에 대해 지정합니다. 기본 채널 그룹, 소스/미디어, 레퍼러 또는 캠페인으로 분류할 수 있습니다.

Analysis Workspace에서 기본 **[!UICONTROL 마지막 터치]** 속성 모델을 사용하는 **[!UICONTROL 마케팅 채널]** 차원은 세션 기반 채널 보고를 제공합니다.

1. **[!UICONTROL 마케팅 채널]** 차원을 [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)(으)로 끌어서 놓습니다.
2. 기본 **[!UICONTROL 이벤트]** 지표와 함께 원하는 지표를 드래그합니다.

GA4의 분류는 다음 Customer Journey Analytics 차원에 매핑됩니다.

* **채널**: **[!UICONTROL 마케팅 채널]**. Customer Journey Analytics에는 기본 제공 채널 그룹화가 없습니다. **[!UICONTROL 마케팅 채널]** 함수 템플릿을 사용하여 [파생 필드](/help/data-views/derived-fields/derived-fields.md)로 정의하거나, Analytics 소스 커넥터를 사용할 때 Adobe Analytics에서 규칙을 전달하십시오([마케팅 채널 차원 사용](/help/use-cases/aa-data/marketing-channels.md) 참조).
* **Source / 중간 및 참조**: **[!UICONTROL 참조 도메인]** 및 **[!UICONTROL 레퍼러 유형]**.
* **Campaign**: GA4의 `utm_*` 매개 변수는 자동으로 수집되지 않습니다. 각 매개 변수는 구현 중에 XDM 필드에 매핑되어야 차원으로 표시됩니다. 캠페인 값이 추적 코드로 도착하는 경우 **[!UICONTROL 추적 코드]** 차원을 사용하십시오.

+++

+++속성 및 전환 경로

GA4의 속성 보고서(Advertising 아래)는 다양한 채널이 전환에 기여하는 방식을 보여 주고 모델 비교 및 전환 경로 분석을 허용합니다.

Analysis Workspace에서 [[!UICONTROL 속성] 패널 사용](/help/analysis-workspace/c-panels/attribution.md):

1. 패널 아이콘을 선택하고 **[!UICONTROL 속성]** 패널을 캔버스로 드래그합니다.
2. **[!UICONTROL 마케팅 채널]** 차원을 **[!UICONTROL Dimension 추가]** 상자로 드래그합니다.
3. 전환 지표(예: 구매 이벤트)를 **[!UICONTROL 지표 추가]** 상자로 드래그합니다.
4. **[!UICONTROL 빌드]**&#x200B;를 선택합니다.

[!UICONTROL 속성 패널]은(는) 모델 비교 표와 방문자가 전환하기 전에 사용한 상위 경로를 보여 주는 [!UICONTROL 채널 흐름] 시각화를 생성합니다. **[!UICONTROL 모델 추가]**&#x200B;를 선택하여 여러 속성 모델을 동시에 비교합니다.

+++

## 참여

+++페이지 및 화면

GA4의 페이지 및 화면 보고서에는 개별 페이지 및 앱 화면에 대한 성능 지표가 표시됩니다.

Analysis Workspace에서 **[!UICONTROL 페이지]** 차원을 [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)(으)로 드래그하고 원하는 지표를 추가합니다. 일반적인 지표에는 **[!UICONTROL 세션]**, **[!UICONTROL 사람]**, **[!UICONTROL 바운스 비율]** 및 **[!UICONTROL 세션당 체류 시간]**&#x200B;이 포함됩니다.

URL 경로 구조(예: `/blog/` 또는 `/products/`)로 페이지를 그룹화하려면 구현에서 정의하는 경우 **[!UICONTROL 사이트 섹션]** 차원을 사용하거나 **[!UICONTROL URL 구문 분석]** 함수로 페이지 URL을 구문 분석하는 [파생 필드](/help/data-views/derived-fields/derived-fields.md)를 만드십시오. 명시적 페이지-섹션 매핑을 유지하는 경우 [조회 데이터 세트](/help/connections/standard-lookups.md)에서 그룹화를 대신 제공할 수 있습니다.

+++

+++랜딩 페이지

GA4의 랜딩 페이지 보고서는 사용자가 세션을 시작할 때 도착하는 페이지를 보여줍니다.

Analysis Workspace에서 **[!UICONTROL 시작 페이지]** 차원을 [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)(으)로 끌어옵니다. **[!UICONTROL 세션]**&#x200B;은(는) 이 차원에 가장 적절한 지표입니다.

+++

+++이벤트

GA4의 이벤트 보고서는 이벤트 수준 지표와 함께 각 이벤트가 실행된 횟수를 보여줍니다.

GA4에서 이벤트에는 이름과 선택적 매개 변수가 있습니다(예: 매개 변수가 `video_title`인 이벤트 `video_play`). Customer Journey Analytics에서 이벤트 이름에 대한 표준 차원은 **[!UICONTROL 이벤트 유형]**(`xdm.eventType`에서 소싱)입니다. 이벤트 매개 변수는 구현에 따라 이름이 다른 XDM 필드에 매핑됩니다.

**[!UICONTROL 이벤트 유형]** 차원을 [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)(으)로 드래그하여 **[!UICONTROL 이벤트]** 지표와 함께 모든 이벤트 유형을 나열합니다.

+++

+++주요 이벤트(전환)

GA4의 주요 이벤트 보고서(이전의 전환)는 GA4 속성 구성에서 비즈니스에 중요한 것으로 플래그가 지정된 이벤트, 즉 수와 함께 이름별로 각 주요 이벤트를 나열합니다.

Customer Journey Analytics에는 &quot;키 이벤트&quot; 플래그가 없습니다. 모든 상호 작용은 이벤트이므로 열 전환 목록이 미리 설정되어 있지 않습니다.

GA4의 전환 목록을 이름별로 다시 만들려면 **세그먼트를 행으로 사용**&#x200B;하십시오. [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)에서는 지표를 행 위치에 배치할 수 없지만 세그먼트를 배치할 수 있습니다.

1. 각 변환에 대해 해당 이벤트를 격리하는 세그먼트(예: `xdm.eventType`이(가) `commerce.purchases`인 이벤트 범위 세그먼트)를 만듭니다. 각 세그먼트를 나타내는 전환 뒤에 이름을 지정합니다(예: **구매**).
2. 각 전환 세그먼트를 행당 하나씩 [!UICONTROL 자유 형식 테이블]의 행 영역으로 끌어서 놓습니다.
3. **[!UICONTROL 이벤트]** 지표를 열로 추가합니다. 각 행은 GA4의 키 이벤트 목록을 미러링하여 전환의 수를 보여줍니다. **[!UICONTROL 사람]**&#x200B;을(를) 대신 사용하여 고유한 변환기를 계산하십시오.

전환율을 추가하려면 **[!UICONTROL 세션]** 또는 **[!UICONTROL 사람]**(으)로 나눈 전환 지표로 정의된 계산된 지표(지표 목록 근처의 **+** 아이콘 선택)를 만드십시오.

여기에서 격리하는 각 전환은 데이터 보기에서 재사용 가능한 지표로 정의할 수도 있습니다. 설정 방법은 [일반 지표](#common-metrics)의 **주요 이벤트 → 사용자 지정 이벤트 지표** 항목을 참조하십시오.

+++

## 수익 창출

+++전자 상거래 구매

GA4의 전자 상거래 구매 보고서는 품목, 수익 및 수량을 포함한 제품 수준의 구매 데이터를 보여 줍니다.

Customer Journey Analytics에서 전자 상거래 보고는 구매 지표와 함께 **[!UICONTROL Product]** 차원을 사용합니다. 이 보고서를 사용하려면 구현에서 XDM 상거래 데이터(예: `xdm.commerce.purchases`, `xdm.commerce.order` 및 `xdm.productListItems`)를 전송해야 합니다.

1. **[!UICONTROL Product]** 차원을 [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)(으)로 끌어옵니다.
2. **[!UICONTROL 주문]**, **[!UICONTROL 매출]**, **[!UICONTROL 단위]**&#x200B;와 같은 전자 상거래 지표를 기본 **[!UICONTROL 이벤트]** 지표와 함께 드래그합니다.

+++

+++구매 여정(funnel)

GA4의 구매 여정 보고서는 사용자가 장바구니에서 장바구니에 추가, 체크아웃에서 구매로 시작 등 쇼핑 funnel을 통해 이동하는 방법과 드롭오프의 위치를 보여줍니다.

Analysis Workspace에서 [**[!UICONTROL 폴아웃]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) 시각화를 사용하십시오.

1. 시각화 아이콘을 선택하고 **[!UICONTROL 폴아웃]** 시각화를 캔버스로 드래그합니다.
2. **[!UICONTROL 페이지]** 차원을 찾아 확장하여 개별 페이지 값을 표시합니다.
3. 첫 번째 funnel 단계(예: 제품 페이지)를 첫 번째 **[!UICONTROL 터치포인트 추가]** 슬롯으로 드래그합니다.
4. 각 단계에 대한 터치포인트를 계속 추가합니다.

폴아웃 시각화는 차원, 지표 또는 세그먼트를 페이지뿐만 아니라 터치포인트로 허용하므로 GA4의 이벤트 기반 유입 경로와 일치하고 이벤트, 페이지 및 세그먼트를 혼합하는 시퀀스로 확장합니다.

+++

+++프로모션

GA4의 프로모션 보고서는 내부 프로모션(배너, 주요 배치)이 어떻게 제품 상호 작용을 촉진하는지를 보여줍니다.

Customer Journey Analytics에서 프로모션 데이터를 사용하려면 XDM 스키마 필드에서 프로모션 노출 횟수 및 클릭 수를 캡처해야 합니다. 수집되면 노출 및 클릭 지표가 있는 프로모션 이름 차원을 포함하는 [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)을 만듭니다. Customer Journey Analytics 관리자와 협력하여 데이터 보기에서 사용할 수 있는 프로모션 데이터를 확인합니다.

+++

+++게시자 광고

GA4의 게시자 광고 보고서 는 게시자가 수익을 창출하는 속성에 대한 Google 광고 관리자 또는 AdMob의 광고 수익을 보여줍니다.

Customer Journey Analytics에는 기본 게시자 광고 수익 통합이 없습니다. 이 데이터를 보고하려면 소스 커넥터 또는 직접 데이터 수집을 사용하여 광고 수익 창출 플랫폼(예: Google Ad Manager 또는 AdMob)의 수익 수치를 Adobe Experience Platform에 데이터 세트로 수집하십시오. 데이터가 수집되면 Customer Journey Analytics에서 보고할 수 있습니다.

+++

## 유지

+++유지 개요

GA4의 유지 개요 보고서에는 신규 사용자와 재방문 사용자의 여러 유지 보기 및 시간이 지남에 따라 재방문하는 사용자의 수를 보여주는 집단 차트가 포함됩니다.

**새 사용자와 재방문 사용자 비교**: **[!UICONTROL 첫 번째 세션]** 및 **[!UICONTROL 재방문 세션]** 세그먼트를 [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)의 행으로 사용:

1. 구성 요소 패널에서 **[!UICONTROL 첫 번째 세션]** 세그먼트를 테이블의 행 영역으로 드래그한 다음 그 아래에 **[!UICONTROL 재방문 세션]** 세그먼트를 드래그합니다.
2. 기본 **[!UICONTROL 이벤트]** 지표와 함께 원하는 지표를 추가합니다.
3. 시간에 따른 트렌드를 추적하려면 테이블 위로 [**[!UICONTROL 선]**](/help/analysis-workspace/visualizations/line.md) 시각화를 드래그한 다음 각 행을 ctrl+클릭(Windows)하거나 cmd+클릭(Mac)하여 두 세그먼트를 모두 강조 표시합니다.

**시간에 따른 유지**: [**[!UICONTROL 집단 테이블]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) 시각화 사용:

1. 시각화 아이콘을 선택하고 **[!UICONTROL 집단 테이블]**&#x200B;을 캔버스로 드래그합니다.
2. **[!UICONTROL 사람]** 지표를 포함 및 반환 기준 필드로 드래그한 다음 **[!UICONTROL 빌드]**&#x200B;를 선택합니다.

[!UICONTROL 집단 테이블]은(는) 초기 기간별로 사람을 그룹화하고 후속 기간에 대한 반환 동작을 추적합니다. 포함, 반환 및 세부 기간 기준은 모두 구성할 수 있습니다.

+++

## 사용자

+++인구 통계 세부 정보

GA4의 인구 통계학적 세부 사항 보고서는 위치(국가, 지역, 도시) 및 언어와 함께 사용자 특성(연령, 성별 및 관심 분야(Google 신호가 지원하며 개인화가 활성화된 Google 계정에 로그인해야 함)을 다룹니다.

**위치**&#x200B;는 Customer Journey Analytics 차원에 직접 매핑됩니다. [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)에서 **[!UICONTROL 국가]**, **[!UICONTROL 지역]** 또는 **[!UICONTROL 도시]**&#x200B;를 사용하거나 지역 개요를 위한 [[!UICONTROL 맵]](/help/analysis-workspace/visualizations/map.md) 시각화를 사용하십시오. **[!UICONTROL 사람]** 지표를 **[!UICONTROL 지표 추가]** 슬롯으로 드래그하고 **[!UICONTROL 빌드]**&#x200B;를 선택하십시오.

**연령, 성별 및 관심 분야**&#x200B;에는 자사 데이터가 필요합니다. 조직에서 CRM, 등록 양식 또는 동의 기반 설문 조사를 통해 인구 통계 데이터를 수집하는 경우 [프로필 데이터 세트](/help/connections/create-connection.md#profile-dataset)(으)로 수집한 다음 이벤트 데이터에 가입하십시오. 이 접근 방식은 합의된 자사 속성을 사용하므로 GA4의 추론된 Google 신호 모델보다 안정적인 데이터를 생성합니다.

+++

+++기술 세부 정보

GA4의 기술 보고서에는 브라우저, 운영 체제, 화면 해상도 및 장치 카테고리가 표시됩니다.

Analysis Workspace에서 다음 차원은 표준 XDM 필드에서 각각 제공되는 GA4의 기술 차원에 매핑됩니다.

| GA4 기술 차원 | Analysis Workspace 차원 | XDM 필드 |
|---|---|---|
| 브라우저 | **[!UICONTROL 브라우저]** | `xdm.environment.browserDetails.name` |
| 운영 체제 | **[!UICONTROL 운영 체제]** | `xdm.environment.operatingSystem` |
| 화면 해상도 | **[!UICONTROL 모니터 해상도]** | `xdm.device.screenWidth`, `xdm.device.screenHeight` |
| 장치 카테고리(모바일, 데스크탑, 태블릿) | **[!UICONTROL 모바일 장치 유형]** | `xdm.device.type` |
| 디바이스 모델 | **[!UICONTROL 모바일 장치]** | `xdm.device.model` |

구성 요소 패널에서 [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)(으)로 이러한 차원을 드래그합니다.

>[!NOTE]
>
>최신 브라우저는 사용자 에이전트 문자열의 세부 정보를 줄였기 때문에 완전하고 정확한 값은 웹 SDK 구성에서 [사용자 에이전트 클라이언트 힌트](https://experienceleague.adobe.com/ko/docs/experience-platform/collection/use-cases/client-hints)를 수집하는 것에 따라 달라집니다.

+++

## 탐색

+++자유 형식 탐색

GA4의 자유 형식 탐색은 구성 가능한 행, 열 및 선택적 차트 오버레이가 있는 빈 캔버스 테이블입니다.

Analysis Workspace의 [**[!UICONTROL 자유 형식 테이블]**](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)은(는) 직접 이에 해당하는 것이며 대부분의 Workspace 프로젝트의 기반입니다. 차원을 행으로, 지표를 열로, 세그먼트를 테이블 위의 세그먼트 드롭 영역으로 드래그합니다.

GA4 탐색과 Analysis Workspace 간의 용어 매핑은 [Workspace에서 시작하기](home.md#getting-started-in-analysis-workspace)를 참조하십시오.

+++

+++Funnel 탐사

GA4의 Funnel 탐사는 일련의 단계를 정의하고 각 단계에서 완료 및 드롭오프를 측정합니다.

Analysis Workspace에서 [**[!UICONTROL 폴아웃]**](/help/analysis-workspace/visualizations/fallout/fallout-flow.md) 시각화를 사용하십시오.

1. 시각화 아이콘을 선택하고 **[!UICONTROL 폴아웃]** 시각화를 캔버스로 드래그합니다.
2. 첫 번째 단계를 나타내는 차원, 지표 또는 세그먼트를 첫 번째 **[!UICONTROL 터치포인트 추가]** 슬롯으로 드래그합니다.
3. 시퀀스의 각 후속 단계에 대한 터치포인트를 계속 추가합니다.

모든 차원, 지표 또는 세그먼트는 터치포인트 역할을 할 수 있으므로 [!UICONTROL 폴아웃]은(는) GA4의 이벤트 기반 유입 경로와 일치하며 이벤트, 페이지 및 세그먼트를 혼합하는 크로스 채널 시퀀스로 확장됩니다.

+++

+++경로 탐색

GA4의 경로 탐색(이 사용자 흐름이라고 하는 범용 분석)은 사용자가 탐색하는 페이지 또는 이벤트의 시퀀스를 시각화합니다.

Analysis Workspace에서 [**[!UICONTROL 흐름]**](/help/analysis-workspace/visualizations/c-flow/flow.md) 시각화를 사용하십시오.

1. 시각화 아이콘을 선택하고 **[!UICONTROL 흐름]** 시각화를 캔버스로 드래그합니다.
2. 경로를 지정할 차원(예: **[!UICONTROL Page]** 또는 **[!UICONTROL 이벤트 유형]** 값)의 값을 흐름의 가운데로 끕니다.
3. 시각화는 해당 시점 전후에 사용자가 수행한 작업을 보여 줍니다.

[!UICONTROL 흐름] 시각화는 대화형입니다. 어느 방향으로든 경로를 더 확장하려면 아무 노드나 선택하십시오. 페이지, 이벤트, 마케팅 채널 또는 사용자 지정 링크에서 경로를 지정할 수 있도록 모든 차원을 사용할 수 있습니다.

+++

+++세그먼트 겹치기

GA4의 세그먼트 겹침 탐색은 여러 사용자 세그먼트가 어떻게 교차하는지를 보여주며 벤 다이어그램으로 시각화됩니다.

Analysis Workspace에서 [**[!UICONTROL 벤]**](/help/analysis-workspace/visualizations/venn.md) 시각화를 사용하십시오.

1. 시각화 아이콘을 선택하고 **[!UICONTROL 벤]** 시각화를 캔버스로 드래그합니다.
2. 최대 3개의 세그먼트를 구성 요소 패널에서 시각화로 드래그합니다.

벤 다이어그램은 교차 크기를 보여 주고 그 아래의 [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)은 기본 데이터를 보여 줍니다.

+++

+++집단 탐색

GA4의 집단 탐색은 공유 특성(일반적으로 획득 날짜)별로 사용자를 그룹화하고 시간 경과에 따른 사용자의 행동을 추적합니다.

Analysis Workspace에서 [**[!UICONTROL 집단 테이블]**](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) 시각화를 사용하십시오.

1. 시각화 아이콘을 선택하고 **[!UICONTROL 집단 테이블]**&#x200B;을 캔버스로 드래그합니다.
2. **[!UICONTROL 사람]** 지표를 포함 및 반환 기준 필드로 드래그합니다.
3. **[!UICONTROL 빌드]**&#x200B;를 선택합니다.

[!UICONTROL 집단 테이블]은(는) 초기 기간별로 사람들을 그룹화하고 후속 기간에 대한 반환 동작을 추적합니다. 기본적으로 인수 날짜에 집단을 구성하지만 포함, 반환 및 세부기간 기준은 모두 구성할 수 있습니다.

+++

+++사용자 탐색기

GA4의 사용자 탐색기에는 개별 사용자, 해당 세션 내역 및 이벤트 타임라인이 표시됩니다.

Customer Journey Analytics은 다음 두 가지 방법으로 사용자 수준 분석을 지원합니다.

* **결합을 사용할 수 있음**: 특정 개인 ID 값에 대한 범위를 설정하는 세그먼트를 만들어 모든 Workspace 프로젝트에 적용합니다. **[!UICONTROL 개인]** 컨테이너는 세션과 채널 간에 해당 개인의 결합된 활동을 격리합니다.
* **원시 이벤트 데이터**: Adobe Experience Platform UI에서 **데이터 세트 미리 보기**&#x200B;를 사용하여 원시 XDM 이벤트 레코드를 검사합니다. 이 보기는 구현 유효성 검사와 개별 이벤트 디버깅에 유용합니다.

+++

+++사용자 라이프타임

GA4의 사용자 라이프타임 탐색은 고정된 날짜 범위 내에서가 아니라 비즈니스와 전체 관계에 걸쳐 각 사용자의 누적 가치와 참여를 측정합니다. 구매 확률, 이탈 확률 및 예상 매출에 대한 Google의 머신 러닝 예측과 과거 라이프타임 지표를 결합합니다.

이는 다음 두 가지 부분으로 Customer Journey Analytics에 매핑됩니다.

**이전 수명 값**&#x200B;은(는) 기본적으로 달성할 수 있습니다. Customer Journey Analytics은 전체 데이터 보존 기간에 대해 보고하므로 긴 날짜 범위를 설정하고 해당 전환 확인 기간 동안 각 개인의 누적된 매출과 참여를 집계할 수 있습니다. 결합 또는 영구 사용자 ID를 사용하여 **[!UICONTROL 개인]** 컨테이너는 해당 활동을 한 개인에 연결하며 계산된 지표는 1인당 값을 표현합니다. 결과는 무제한 수명이 아니라 1에 가까운 길고 구성 가능한 전환 확인입니다.

**예측 라이프타임 값**&#x200B;이(가) 내장되어 있지 않습니다. Customer Journey Analytics에는 제품 내 구매 확률, 이탈 또는 예상 매출 모델이 없습니다. 예측 점수를 사용하려면 외부에서(예를 들어, CRM 또는 데이터 과학 워크플로우에서) 계산하여 프로필 데이터 세트로 Customer Journey Analytics에 가져온 다음 차원 또는 지표로 표시합니다. Adobe에서는 구현 컨설턴트와 함께 이 접근 방식을 디자인할 것을 권장합니다.

+++

## 일반 지표

+++활성 사용자 → 사람

GA4의 **활성 사용자**&#x200B;는 날짜 범위에 참여 세션이 하나 이상 있는 사용자를 계산합니다.

Customer Journey Analytics에서 가장 가까운 동등한 사용자는 날짜 범위의 고유 사용자 ID 수인 **[!UICONTROL 사람]**&#x200B;입니다. [!UICONTROL 사람]은(는) 참여 수준에 관계없이 식별된 모든 사람을 포함하므로 일반적으로 수동 트래픽이 많은 사이트의 경우 GA4의 활성 사용자보다 높습니다.

더 자세한 동작 비교를 위해 [참여 세션 세그먼트](compare-data.md#engaged-sessions)를 적용하여 참여 기준을 충족하는 사용자에게 [!UICONTROL 사람] 지표의 범위를 지정합니다.

+++

+++참여 세션 → 계산된 지표

GA4의 **참여 세션**&#x200B;은(는) 10초 이상 지속되거나, 2개 이상의 페이지 보기가 있거나, 하나 이상의 주요 이벤트를 포함한 세션을 계산합니다.

Customer Journey Analytics에는 내장된 참여 세션 지표가 없습니다. 참여 기준을 캡처하는 세그먼트로 정의한 다음 **[!UICONTROL 세션]** 지표와 함께 사용합니다. 권장 접근 방식과 여기에서 참여 비율을 도출하는 방법은 [참여 세션](compare-data.md#engaged-sessions)을 참조하세요.

+++

+++참여 비율 → 계산된 지표

GA4의 **참여 비율**&#x200B;은 참여한 세션의 백분율입니다. 참여한 세션을 총 세션으로 나눈 값입니다.

Customer Journey Analytics에서 참여 세션 정의에서 계산된 지표로 빌드합니다. 단계별 지침은 [참여 세션](compare-data.md#engagement-rate)을 참조하세요.

+++

+++평균 참여 시간 → 세션당 소비한 시간

GA4의 **평균 참여 시간**&#x200B;은(는) 참여 세션 중 브라우저 또는 앱이 전경에 있었던 평균 시간을 측정합니다.

Customer Journey Analytics에서 세션의 첫 번째 이벤트에서 마지막 이벤트까지의 경과 시간을 측정하는 **[!UICONTROL 세션 기간(초)]**&#x200B;을 사용합니다. 이 구성 요소에는 사용자가 적극적으로 참여하지 않았을 수 있는 기간이 포함되므로 값은 GA4의 측정과 다를 수 있습니다. 가장 가까운 내장 버전입니다.

+++

+++이벤트 수 → 이벤트

GA4의 **Event count**&#x200B;은 이벤트가 기록된 총 횟수입니다.

Customer Journey Analytics에서 이에 해당하는 지표는 **[!UICONTROL 이벤트]**(선택한 날짜 범위 및 적용된 세그먼트에 대한 데이터 집합에 있는 총 이벤트 레코드 수)입니다.

+++

+++세션 → 세션

GA4의 **세션**&#x200B;과(와) Customer Journey Analytics의 **[!UICONTROL 세션]**&#x200B;은(는) 모두 날짜 범위의 세션 수를 측정합니다. 카운트는 서로 다른 세션 정의 규칙으로 인해 다를 수 있습니다. 자세한 내용은 [GA4 및 Customer Journey Analytics 데이터가 다른 이유](compare-data.md#sessions)를 참조하십시오.

+++

+++새 사용자 → 첫 번째 세션 세그먼트가 사람들에게 적용됨

GA4의 **새 사용자**&#x200B;는 선택한 날짜 범위에서 첫 번째 세션을 가진 사용자를 계산합니다.

Analysis Workspace:

1. 구성 요소 패널에서 **[!UICONTROL 첫 번째 세션]** 세그먼트를 찾습니다.
2. [[!UICONTROL 자유 형식 테이블]](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) 위의 세그먼트 드롭 영역으로 드래그합니다.
3. **[!UICONTROL 사람]** 지표를 사용하여 고유한 새 사람을 계산합니다.

+++

+++바운스 비율 → 바운스 비율(경고 포함)

GA4의 **바운스 비율**&#x200B;은(는) 연결되지 않은 세션의 백분율입니다(10초 미만, 키 이벤트 없음, 2페이지 보기 미만). 이는 참여율의 역입니다.

Customer Journey Analytics의 **[!UICONTROL 바운스 비율]** 지표는 기본적으로 다른 정의를 사용하며 데이터 보기별로 구성할 수 있습니다. 이러한 차이는 다른 행동을 측정하는 물질적으로 다른 숫자를 생성합니다.

Customer Journey Analytics에서 GA4의 바운스 비율을 근사화하려면 참여 비율 지표를 빌드하고 `1 - Engagement Rate`(으)로 정의된 두 번째 계산된 지표로 반전합니다. 단계별 빌드는 [참여 세션](compare-data.md#engagement-rate)을(를) 참조하십시오.

정의 차이에 대한 자세한 설명은 [GA4 및 Customer Journey Analytics 데이터가 다른 이유](compare-data.md#bounce-rate)를 참조하십시오.

+++

+++사용자 지정 이벤트 지표→ 주요 이벤트

GA4의 **주요 이벤트**(이전 명칭: 전환)은 GA4 속성 구성에서 중요한 비즈니스 결과로 지정된 이벤트입니다.

Customer Journey Analytics에서 전환은 데이터 보기에 구성된 사용자 지정 이벤트 지표입니다. 모든 XDM 이벤트는 지표로 노출될 수 있으며, 지표는 XDM 필드 값에서 조건부로 증가하도록 설정할 수 있습니다(예: `xdm.eventType`이(가) `commerce.purchases`일 때 증가하는 **[!UICONTROL 구매]** 지표). Analysis Workspace의 구성 요소 패널에서 해당 레이블로 관련 지표를 찾습니다. 이름은 관리자가 구성한 방식을 반영합니다.

GA4의 키 이벤트 *보고서*(카운트와 함께 모든 전환 목록)를 재현하려면 이 페이지의 [참여](#engagement)에서 **키 이벤트(전환)** 항목을 참조하십시오.

+++

>[!MORELIKETHIS]
>
>* [Google Analytics 데이터 보고](/help/use-cases/third-party/ga/report.md)
