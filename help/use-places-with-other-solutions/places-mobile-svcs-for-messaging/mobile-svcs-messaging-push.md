---
title: Push notifications
description: This section shows you how to use Places Service with push notifications.
exl-id: c094fe9c-6148-45ba-850a-f4c520d3362c
TQID: https://experienceleague.adobe.com/aaTMSoOkVUfbPDpPiRm7P3-8d8JSO9N0Ga12Hlmf-go
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: Experience Cloud
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
feature_v2:
  - id: e08599ea-8888-4294-ba74-3ba0a7762a46
    internal-label: Data collection
subfeature_v2:
  - id: d2a6cbf4-df32-480f-909e-b42f66dcb9f0
    internal-label: Places
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Push notifications

Mobile Services allows you to send push notifications to Adobe Analytics segments. In Places Service, you can segment the audience for your push message by using their historical interactions with your POIs. For example, you can send a message to users who have been in one of your stores in the last 30 days.

Before you begin, ensure that you have completed the following tasks:

* Places Service data has been processed by Adobe Analytics.

  This means that your mobile app has successfully sent Places Service data into a Report Suite and that the data is available for segmentation.

* The push notification channel in Mobile Services is set up.

  For more information, see [Create a push message](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html).

* Understand how to send a push notification to an Analytics segment in Mobile Services.

  For more information, see [Create a push message](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html).

## Send a notification

On the **[!UICONTROL Audience]** tab of the *Create push notification* workflow, you can create the audience for this message in one of the following ways:

* In the **[!UICONTROL Analytics Segments]** drop-down list, select a previously created Adobe Analytics segment.

* In the **[!UICONTROL Custom Segment]** section, build an audience by using the available custom segment parameters.

![setting up a push message](/help/assets/push-set-up.png)
