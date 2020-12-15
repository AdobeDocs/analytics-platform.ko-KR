---
title: 날짜 범위 만들기
description: 보고에 사용할 날짜 범위를 만듭니다.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 10%

---


# 날짜 범위 만들기

>[!NOTE]
>
>Customer Journey Analytics의 Analysis Workspace 설명서를 보고 계십니다. 이 기능은 [기존 Adobe Analytics의 Analysis Workspace](https://docs.adobe.com/content/help/ko-KR/analytics/analyze/analysis-workspace/home.html)와 약간 다릅니다. [추가 정보...](/help/getting-started/cja-aa.md)

다음 두 가지 방법 중 하나를 사용하여 사용자 지정 날짜 범위를 만들 수 있습니다.

* 왼쪽의 날짜 범위 구성 요소 목록 옆에 있는 &#39;`+`&#39; 단추를 클릭하여 작업 영역 프로젝트에 바로 있습니다.
* 날짜 범위 관리자 내

날짜 범위 관리자에서 날짜 범위를 만들려면:

1. AdobeID 자격 증명을 사용하여 [analytics.adobe.com](https://analytics.adobe.com)에 로그인합니다.
1. [!UICONTROL 구성 요소] > [!UICONTROL 날짜 범위]로 이동합니다.
1. 날짜 범위를 만드는 양식 창을 열려면 [!UICONTROL 추가] 단추를 클릭합니다.

## 날짜 범위 양식 창 만들기

모달 창에는 편집할 수 있는 4개의 필드가 있습니다.

* **날짜 범위**:이 구성 요소에 대해 원하는 날짜 범위입니다.
* **제목**:이 구성 요소에 사용할 이름입니다. 제목은 작업 공간 프로젝트에 사용됩니다.
* **설명**:이 구성 요소에 대해 원하는 설명입니다. 설명은 ![i](../assets/i.png) 아이콘을 클릭할 때 표시됩니다.
* **태그**:태그를 사용하여 날짜 범위를 구성합니다. 날짜 범위는 여러 태그에 속할 수 있습니다.

## 날짜 범위 선택

모달 창에서 날짜 범위를 클릭하면 다음과 같은 여러 가지 옵션이 있습니다.

* **달력**:시작 및 종료 날짜를 선택합니다.
* **롤링 날짜** 사용:시간이 지남에 따라 날짜 범위를 변경하려면 이 상자를 선택합니다. 날짜 범위를 정적으로 유지하려면 이 상자를 선택하지 마십시오.
* **사전 설정 선택**:기본적으로 Adobe에서 제공하는 범위를 기반으로 사용자 지정 날짜 범위를 원하는 경우 이 드롭다운을 사용합니다. 사전 설정을 선택하면 필요에 맞게 날짜 범위를 사용자 정의할 수 있습니다. Adobe에서 제공하는 사전 설정에 영향을 주지 않습니다.

## 롤링 날짜 범위

롤링 날짜 범위를 원하는 경우 롤링 시기를 사용자 정의할 수 있습니다. 시작 날짜와 종료 날짜가 서로 독립적으로 롤링되는 시기를 제어할 수 있습니다.

* **날짜가 시작되면**:날짜가 기간의 초에서 시작되는지, 기간이 끝날 때 시작하는지, 아니면 고정 날짜를 사용하는지를 선택합니다.
* **사용할** 기간:날짜 범위가 롤되는 빈도를 선택합니다. 매일, 매주, 매달, 매 분기 또는 매년 롤아웃할 수 있습니다.
* **오프셋**:날짜 범위의 오프셋을 선택합니다. 일, 주, 월, 분기 또는 연도를 추가하거나 제거할 수 있습니다.

## 롤링 날짜 예

일부 날짜 범위는 특정 보고서에서 유용할 수 있습니다.

연간 누계:

```text
Start: Start of current year
End: End of current day
```

지난 목요일 ~ 이번 주 목요일:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

회계 연도(예: 회계연도가 12월에 시작하는 경우)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
