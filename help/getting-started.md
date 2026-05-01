---
title: Getting started
description: Getting started with Places Service.
exl-id: 1f0ac226-4993-495b-9d07-1e0ada7f19a7
TQID: https://experienceleague.adobe.com/NjssmuGH8672GGroi6sil5e0INPIDAcJl7Uz623-Vts
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: Experience Cloud
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
  - id: f7bdf6be-dd3b-4d2d-ac52-0e62ed0d3102
    internal-label: Admin Console
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
# Getting started {#getting-started}

Here is a helpful video to get an overview of Places Services:

<!--
Test of different youtube link for exl
-->

>[!VIDEO](https://video.tv.adobe.com/v/41647)
 
## Using Places Service

To use Places Service, complete the following tasks: 
 
### 1. Ensure that your user is provisioned to use Places Service
 
The Places Service product context is available with all Experience Cloud organizations. 
 
* Ensure that you are listed as a user under the Places Service and Experience Platform Launch product contexts in the Admin Console.  
 
   For more information, see *Adding a user to Experience Platform Launch and Places Service* in [Frequently asked questions](/help/places-gain-access.md).
 
  
### 2. Create your POIs
 
Points of Interest (POI) are geo-fences that you create for your organizations, and you can create POIs in one of the following ways:

* Using the Places Service user interface. 

  For more information, see [Places Service overview](/help/poi-mgmt-ui/poi-mgmt-ui-overview.md). 

* Using the APIs from Places Web service. 

  For more information, see [Web Service API](/help/web-service-api/places-web-services.md).


### 3. Configure the Places extension

For more information about configuring the Places extension, see the following information:

* [Places extension](/help/places-ext-aep-sdks/places-extension/places-extension.md)

### 4. (Optional) Implement a region monitoring solution

If you plan to do active region monitoring, you will need to implement directly with operating system. For more information, see the following documents:

* iOS - [CoreLocation documentation](https://developer.apple.com/documentation/corelocation/monitoring_the_user_s_proximity_to_geographic_regions) 

* Android - [Location documentation](https://developer.android.com/training/location/geofencing)