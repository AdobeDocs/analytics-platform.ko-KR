---
title: Customer Journey Analytics으로 마이그레이션할 때 Adobe Experience Platform으로 데이터 보내기
description: Customer Journey Analytics으로 마이그레이션할 때 Adobe Experience Platform으로 데이터 보내기
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 1%

---

# 3단계: 업그레이드 시 Adobe Experience Platform으로 데이터 보내기

+++이 섹션을 확장하여 이 페이지의 정보가 대규모 업그레이드 프로세스에 적합한 위치를 확인합니다. 이전 업그레이드 단계가 모두 완료되었는지 확인합니다.

이 섹션을 계속하기 전에 먼저 이전 업그레이드 작업을 모두 완료했는지 확인하십시오.

이 페이지의 정보는 아래 표에 강조 표시된 대로 업그레이드 프로세스의 3단계를 다룹니다.

| 업그레이드 작업 | 세부 사항 |
|---------|----------|
| **1단계: [업그레이드 시작](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Customer Journey Analytics으로 업그레이드할 때의 이점 및 기본 업그레이드 프로세스에 대해 알아봅니다. |
| **2단계: [업그레이드 경로 선택](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Customer Journey Analytics으로 업그레이드하는 방법은 다양합니다. 조직의 현재 Adobe Analytics 환경 및 장기 목표에 따라 조직에 가장 적합한 방법을 선택합니다. |
| <span class="preview">**3단계: Adobe Experience Platform으로 데이터 보내기**</span> | <span class="preview">Adobe Experience Platform으로 데이터를 보내는 프로세스는 2단계에서 선택한 업그레이드 경로에 따라 다릅니다.</span> |
| **4단계: [내역 데이터 유지](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | 대부분의 조직은 특정 시간 동안 이전 Adobe Analytics 데이터를 유지해야 합니다. 이를 수행하기 위한 다양한 옵션을 사용할 수 있습니다. |
| **5단계: [추가 구현 작업 수행](/help/getting-started/cja-getting-started.md)** | 업그레이드 프로세스의 이 시점에서 Customer Journey Analytics 환경을 사용하기 전에 다양한 작업을 수행해야 합니다.<p>이러한 추가 작업은 새로운 Customer Journey Analytics 구현뿐만 아니라 Adobe Analytics에서의 업그레이드에도 적용됩니다.</p><p>이러한 작업에는 다음이 포함됩니다.</p><ul><li>Experience Platform으로 다른 데이터 가져오기</li><li>Platform 데이터 세트와 Customer Journey Analytics 간 연결 만들기</li><li>데이터 보기 만들기</li><li>보고 API 사용 포팅</li><li>데이터 피드 및 Data Warehouse 계정</li><li>프로젝트 및 구성 요소 마이그레이션</li><li>Planning 사용자 온보딩</li></ul> <p>자세한 내용은 [Customer Journey Analytics 시작](/help/getting-started/cja-getting-started.md)을 참조하세요. |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>이 페이지의 정보는 다음과 같은 보다 포괄적인 업그레이드 정보로 대체됩니다. <ul><li>**권장된 업그레이드 단계**<p>자세한 내용은 [Adobe Analytics에서 Customer Journey Analytics으로 업그레이드할 때 권장되는 경로](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)를 참조하십시오.</p></li><li>**Customer Journey Analytics 업그레이드 안내서**<p>조직 및 고유한 환경에 맞게 조정된 업그레이드 단계를 동적으로 생성하는 새로운 업그레이드 가이드를 사용할 수 있습니다.</p><p>Customer Journey Analytics에서 가이드에 액세스하려면 **[!UICONTROL Workspace]** 탭을 선택한 다음 왼쪽 패널에서 **[!UICONTROL Customer Journey Analytics으로 업그레이드]**&#x200B;를 선택합니다. 화면에 표시되는 안내를 따릅니다.</p></li></ul>

조직에 가장 적합한 업그레이드 경로를 [선택](/help/getting-started/cja-upgrade/cja-upgrade-path.md)한 후 Adobe Experience Platform에서 사용할 수 있도록 하기 위해 Customer Journey Analytics에 데이터를 전송할 수 있습니다.

각 업그레이드 경로에 대해 Experience Platform으로 데이터를 전송하는 프로세스는 아래에 나와 있습니다. 자세한 구성 정보는 표의 링크를 참조하십시오.

| 업그레이드 경로 | 데이터를 플랫폼으로 전송하는 프로세스 | 추가 정보 |
|---------|----------|----------|
| Experience Platform Web SDK의 새로운 구현 | <ol><li>조직에 대한 XDM 스키마를 만듭니다.<p>데이터 팀과 협력하여 Customer Journey Analytics에 대한 조직의 이상적인 스키마 디자인을 식별합니다.</p></li><li>Experience Platform Web SDK 구현</li><li>데이터를 플랫폼으로 전송합니다.</li></ol><p>이러한 각 단계에 대한 자세한 내용은 [Adobe Experience Platform Web SDK을 통해 데이터 수집](/help/data-ingestion/aepwebsdk.md)을 참조하십시오. | Experience Platform Web SDK의 새로운 구현이므로 구현 중에 첫 번째 단계 중 하나로 스키마를 만들어야 하므로 스키마 매핑이 필요하지 않습니다. |
| 웹 SDK을 사용하도록 Adobe Analytics 구현 마이그레이션 | <ol><li>기존 Adobe Analytics 구현을 Experience Platform Web SDK으로 이동한 다음 Adobe Analytics에서 모든 것이 작동하는지 확인합니다.<p>이 작업을 수행하는 방법에 대한 자세한 내용은 현재 구현이 Analytics 태그 확장인지 아니면 AppMeasurement인지에 따라 다음 리소스를 사용하십시오.</p><ul><li>Analytics 태그 확장을 사용하는 경우 [Adobe Analytics 태그 확장에서 웹 SDK 태그 확장으로 마이그레이션](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)을 참조하십시오.</li><li>AppMeasurement을 사용하는 경우 [AppMeasurement에서 웹 SDK으로 마이그레이션](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)을 참조하십시오.</li></ul><li>[조직에 대한 XDM 스키마를 만듭니다](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>데이터 팀과 협력하여 Customer Journey Analytics에 대한 조직의 이상적인 스키마 디자인을 식별합니다.</p></li><li>[데이터 준비를 사용하여 데이터 개체의 모든 필드를 XDM 스키마에 매핑합니다](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li><li>[데이터 스트림을 설정](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream)하여 플랫폼으로 데이터 전송을 시작합니다.</li></ol> |  |
| 데이터를 Platform으로 보내도록 기존 Adobe Analytics Web SDK 구현을 구성합니다 | <ol><li>[데이터 스트림을 설정](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream)하여 플랫폼으로 데이터 전송을 시작합니다.<p>Adobe Analytics 구현에서 이미 Experience Platform Web SDK을 사용하고 있으므로 [Adobe Experience Platform Web SDK을 통해 데이터 수집](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)의 다른 섹션을 무시할 수 있습니다.</p><p>Adobe Analytics 구현으로 이미 데이터를 Platform에 전송하는 경우 이 단계는 필요하지 않습니다. 이 프로세스의 뒷부분에서 설명한 대로 Platform 데이터 세트와 Customer Journey Analytics 간에 연결을 만들면 됩니다.</p></li><li>(선택 사항) [조직에 대한 XDM 스키마를 만듭니다](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>데이터 팀과 협력하여 Customer Journey Analytics에 대한 조직의 이상적인 스키마 디자인을 식별합니다.</p><p>참고: XDM 스키마를 만들 때의 장점에 대한 자세한 내용은 [스키마 선택](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema)을 참조하세요.</li><li>(조건부) XDM 스키마를 만든 경우 [데이터 준비를 사용하여 데이터 개체의 모든 필드를 XDM 스키마에 매핑합니다](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li></ol> |  |
| Analytics 소스 커넥터 사용 | [기존 Adobe Analytics에서 데이터 수집 및 사용](/help/data-ingestion/analytics.md) | Adobe Analytics 소스 커넥터를 사용하면 Analytics 데이터가 XDM 스키마에 자동으로 매핑됩니다. 추가 매핑이 필요하지 않습니다. |

## 그런 다음 내역 데이터 유지

다음으로 [내역 Adobe Analytics 데이터를 유지](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)하는 방법을 결정하십시오.
