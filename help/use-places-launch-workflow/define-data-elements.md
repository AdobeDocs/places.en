---
title: Define data elements
description: This section provides information about how to create, use, and publish data elements in Experience Platform Launch for Places.
exl-id: 57e88a37-0b0b-4064-ab72-382a36a0d01d
TQID: https://experienceleague.adobe.com/NQ83uUZJtNglAcxD6HNl4Gw1Y8-0-uqfu-hH8H0EITg
product_v2:
  - id: a829a185-511f-4bf8-8dcf-9e684f8011cf
    internal-label: Advertising
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: Experience Cloud
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
feature_v2:
  - id: e08599ea-8888-4294-ba74-3ba0a7762a46
    internal-label: Data collection
subfeature_v2:
  - id: d2a6cbf4-df32-480f-909e-b42f66dcb9f0
    internal-label: Places
  - id: f9a2105e-7a47-4e85-9193-31a519a2cb83
    internal-label: Data elements
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Define a data element {#define-data-elements}

The following information helps you understand data elements and how to create and publish them. 

## About data elements

Data elements are the building blocks for the application's data dictionary and are used to collect, organize, and deliver data across marketing and ad technology.

A data element is a variable where the value can be mapped to a Visitor ID, a Carrier Name, an Advertising ID, a Push ID and so on. In Experience Platform Launch, you can reference this value by its variable name. This collection of data elements becomes the dictionary of defined data that you can use to build your rules (events, conditions, and actions), and this dictionary is shared across Experience Platform Launch where it can be used with any extension in your property.

With the Places extension, you can reference values from the following targets:

* Current POI, which refers to the POI in which your customer is currently located. 

    If the user is located in multiple POIs, the one belongs to the library with higher rank is picked. If multiple POIs belong to the highest rank library, the one with the smallest radius is picked.
* Last exited POI, which refers to the most recent POI that the user exited.
* Last entered POI, which refers to the most recent POI that the user entered. 

Each POI contains the following data references:

* **[!UICONTROL Category]**: category of the POI
* **[!UICONTROL City]**: city of the POI
* **[!UICONTROL Country]**: country of the POI
* **[!UICONTROL Latitude]**: latitude of the POI
* **[!UICONTROL Longitude]**: longitude of the POI
* **[!UICONTROL Metadata]**: custom metadata of the POI
* **[!UICONTROL Name]**: name of the POI
* **[!UICONTROL Radius]**: radius of the POI
* **[!UICONTROL Region ID]**: ID of the POI
* **[!UICONTROL Region/State]**: region, province or state of the POI

### Create a data element

1. In the Property page for your app, click the **[!UICONTROL Data Elements]** tab.

1. Click **[!UICONTROL Create New Data Element]**.

1. In the list of installed extensions, find **[!UICONTROL Places]**.

1. In the **[!UICONTROL Data Element Type]** drop-down list, select a data reference for this data element.

1. Select a POI target.

1. If this data element is a custom metadata reference, select a metadata key.

1. Type a name for the data element and click **[!UICONTROL Save]**.

    ![Create data element](/help/assets/create-de-7-v3.png)


## Use a data element

After a data element is created, if a data element picker is present, you can use the data element from any rule component.

![Use the data element](/help/assets/use-de-v2.png)

If a data element picker is not present in the rule component, you can use the data element by wrapping the data element name with the **[!UICONTROL %%]** tokens.
For example, if the data element name is **[!UICONTROL Last POI City]**, you may add **[!UICONTROL LAST POI City]** to a text input.


## Publish data elements

If data elements are used in any of the rule components, these data elements must also be included in the library and published.
