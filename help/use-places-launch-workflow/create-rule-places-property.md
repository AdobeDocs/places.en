---
title: Creating a rule for your Places Service property
description: The Places SDK keeps track of the current location, monitors the configured POIs around the current location, and tracks the entry and exit events for these POIs.
exl-id: dd5aa7ac-55f9-44dc-8632-e483ef3b91a0
---
# Create entry and exit rules {#create-entry-exit-rules}

With the Places extension and a region monitoring solution installed in your mobile application, you can create rules in Adobe Experience Platform Launch that are triggered or conditioned location data including location entry and exit events. 

## Rules

You can configure a rule, which is composed of an event, a condition, and an action. Each rule is composed of the following:

* One or more events
* (Optional) conditions
* One or more actions

### Places Service events

Places Service offers the following events on which you can run a rule:

* **Enter POI**, which is triggered by the Places SDK when your customer enters the POI that you configured.
* **Exit POI**, which is triggered by the Places SDK when your customer exits the POI that you configured.

### Places Service conditions

Conditions define the criteria that the data associated with the event, or the shared state of an extension at that instance, must meet for the action to be taken. For example, you can set a condition to trigger an action on an entry to a coffee shop only in the city of San Francisco.

The Places SDK maintains the following states:

* Current POI, which refers to the POI in which your customer is currently located.
* Last exited POI, which refers to the most recent POI that your customer exited.
* Last entered POI, which refers to the most recent POI that your customer entered.

Each POI contains the following data elements:

* ID 
* Name
* Latitude/longitude
* Radius
* Metadata such as city, country, state, category

### Actions

Actions define what the app will do in response to the condition for the rule is met for the fired event. For example, when your customer enters your POI, you can configure a welcome message to display on their mobile device.

## Create a rule: an example

>[!CAUTION]
>
>This example assumes that you have created a POI library of all coffee shops in the United States. For more information about creating POIs and libraries, see [Create a POI](/help/poi-mgmt-ui/create-a-poi-ui.md) and *Create a Library* in [Manage multiple libraries](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/manage-libraries-in-the-places-ui.html).

The following procedure is an example of how to create a rule that sends a post back to Slack when you enter a coffee shop in San Francisco.

The event, condition, and action are defined in the following ways:

* **Event**: Places entry event.
* **Condition**: City for the **Current POI** is San Francisco
* **Action**: Send a postback to Slack the name of the coffee shop that your customer entered.

### Prerequisite

Before you create a rule, you must create a data element in Adobe Experience Platform Launch. Data elements automatically populate the necessary information about your POI in the postback message.

To create a data element in Experience Platform Launch:

1. Click the **Data Elements** tab.
1. Click **Add Data Element**.
1. Type a name, for example, **Current coffee shop name**.
1. In the **Extension** drop-down list, select **Places – Beta**.
1. In **Data Element**, select **City**.
1. In the right pane, select **Current POI**.
1. Click **Save**.

### Create a rule in Experience Platform Launch for Places Service

![creating a rule](/help/assets/placesrule.png)

1. In Experience Platform Launch, click the **[!UICONTROL Rules]** tab.
1. Click **[!UICONTROL Add Rule]**.
1. Type a name for the rule, for example, **[!UICONTROL Track entry for coffee shop in SF]**.

### Create an event

1. In the Events section, click **[!UICONTROL + Add]**. Events determine when you want the rule to fire.
1. In the **[!UICONTROL Extension]** drop-down list, select **[!UICONTROL Places – Beta]**.
1. In the **[!UICONTROL Event Type]** drop-down list, select **[!UICONTROL Enter POI]**.
1. In **[!UICONTROL Name]**, enter a name for the event, for example, **[!UICONTROL Entering a coffee shop]**.
1. Click **[!UICONTROL Keep Changes]**.

### Create a condition

1. In the Conditions section, click **[!UICONTROL +Add]**. Conditions determine what criteria has to be met for the action to be taken.
1. In **[!UICONTROL Logic Type]**, select Regular, which allows actions to execute if the condition is met.
1. In the **[!UICONTROL Extension]** drop-down list, select **[!UICONTROL Places – Beta]**.
1. In **[!UICONTROL Condition Type]**, select **[!UICONTROL City]**.
1. Type a condition name, for example, **[!UICONTROL Coffee shop in SF]**.
1. In the right pane, click **[!UICONTROL Current POI]**, and in the drop-down list, select **[!UICONTROL San Francisco]** as one of your cities.
1. Click **[!UICONTROL Keep Changes]**.

### Create an action

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL + Add]**.
1. In the **[!UICONTROL Extension]** drop-down list, leave the default **[!UICONTROL Mobile Core]** option selected.
1. Select an action type, for example, **[!UICONTROL Send Postback]**.

   a. In **[!UICONTROL URL]**, type the postback URL for Slack, for example, `https://hooks.slack.com/services/`.

   b. To send a post body, select the **[!UICONTROL Add Post Body]** check box.

   c. In **[!UICONTROL Post Body]**, add the post body, for example: `{ "text": "A customer has entered" }`

   c. Type a content type for example **[!UICONTROL application/json]**.

   d. Select a timeout value, for example, **[!UICONTROL 5]**.

1. Click **[!UICONTROL Keep Changes]**.

### Publish the rule

1. To activate the rule, you must publish it. For more information about publishing your rule in Experience Platform Launch, see [Publishing](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html).

### Thinking beyond entries and exits

Using Places Service geo-fence entries and exits to trigger rules in Experience Platform Launch is incredibly powerful, but you can also use location data as a condition for other events to fire. For example, you could have a Mobile Core Track Action event trigger ready to fire based on a particular trackAction call event inside your app. Based on this event, you can place additional location conditions to the event before an action is performed. For example, open up an in-app survey when a purchase `trackAction` event occurs, but **only** if the user's current location includes specific Places Service metadata. 

![create a condition](/help/assets/places-condition.png)
