---
title: Send Places data to Adobe Analytics
seo-title: Send Places data to Adobe Analytics
description: This section provides information about how to send Places data to Analytics.
seo-description: This section provides information about how to send Places data to Analytics. 
---

# Send Places data to Adobe Analytics {#places-data-analytics}


>[!IMPORTANT]
>
>This document assumes that you have Places implemented in your application. For more information about implementing Places, see [Places Extensions](/help/places-ext-aep-sdks/places-extension/places-extension.md).

After Places sends the entry and exit events, you can create rules in Experience Platform Launch to send Places data to Adobe Analytics. To create this type of rule, select your property in Launch and complete the following steps:

## 1. Create a Rule

1. On the **[!UICONTROL Rules]** tab, click **[!UICONTROL Create New Rule]**.

    Remember the following information:

    * If you do not have existing rules for this property, the button will be in the middle of the screen.
    * If your property has rules, the button will be in the top right of the screen.

## 2. Select an Event

1. Give your rule a meaningful name so it will be easily recognizable in your list of Rules. In this example, the Rule is named **Send Data to Analytics**.

2. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

3. From the **[!UICONTROL Extension]** drop-down list, select **[!UICONTROL Places]**.

4. From the **[!UICONTROL Event Type]** drop-down list, select **[!UICONTROL Enter POI]**.

5. Click **[!UICONTROL Keep Changes]**.

   !["select an event"](/help/assets/pt-selectEvent.png)


## 3. Add Conditions

>[!IMPORTANT]
>
>Complete this step if you want to add Conditions to your rule. Otherwise, skip to *Define the Action* below.


In this example, a Condition is created that causes the Rule to trigger only when the Current POI's name equals **[!UICONTROL My POI]**.

1. Under the **[!UICONTROL Conditions]** section, click **[!UICONTROL Add]**.

2. From the **[!UICONTROL Extension]** drop-down list, select **[!UICONTROL Places]**.

3. From the **[!UICONTROL Condition Type]** drop-down list, select **[!UICONTROL Name]**.

4. In the window on the right, in the text field, enter **[!UICONTROL My POI]**.

5. Click **[!UICONTROL Keep Changes]**.

   !["set a condition"](/help/assets/ad-setCondition.png)


## 4. Define the Action

1. Under the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

2. From the **[!UICONTROL Extension]** drop-down list, select **[!UICONTROL Adobe Analytics]**.  

3. From the **[!UICONTROL Action Type]** drop-down list, select **[!UICONTROL Track]**.

4. On the right pane, add the action or state that you want to send to Analytics. You can also choose to add any additional context data to this request. Remember that you can use data elements to get this data dynamically from the SDK.

5. Click **[!UICONTROL Keep Changes]**.

In the following example, a `TrackAction` call is sent to Analytics with additional context data of **poi.name** equal to the name of the POI that triggered this entry event:

!["set an action"](/help/assets/pt-setAction.png)

## 5. Save the Rule and Rebuild your Property

After you complete your configuration, verify that your Rule looks like the following image:

!["rule is created"](/help/assets/pt-ruleComplete.png)


1. Click **[!UICONTROL Save]**

2. Rebuild your Launch property and deploy it to the correct Environment.
