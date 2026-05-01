---
title: Manage existing POIs
description: In the Places Service UI, you can edit, delete, or filter existing POIs.
exl-id: a4cf28ae-1e3c-4724-bca3-ac1d0cd6da09
TQID: https://experienceleague.adobe.com/2VnBQ5-flpx5cyeK3n5b3AOKqnt7RVkdqFBXYa9O5Ys
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: Experience Cloud
  - id: dc5cf79d-43c4-4731-bffa-1df5d7549cb1
    internal-label: Adobe Sign
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
# Manage existing POIs {#managing-existing-pois}

POIs and libraries are created and managed in the Places database by using the Places UI.

## Edit a POI

1. Log into Places using your Adobe ID.
1. Log into Places Service using your Adobe ID.
1. In the top right side, click the icon that looks like a bulleted list.
1. Locate the POI that you want to edit.
1. Click **[!UICONTROL ...]** and select **[!UICONTROL View Details]**.
1. Update the information and click **[!UICONTROL Save]**.

## Delete a POI

1. Log into Places using your Adobe ID.
1. Log into Places Service using your Adobe ID.
1. In the top right side, click the icon that looks like a bulleted list.
1. Locate the POI that you want to delete.
1. Click **[!UICONTROL ...]** and select **[!UICONTROL Delete]**.

## Filter POIs by city, state, country, or metadata

![filter a POI](/help/assets/filter_poi.png)

1. Log in to the Places Service UI using your Adobe ID.
1. In the top right side, click the filtering icon.
1. You can filter POIs in one of the following ways: 

   * By library:

      a. Select a library.

   * By property:

      a. In Property drop-down list, select **[!UICONTROL Country]**, **[!UICONTROL State]**, or **[!UICONTROL City]**.

      b. In the next line, enter a value. 

        For example, you can select **[!UICONTROL State]** and type **[!UICONTROL California]**.

   * With metadata:

      a. Enter a key and value.

## Defining a geofence POI

Geofences are a type of POI and are defined in the database based by the following keys:

| Keys | Description | Required? |
| :--- | :--- | :--- |
| ID | Unique identifier assigned to each POI | Yes |
| Name | Friendly name given to the POI. | Yes |
| Library | Each POI must be assigned a library for organization. | Yes |
| Radius | The radius for your POI in meters. | Yes|
| Icon | Assist with visualizations of the POIs. | Yes (assigned default) |
| Color | Assist with visualizations of the POIs. | Yes (assigned default) |
| Category | Assign a common framework of categories that are common across all POIs in all libraries. | No |
| Address | Street address. | No |
| City | City of the POI. | No |
| State/Region | State or region of the POI. | No |
| Country | Country of the POI. | No |
| Latitude | Latitude coordinate for the center of the POI. | Yes |
| Longitude | Longitude coordinate for the center of the POI. | Yes |
| Metadata | Custom key and value pairs that can be assigned to POIs. This metadata streamlines future workflows by allowing you to group POIs across libraries for each to use rules and filters in downstream workflows such as send a push notification when someone enters a POI with the Type = Competitor. | No |
