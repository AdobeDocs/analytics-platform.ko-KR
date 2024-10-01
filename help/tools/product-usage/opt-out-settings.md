---
title: 제품 사용 옵트아웃 설정
description: 조직 내의 개별 사용자에 대한 옵트아웃 설정을 관리합니다.
hide: true
hidefromtoc: true
source-git-commit: 5c18fd78a71ddffef62dc3ac69f1abc3b42bddda
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# 제품 사용 옵트아웃 설정 {#product-usage-opt-out-settings}

_옵트아웃 설정_ 페이지에서는 제품 사용 추적에서 조직 내의 사용자를 제외하거나 다시 포함할 수 있습니다.

**Customer Journey Analytics** > **[!UICONTROL 도구]** > **[!UICONTROL 제품 사용]** > **[!UICONTROL 옵트아웃 설정]**

이 페이지에서는 다음 설정을 사용할 수 있습니다.

* **[!UICONTROL 옵트아웃 사용자]**: 조직의 모든 Customer Journey Analytics 사용자가 포함된 드롭다운 목록입니다. 이 드롭다운 목록에서 사용자를 선택하고 **[!UICONTROL 옵트아웃]**&#x200B;을 선택하여 해당 사용자를 제품 사용 추적에서 제외합니다. 해당 사용자는 아래의 [!UICONTROL 옵트아웃 사용자 목록] 표에 추가됩니다.
* **[!UICONTROL 옵트아웃 사용자 목록]**: 현재 제품 사용 추적에서 옵트아웃된 모든 사용자를 보여 주는 표입니다. 사용자를 제품 사용 추적에 다시 옵트인하려면 지정된 사용자 옆에 있는 확인란을 선택한 다음 **[!UICONTROL 옵트인]** 단추를 선택합니다.

Adobe은 클라이언트측과 서버측 추적을 결합하여 조직의 제품 사용 데이터를 수집합니다. 사용자가 처음에 옵트아웃되면 Customer Journey Analytics에 로그아웃했다가 다시 로그인할 때까지 해당 사용자는 디버거에 클라이언트측 추적 데이터를 계속 볼 수 있습니다. Adobe의 서버측 유효성 검사는 옵트아웃된 사용자에 대해 클라이언트측 추적 데이터가 삭제되도록 합니다.

>[!CONTEXTUALHELP]
>id="cja_product_usage_opt_out_settings"
>title="사용자 옵트아웃"
>abstract="제품 사용 추적에서 사용자를 제외합니다."
