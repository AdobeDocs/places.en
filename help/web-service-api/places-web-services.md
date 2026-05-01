---
title: Web Services API overview overview
description: Places Service is the set of services that makes it easier for Adobe customers to hydrate the Adobe Experience Cloud and Adobe Experience Platform solutions with location data and the right experience to the right person at the right time and in the right place.
exl-id: 9e7358d1-3ba0-4304-aeb2-fed7162afb57
TQID: https://experienceleague.adobe.com/jP7iQH7X85UZROjsa3XzuN0bJZjjKffODFGGji7XZfQ
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: Experience Cloud
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
# Web Services API overview {#places-web-services-api}

Places Service is the set of services that makes it easier for Adobe customers to hydrate the Adobe Cloud Platform and Adobe Experience Platform solutions with location data and the right experience to the right person at the right time and in the right place.

The web services APIs allow you to do the following:

* Manage geofences
* Measure the location of users even when app is in the background
* Use data in real-time when it matters

This section provides information about how to use the REST APIs and the POI database, which contains your org's POI data.

## REST APIs

The Places Service REST API let you work programmatically with your organization's POIs. These APIs allow you to create, update, and delete your libraries and the POIs in those libraries. These APIs use JavaScript Object Notation (JSON) standards to format the data that is sent and received. A principal advantage of JSON is that it makes API queries easy to write, read, and parse by developers and machines.

Before you can use the web services API, ensure that the following requirements have been met:

* Places Service is provisioned in your organization, and you have appropriate access as a user.

  For more information, see *Prerequisites for user access* in [Integration overview and prerequisites](/help/web-service-api/adobe-i-o-integration.md).

* After Places Service is provisioned in your organization, and you have access, create an Adobe integration for Places Service. 

  For more information, see *Creating a Places Service integration* in [Integration overview and prerequisites](/help/web-service-api/adobe-i-o-integration.md).

Additional information:

* For more information about information about the available APIs and how to use them, see [Manage libraries](/help/web-service-api/api-usage/manage-libraries/manage-libraries.md) and [Manage POIs](/help/web-service-api/api-usage/manage-pois/manage-pois.md). 
* For more information about the headers and parameters in these APIs, see [Headers and parameters](/help/web-service-api/api-usage/headers-and-parameters.md).
