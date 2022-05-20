---
description: Find out how AEP Attribution AI integrates with Workspace in CJA.
title: Integrate Attribution AI with CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: b82bf04bb09a38f1cd475ecd2036acc240b7ef38
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Integrate Attribution AI with CJA

>[!NOTE]
>
>This functionality will be released on May 25, 2022.

[](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en) With Attribution AI, marketers can measure and optimize marketing and advertising spend by understanding the impact of every individual customer interaction across each phase of the customer journeys.

Attribution AI supports two categories of scores: algorithmic and rule-based. Algorithmic scores include incremental and influenced scores.

* ****
* **** This baseline depends on AI observations of patterns, seasonality, and so on, due to existing brand recognition, loyalty, and word of mouth. The remaining credit is divided among marketing channels.

 Attribution AI supports 3 Experience Platform schemas: Experience Event, Adobe Analytics, and Consumer Experience Event.

Attribution AI integrates with Customer Journey Analytics (CJA) to the extent that Attribution AI runs models against data and then CJA imports the output of those models as a data set, which can then be integrated with the rest of your CJA data sets. Attribution AI-enabled datasets can be then be leveraged in data views and reporting in CJA.

## 워크플로

Some of the steps are performed in Adobe Experience Platform prior to working with the output in CJA. The output consists of a dataset with an applied Attribution AI model.

### Step 1: Create an Attribution AI instance

[](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html)

### Step 2: Set up a CJA connection to Attribution AI datasets

[](/help/connections/create-connection.md) These datasets appears with the &quot;Attribution AI Scores&quot; prefix, as shown here:

![](assets/aai-scores.png)

### Step 3: Create data views based on these connections

[](/help/data-views/create-dataview.md) (Would be great to have a screenshot here.)

### Step 4: Report on AAI data in CJA Workspace

In a CJA Workspace project, you can pull in metrics like &quot;AAI Orders&quot;, and dimensions like &quot;AAI Campaign Name&quot; or &quot;AAI Marketing Channel&quot;, for example.

![](assets/aai-dims.png)

Here we see a Workspace project with AAI data that shows orders with influenced and incremental scores.

![](assets/aai-project.png)

![](assets/aai-project2.png)


## Differences between Attribution AI and Attribution IQ

[](/help/analysis-workspace/attribution/overview.md) This table shows some of the differences in functionality:

| 기능 | Attribution AI | Attribution IQ |
| --- | --- | --- |
| Does fractional attribution | 예 | 아니요 |
| Allows users to adjust model | 예 | 예 |
| Does attribution across channels (Note: AAI does not use the same stitched data that CJA does.) | 예 | 예 |
| Includes incremental and influenced scores | 예 | 아니요 |
| Does ML modeling | 예 | 예 |
| Does ML modeling with predictions | 예 | 아니요 |

{style=&quot;table-layout:auto&quot;}
