---
title: In-App messages with Places Service
description: This section provides information about how to use Push messaging in Campaign Standard with In-App messages in Campaign Standard.
exl-id: c80727b8-20c9-4ca0-9f2c-20ec646bb7fa
TQID: https://experienceleague.adobe.com/H2gW4nvnx8Es33S8nCt52OIUsNOY5SG1SZVJPw0BFFg
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: Experience Cloud
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
  - id: f002a92a-b99f-47a4-90c8-65e0e415bc7a
    internal-label: Pass
feature_v2:
  - id: d833d0ef-8ed5-4cff-a5e7-9f12abd02a31
    internal-label: SDKs
  - id: e08599ea-8888-4294-ba74-3ba0a7762a46
    internal-label: Data collection
subfeature_v2:
  - id: d2a6cbf4-df32-480f-909e-b42f66dcb9f0
    internal-label: Places
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# In-App messaging with Places Service {#in-app-messages-loc-service}

This information helps you understand how you can use Places Service information to send In-App Messages or Local Notifications.

## Prerequisites

Before you begin, complete the following tasks:

* Have a mobile application configured with the Adobe Experience Platform Mobile SDK, including the [Adobe Campaign Standard extension](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard). 

* Integrate the [Adobe Experience Platform Mobile SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) into your app.
* Add the [Adobe Campaign Standard Extension](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) to your mobile app configuration.

* [Create a POI](/help/poi-mgmt-ui/create-a-poi-ui.md) in the Places Service POI management interface.

* Install and configure the [Places extension](/help/places-ext-aep-sdks/places-extension/places-extension.md) and a region monitoring solution ([CoreLocation documentation](https://developer.apple.com/documentation/corelocation/monitoring_the_user_s_proximity_to_geographic_regions) for iOS, or [Android location documentation](https://developer.android.com/training/location/geofencing)) in your mobile application.

## Sending an In-App message based on a geo-fence entry or exit

1. In your Adobe Campaign Standard instance, click **[!UICONTROL Create In-App message]**.
1. For the message type, select **[!UICONTROL Target all users of a Mobile application]**.
1. Click **[!UICONTROL Next]** and type the general details.
1. In the left pane, verify that you can use a variety triggers that are related to Places Services.

    * You can choose to have the in-app message display if the user has entered a POI geo-fence.
    * You can also use metadata that is defined in the Places Services UI to filter audience.
 
    In the example below, you can trigger an in-app message that is displayed only to users who enter one of the vacation resorts that are participating in a free drink program, and you want to send those users a coupon when they arrive.

   !["In-App Message Places metadata"](/help/assets/last-entered-vacation.png)

1. Click the **[!UICONTROL Next]** to finish creating the In-app message for delivery.

    !["create an event"](/help/assets/prepare-ACS.png)

    To test the in-app message delivery, launch the application in Xcode or Android studio and use the location simulator to select a POI hat fits the messaging criteria.

    !["drink coupon"](/help/assets/drink-coupon-on-app.png)

Using Places Services with Adobe Campaign Standard gives you a powerful tool to segment and target your messaging to users based on geo-fence entries and exits. This integration allows you to build more personalized and contextual use cases.

<!--I changed this embed to a link to pass validation. We should not link to youtube videos, so please upload this to MCP-->

[Adobe Experience Platform Location Service with Campaign Messaging](https://www.youtube.com/watch?v=ikiTTQw9c-o)
