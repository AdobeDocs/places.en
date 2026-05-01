---
title: Using metadata with POIs
description: This section provides information and strategies about how to use metadata with POIs.
exl-id: e669e560-a999-43ff-aeb4-06e6308b0d5c
TQID: https://experienceleague.adobe.com/wTzahAs7MMSv0q-cEhkNObBpALUJXqDXlOcqjitezwY
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: Experience Cloud
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
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
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Strategies for using metadata with POIs {#using-metadata-pois}

In Places Service, when you create a a new POI, the only required elements are Name, Radius, Latitude and Longitude. For more information about creating a POI, see [Create a POI](/help/poi-mgmt-ui/create-a-poi-ui.md). If, however, you are only entering the minimum information, you will miss an opportunity to create additional value.

POI metadata can be used in a variety of ways. From a POI management standpoint, adding metadata values can help in searching for or filtering a list of potentially thousands of POIs. Creating metadata for key attributes related to a POI can yield value in downstream workflows. For instance, a hotel chain creating POIs for each property may want to include metadata such as if the hotel property has a pool or not, or a restaurant and bar, or if they have a gym facility. This metadata can be included as context data in analytics and can also be used for targeted offers or messaging.

## Places Service metadata in Launch

In Experience Platform Launch, you can create data elements for each Places Service metadata field that is important for tracking or messaging purposes.

![data element for the gym facility](/help/assets/gymfacility.png)

You can then create an action with the Analytics extension for creating a new hit that includes whatever metadata you would like as context data.

![action for the gym facility](/help/assets/Analytics-gym.png)

## In-App Messaging in Adobe Campaign

Metadata can be used as a filter for local notifications and in-app messages defined in Adobe Campaign Standard. Using metadata as a filter affords the opportunity to create a more relevant message that is contextual to the actual location.

![filtering local notifications and in-app messages in ACS](/help/assets/ACS_gym_metadata.png)
