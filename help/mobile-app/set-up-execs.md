---
description: Adobe Analytics 대시보드 모바일 앱을 사용하도록 사용자를 설정하는 방법
title: 경영진이 대시보드를 사용할 수 있도록 설정
feature: Analytics Dashboards
role: User, Admin
exl-id: 647f192a-e317-4011-92bc-a8bb8494a3c7
solution: Customer Journey Analytics
source-git-commit: d8286e34edba128113ba99602ba24eea67c5dea8
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 69%

---

# 경영진 사용자가 대시보드를 사용할 수 있도록 설정

경우에 따라 경영진 사용자는 앱에 액세스하고 앱을 사용하기 위해 추가 지원이 필요할 수 있습니다. 이 섹션에서는 큐레이터가 그러한 지원을 제공하는 데 도움이 되는 정보를 제공합니다.

## 앱 사용자에게 Adobe Analytics 액세스 권한 부여

1. [Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=ko)에서 새 사용자를 설정합니다.

1. 스코어카드를 공유할 수 있으려면 앱 사용자에게 Analysis Workspace, 스코어카드가 기반으로 하는 데이터 보기, 세그먼트, 지표 및 차원과 같은 스코어카드 구성 요소에 액세스할 수 있는 권한을 부여해야 합니다.

## 앱 사용자의 시스템 사전 요구 사항

경영진 사용자가 앱의 스코어카드에 액세스할 수 있도록 하려면 다음을 확인합니다.

* 해당 디바이스의 최소 모바일 OS 요구 사항은 iOS 버전 10 이상 또는 Android 버전 4.4 (KitKat) 이상입니다.
* Customer Journey Analytics에 대한 유효한 로그인이 있습니다.
* 모바일 스코어카드를 올바르게 생성했으며 이 스코어카드를 경영진 사용자와 공유했습니다.
* 스코어카드에 포함된 구성 요소에 액세스할 수 있습니다. 스코어카드를 공유할 때 **[!UICONTROL 임베드된 구성 요소 공유]** 옵션을 선택할 수 있습니다.

## 경영진이 앱을 다운로드하여 설치하도록 지원

>[!NOTE]
>
>모바일 앱의 이름은 앱스토어에서 Adobe Analytics 대시보드 로 지정되지만, Customer Journey Analytics 모바일 스코어카드와 동일하게 앱을 사용할 수 있습니다.

**iOS를 사용하는 경영진 사용자:**

다음 링크(**[!UICONTROL 도구]** > **[!UICONTROL Analytics 대시보드(모바일 앱)]** 아래의 Customer Journey Analytics에서도 사용 가능)를 클릭하고 프롬프트에 따라 앱을 다운로드하여 설치하고 엽니다.

`[iOS link](https://apple.co/2zXq0aN)`

**Android를 사용하는 경영진 사용자:**

다음 링크(**[!UICONTROL 도구]** > **[!UICONTROL Analytics 대시보드(모바일 앱)]** 아래의 Customer Journey Analytics에서도 사용 가능)를 클릭하고 프롬프트에 따라 앱을 다운로드하여 설치하고 엽니다.

`[Android link](https://bit.ly/2LM38Oo)`

경영진 사용자는 다운로드 및 설치 후 기존 Customer Journey Analytics 자격 증명을 사용하여 앱에 로그인할 수 있습니다. Adobe 및 Enterprise/Federated ID가 모두 지원됩니다.

![Adobe Analytics 대시보드 시작 화면](assets/welcome.png)

## 경영진이 스코어카드에 액세스할 수 있도록 지원

1. 경영진 사용자가 앱에 로그인하도록 합니다.

   **[!UICONTROL 회사 선택]** 화면이 표시됩니다. 이 화면에 경영진 사용자가 속한 로그인 회사가 나열됩니다.

1. 공유한 스코어카드에 적용되는 로그인 회사 또는 Experience Cloud 조직의 이름을 경영진이 탭하도록 합니다.

   스코어카드 목록에는 해당 로그인 회사 아래에 경영진과 공유된 모든 스코어카드가 표시됩니다.

1. 해당되는 경우 경영진이 **[!UICONTROL 가장 최근에 수정됨]** 항목별로 이 목록을 정렬하도록 합니다.

1. 경영진이 스코어카드의 이름을 탭하여 보도록 합니다.

   ![회사 선택](assets/accesscard.png)


### 스코어카드 UI 설명

공유하는 스코어카드에 타일이 어떻게 표시되는지 경영진 사용자에게 설명합니다.

![선택한 날짜 범위, 세그먼트, 지표 및 차원을 포함한 타일 설명](assets/newexplain.png)

![스코어카드의 예](assets/intro_scorecard.png)

타일에 대한 추가 정보:

* 스파크라인의 세부기간은 날짜 범위의 길이에 따라 달라집니다.
* 하루는 시간별 트렌드를 표시함
   * 이틀 이상 및 1년 미만은 일별 트렌드를 표시함
   * 1년 이상은 주별 트렌드를 표시함
   * 비율 값 변경 수식은 지표 합계(현재 날짜 범위) – 지표 합계(비교 날짜 범위) / 지표 합계(비교 날짜 범위)입니다.
   * 화면을 아래로 당기면 스코어카드를 새로 고칠 수 있습니다.


1. 타일에 대한 세부 분류가 어떻게 작동하는지 표시하려면 타일을 탭합니다.

   ![분류 보기](assets/sparkline.png)

   * 스파크라인의 아무 지점이나 눌러 해당 포인트와 연관된 데이터를 라인에서 볼 수 있습니다.

   * 타일에 추가된 차원의 데이터를 표시하는 테이블이 포함됩니다. 아래쪽 화살표를 눌러 차원을 선택합니다. 타일에 추가된 차원이 없으면 테이블에 차트 데이터가 표시됩니다.

1. 스코어카드의 날짜 범위를 변경하려면 날짜 헤더를 누르고 보려는 기본 및 비교 날짜 범위 조합을 선택합니다.

   ![날짜 변경](assets/changedate.png)

## 앱 환경 설정 변경

환경 설정을 변경하려면 위에 표시된 **[!UICONTROL 환경 설정]** 옵션을 누릅니다. 환경 설정에서 생체 인식 로그인을 켜거나 아래에 표시된 대로 다크 모드로 앱을 설정할 수 있습니다.

![다크 모드](assets/darkmode.png)

## 문제 해결

경영진 사용자가 로그인했을 때 아무 것도 공유되지 않았다는 메시지가 표시되는 경우:

![아무 것도 공유되지 않음](assets/nothing.png)

* 경영진 사용자가 잘못된 Customer Journey Analytics 샌드박스를 선택했을 수 있습니다.
* 스코어카드가 경영진 사용자와 공유되지 않았을 수 있음.

경영진 사용자가 올바른 Customer Journey Analytics 샌드박스에 로그인할 수 있으며 스코어카드가 공유되었는지 확인합니다.
