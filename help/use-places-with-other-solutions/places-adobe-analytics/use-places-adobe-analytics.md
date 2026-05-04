---
title: Send POI entry and exit data to Analytics
description: This section provides information about how to send POI entry and exit data to Analytics.
exl-id: 69e96261-4902-47dd-a930-a8f3d19c179c
TQID: https://experienceleague.adobe.com/H-NkwK7KNSGPjEKYuWNc8F0f3MIu3wBr5FGjypxnqng
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: Experience Cloud
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: e08599ea-8888-4294-ba74-3ba0a7762a46
    internal-label: Data collection
subfeature_v2:
  - id: d2a6cbf4-df32-480f-909e-b42f66dcb9f0
    internal-label: Places
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Send POI entry and exit data to Analytics {#places-data-analytics}


>[!IMPORTANT]
>
>This section assumes that you have Places Service implemented in your application. For more information about implementing Places Service, see [Places extensions](/help/places-ext-aep-sdks/places-extension/places-extension.md).

After Places Service sends the entry and exit events, you can create rules in Experience Platform Launch to send Places Service data to Adobe Analytics. To create this type of rule, select your property in Launch and complete the following steps:

## 1. Create a rule

1. On the **[!UICONTROL Rules]** tab, click **[!UICONTROL Create New Rule]**.

    Remember the following information:

    * If you do not have existing rules for this property, the **[!UICONTROL Create New Rule]** button will be in the middle of the screen.
    * If your property has rules, the **[!UICONTROL Create New Rule]** button will be in the top right of the screen.

## 2. Select an event

1. Type a meaningful name for your rule.

    This way, the rule will be easily recognizable in your list of Rules. In this example, the Rule is named **[!UICONTROL Send Data to Analytics]**.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down list, select **[!UICONTROL Places Service]**.

1. From the **[!UICONTROL Event Type]** drop-down list, select **[!UICONTROL Enter POI]**.

1. Click **[!UICONTROL Keep Changes]**.

   !["select an event"](/help/assets/pt-selectEvent.png)


## 3. Add conditions

>[!IMPORTANT]
>
>Complete this step to add Conditions to your rule. Otherwise, skip to *Define the Action* below.

In this example, a Condition is created that causes the Rule to trigger only when the Current POI's name equals **[!UICONTROL My POI]**.

1. Under the **[!UICONTROL Conditions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down list, select **[!UICONTROL Places Service]**.

1. From the **[!UICONTROL Condition Type]** drop-down list, select **[!UICONTROL Name]**.

1. In the right pane, in the text field, enter **[!UICONTROL My POI]**.

1. Click **[!UICONTROL Keep Changes]**.

   !["set a condition"](/help/assets/pt-setCondition.png)


## 4. Define the action

1. Under the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down list, select **[!UICONTROL Adobe Analytics]**.  

1. From the **[!UICONTROL Action Type]** drop-down list, select **[!UICONTROL Track]**.

1. On the right pane, add the action or state that you want to send to Analytics.

    You can also choose to add any additional context data to this request. Remember that you can use data elements to get this data dynamically from the SDK.

1. Click **[!UICONTROL Keep Changes]**.

    In the following example, a `TrackAction` call is sent to Analytics with additional context data of `poi.name` equal to the name of the POI that triggered this entry event:

    !["set an action"](/help/assets/pt-setAction.png)

## 5. Save the rule and rebuild your property

After you complete your configuration, verify that your Rule looks like the following image:

!["rule is created"](/help/assets/pt-ruleComplete.png)

1. Click **[!UICONTROL Save]**

1. Rebuild your Launch property and deploy it to the correct environment.
