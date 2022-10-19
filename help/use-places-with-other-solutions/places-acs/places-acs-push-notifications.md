---
title: Push notifications with Places Service
description: This section provides information about how to use Places Service with push notifications in Campaign Standard.
exl-id: 4b50f552-deb8-49cd-9221-fbbf33aaa5f9
---
# Push Notifications with Places Service {#push-notifications}

In this section, you will learn how to use historical geo-location information to target push notifications that are delivered through Adobe Campaign Standard. 

## Prerequisites

Before you begin, complete the following tasks:

* Have a mobile application configured with the Adobe Experience Platform Mobile SDK, including the [Adobe Campaign Standard extension](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard). 

* Integrate the [Adobe Experience Platform Mobile SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) into your app.
* Add the [Adobe Campaign Standard Extension](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) to your mobile app configuration.

* [Create a POI](/help/poi-mgmt-ui/create-a-poi-ui.md) in the Places Service POI management interface.

* Enable and install the [Places extension](/help/places-ext-aep-sdks/places-extension/places-extension.md).


## Create data elements in Experience Platform Launch

After verifying that the Places extension and a region monitoring solution ([CoreLocation documentation](https://developer.apple.com/documentation/corelocation/monitoring_the_user_s_proximity_to_geographic_regions) for iOS, or [Android location documentation](https://developer.android.com/training/location/geofencing)) are working correctly in your application, you need to create data elements in Experience Platform Launch. Data elements allow you to read the information that was provided by the extensions coming through the Mobile SDK event hub and act as an alias to retrieve data from the client application. To retrieve data from the Places extensions and send the Places Service information to Campaign, you need to create a few data elements.

To create a data element:

1. In your Experience Platform Launch mobile property, click the **[!UICONTROL Data Elements]** tab and click **[!UICONTROL Add Data Element]**.
1. In the **[!UICONTROL Extension]** drop-down list, select **[!UICONTROL Places Service]**.
1. From the **[!UICONTROL Data Element Type]** drop-down list, select **[!UICONTROL Name]**.
1. In the right-hand side pane, you can select **[!UICONTROL Current POI]** which retrieves the name of the POI in which the user is currently located.

   **[!UICONTROL Last Entered]** retrieves the name of the POI that user last entered, and **[!UICONTROL Last Exited]** provides the name of the POI that the user last left. In this example, we selected **[!UICONTROL Last Entered]** and typed a name for the data element, such as **[!UICONTROL Last Entered POI Name]** and clicked **[!UICONTROL Save]**.

   !["Push messaging in Campaign Standard"](/help/assets/ACS_Push1.png)

1. Repeat the steps 1-4 above and create data elements for *Last Entered POI Latitude*, *Last Entered POI Longitude*, and *Last Entered POI Radius*.

In addition to the data elements for Places Service, ensure that you create Mobile Core data elements for *App ID* and *Experience Cloud ID*.

## Create a rule to send location data to Adobe Campaign Standard

Rules in Experience Platform Launch allow you to create complex, multi-solution workflows based on event triggers. With rules, you can create new rules or modify existing ones and have the updates dynamically deployed to your mobile applications. In the following example, the rule will be triggered when a user enters a geo-fenced POI. After the rule is triggered, an update is sent to Campaign Standard to record an entry to a specific POI for a particular user based on the Experience Cloud ID.

1. In your Experience Platform Launch mobile property, on the **[!UICONTROL Rules]** tab, click **[!UICONTROL Add Rule]**.
1. Under the **[!UICONTROL Events]** section, click **[!UICONTROL +]** and select **[!UICONTROL Places Service]** as the extension.
1. For the **[!UICONTROL Event Type]**, select **[!UICONTROL Enter POI]**.
1. Name the rule, for example, **User entered POI**.
1. Click **[!UICONTROL Keep Changes]**.
1. Leave the **[!UICONTROL Conditions]** section blank.

    This section allows you to filter or place restrictions on when this rule should fire.

1. Under the **[!UICONTROL Actions]** section, click **[!UICONTROL +]**.
1. In the **[!UICONTROL Extension]** drop-down list, select **[!UICONTROL Mobile Core]** and in the **[!UICONTROL Action Type]** drop-down list, select **[!UICONTROL Send Postback]**.
1. In **[!UICONTROL URL]**, you need to construct your Campaign Standard locations endpoint.  

    The URL should look similar to `https:///rest/head/mobileAppV5//locations/`.
    Ensure that you use the correct data elements that you created previously for your Campaign server and pKey. 

1. Click the box to add a post body and send the following:

    ```
    {
     "locationData": {
     "distances": "{%%Last Entered POI Radius%%}",
     "poiLabel": "{%%Last Entered POI Name%%}",
     "latitude": "{%%Last Entered POI Lat%%}",
     "longitude": "{%%Last Entered POI Long%%}",
     "appId": "{%%AppID%%}",
     "marketingCloudId": “{%%ecid%%}”
     }
    }
    ```

1. Ensure that you use data elements that you created in the previous section.
1. In **[!UICONTROL Content Type]**, type **[!UICONTROL application/json]**.
1. Click **[!UICONTROL Keep Changes]**.

>[!IMPORTANT]
>
>* It might be helpful to have a Slack web hook set up as an additional action to validate that entries are being triggered and that the right data is being collected.
>* Remember to publish the recent changes to your app to make sure the rule and all of your data elements are deployed as part of your configuration. After you publish, launch the mobile application again to get the latest configuration updates.

## Use location data to target Campaign Messages

Now that we have location data populated in Campaign, we can use POIs as an audience segment tool.

1. In your Adobe Campaign Standard instance, click **[!UICONTROL Create Push Notification]**.
1. For the push notification type, select **[!UICONTROL Send push to Campaign profiles]**.
1. Click **[!UICONTROL Next]** and type the general details.
1. On the Audience screen, click **[!UICONTROL Count]** to determine to how many estimated users the push notification will be sent.

    >[!TIP]
    >
    >In this example, the count will be 3, because there are three installed devices on which the application is being tested.

1. In the left pane, expand the **[!UICONTROL Profile]** tab and drag the **[!UICONTROL POI location]** filter to the main area.
1. In the POI filter window, enter the exact name of the POI that you want to target.

    >[!TIP]
    >
    >You can make additional selections to determine the period of time since the user’s previous visit to this POI.

    !["Push messaging 2 in ACS"](/help/assets/ACS_push2.png)

1. Click **[!UICONTROL Confirm]**.
1. Run the count again at the top to see your audience size change.  

    If you do not see your count update, you might have entered a POI name for which no devices have triggered an entry. Having the Slack web hook becomes valuable in this situation, because you can see a listing of POI entries from various test devices.

1. You can drag out additional POI location filters to include multiple POIs in your message.
1. Click **[!UICONTROL Next]** to finish creating the push notification for delivery.

    !["Push messaging 3 in ACS"](/help/assets/ACS_push3.png)

Using Places Service with Adobe Campaign Standard gives you a powerful tool to segment and target your messaging to users based on geo-fence entries and exits. This integration helps you build more personalized and contextual use cases.
