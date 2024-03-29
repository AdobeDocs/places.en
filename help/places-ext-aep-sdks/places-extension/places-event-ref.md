---
title: Places event reference
description: A list of the events that are handled by the Places extension.
feature: Mobile SDK
exl-id: 98210ef4-5ff1-4792-b97b-2845ce02e78a
---
# Places event reference {#places-event-reference}

Here is a list of the events that are handled by the Places extension.

## GetCurrentPointsOfInterest

**Event Details**

| Type | Source | Name | Paired |
| :--- | :--- | :--- | :--- |
| PLACES | REQUEST_CONTENT | `requestgetuserwithinplaces` | True |

**Event Description**

This event is a request to retrieve the POIs in which the device is currently located.

**Data Payload Definition**

n/a

## GetNearbyPointsOfInterest

**Event Details**

| Type | Source | Name | Paired |
| :--- | :--- | :--- | :--- |
| PLACES | REQUEST_CONTENT | `requestgetnearbyplaces` | True |

**Event Description**

This event is a request to get the nearby POIs by taking into consideration the current device location and the configured Places libraries.

**Data Payload Definition**

| Key | Value Type | Required | Default Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| latitude | double | true | n/a | Holds the latitude value for the center of the search for nearby POIs. |
| longitude | double | true | n/a | Holds the longitude value for the center of the search for nearby POIs. |
| radius | integer | false | n/a | Radius, in meters, used by the search for nearby POIs. |
| count | integer | false | 10 | Maximum number of POIs to return in resulting response event. |

## ProcessRegionEvent

**Event Details**

| Type | Source | Name | Paired |
| :--- | :--- | :--- | :--- |
| PLACES | REQUEST_CONTENT | `requestprocessregionevent` | False |

**Event Description**

This event causes the Places extension to process a geofence entry or exit event.

**Data Payload Definition**

| Key | Value Type | Required | Description |
| :--- | :--- | :--- | :--- |
| regionid | string | true | ID of the region generating the event. |
| regioneventtype | int | true | Type of region event being generated. 1 for entry and 2 for exit. |

## Events dispatched by the Places extension

This information is currently in progress.
