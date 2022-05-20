---
description: Find out how AEP Customer AI integrates with Workspace in CJA.
title: Integrate Customer AI with CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: b82bf04bb09a38f1cd475ecd2036acc240b7ef38
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Integrate Customer AI with CJA

>[!NOTE]
>
>This functionality will be released on May 25, 2022.

[](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en)

With the help of influential factors, Customer AI can tell you what a customer is likely to do and why. Additionally, marketers can benefit from Customer AI predictions and insights to personalize customer experiences by serving the most appropriate offers and messaging.

Customer AI relies on individual behavioral data and profile data for propensity scoring. Customer AI is flexible in that it can take in multiple data sources, including Adobe Analytics, Adobe Audience Manager, Consumer Experience Event data and Experience Event data. If you use the AEP data connector to bring in Adobe Audience Manager and Adobe Analytics data, the model automatically picks up the standard event types to train and score the model. If you bring in your own Experience Event dataset without standard event types, any relevant fields will need to be mapped as custom events or profile attributes if you&#39;d like to use it in the model. This can be done in the Customer AI configuration step. &#x200B;

Customer AI integrates with Customer Journey Analytics (CJA) to the extent that Customer AI-enabled datasets can be leveraged in data views and reporting in CJA. With this integration, you can

* **** Example use case: What is the likelihood of a hotel customer to purchase a show ticket at the hotel’s concert venue?
* **** Example use case: I want to understand the attributes or success events associated with propensity scores.
* **** Example use case: I’d like to understand people who were initially low-propensity users and, over time, became high-propensity users.&#x200B;
* **** Use case: I’d like to understand the distribution of the propensity scores to I can be more precise with my segments. &#x200B;Example: a retailer wants to run a specific promotion for $50 off a product.  They may only want to run a very limited promotion due to budget, etc. They analyze the data and decide to target only the top 80%+&#x200B; of their customers.
* **** Use case: I’d like to track a specific cohort over time. This is similar to the first one, but you can track a specific cohort over time.&#x200B; Hospitality example: A marketer can track their bronze tier versus their silver tier, or silver tier versus their gold tier over time. Then they can see each cohort&#39;s propensity for booking the hotel over time. &#x200B;

## 워크플로

Some of the steps are performed in Adobe Experience Platform prior to working with the output in CJA.

### Step 1: Configure a Customer AI instance

[](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en)

### Step 2: Set up a CJA connection to Customer AI datasets

[](/help/connections/create-connection.md) Each prediction, such as &quot;Likelihood to upgrade account&quot;, equates to one dataset. These datasets appears with the &quot;Customer AI Scores&quot; prefix, as shown here:

![](assets/cai-scores.png)

![연결 생성](assets/create-conn.png)

Here is an example of a XDM schema that CJA would bring in as part of an existing or new dataset:

![](assets/cai-schema.png)

(Note that the example is a profile dataset; the same set of schema object would be part of an Experience Event dataset that CJA would grab. The Experience Event dataset would include timestamps as the score date.) Every customer scored in this model would have a score, a scoreDate, etc. associated with them.

### Step 3: Create data views based on these connections

[](/help/data-views/create-dataview.md)

![](assets/create-dataview.png)

### Step 4: Report on CAI scores in Workspace

In CJA Workspace, you can now create a new project and pull in visualizations.

Here is an example of a Workspace project with CAI data that trends propensity scores for a segment of users over time, in &#x200B;a stacked bar chart:

![](assets/workspace-scores.png)

Here is a table that shows reason codes for why a segment has high or low propensity&#x200B;:

![](assets/reason-codes.png)

This flow diagram shows the entry flow for customer propensity over different scoring runs&#x200B;:

![](assets/flow.png)

This bar chart shows the distribution of propensity scores&#x200B;:

![](assets/distribution.png)

This Venn diagram shows the propensity overlaps over different scoring runs:

![](assets/venn.png)
