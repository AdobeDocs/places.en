---
title: Frequently asked questions
description: This topic provides additional information about some frequently asked questions.
exl-id: cee9f447-5e50-4ed8-b37b-baecbc0e9b7b
TQID: https://experienceleague.adobe.com/LL9eLMDJaq8ZmeiZxv28QZoqXL1A0QKZ-DvTDUx4Gnw
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Frequently asked questions

Here is some information and frequently asked questions about Places Service.

## Migrating from trackLocation in the v4 SDK

If you are migrating from the v4 SDK and are looking for a replacement to the `trackLocation` API, please refer to the topic [Use Places Service without Active Region Monitoring](use-places-without-active-monitoring.md).

## Size and reliability  

Important to note for all geofences being used in region monitoring from a mobile app regardless of using Adobe or some other service. The Operating systems recommend some parameters to keep in mind when creating geofences. For maximum reliability, geofences should have a radius of at least 100 meters. It is okay to create smaller geofences, but entry and exit events may not be generated, or may be generated after the user stops moving for a period.

In addition, accuracy and reliability may be reduced based on hardware conditions such as wi-fi being turned off or unavailable, and also based on the device's location in relation to hampering GPS signals. For example, mountainous areas, urban settings, and indoor areas can reduce location accuracy from the iOS and Android operating systems.

## How does an exit event trigger?

The implemented region monitor should reqeust a list of nearby POIs. Once received, a region should be registered with the operating system for each POI. The operating system is now responsible for notifying the SDK when the device crosses a boundary (entry or exit) for one of the monitored regions. The SDK only triggers an exit event when the operating system notifies the SDK that the event has occurred. The main reason for this notification is the time sensitivity of the location data.  

If the operating system cannot deliver an exit event when the device leaves a region, it is safer for the SDK to just omit the exit event. If the SDK manufactures an exit event without the event being triggered by the operating system, there is a risk that the exit event might be processed well outside the time period during which the device was near the POI.

## Number of POIs

In the Places Service POI management interface, customers can add up to 150 thousand points of interest in a specific library. Customers can define multiple libraries to segment groupings of POIs if desired.

## Some notes about location change and active region monitoring

Monitoring of a geographical region begins immediately after registration for authorized apps. However, don’t expect to receive an event right away, because only boundary crossings generate an event. In particular, if the user’s location is already inside the region at registration time, the location manager doesn’t automatically generate an event. Instead, your app must wait for the user to cross the region boundary before an event is generated and sent to the delegate.

Be judicious when specifying the set of regions to monitor. Regions are a shared system resource, and the total number of regions available systemwide is limited. For this reason, Core Location limits to 20 the number of regions that may be simultaneously monitored by a single app. To work around this limit, consider registering only those regions in the user’s immediate vicinity.

[See additional information on the Apple developer site] (https://developer.apple.com/library/archive/documentation/UserExperience/Conceptual/LocationAwarenessPG/RegionMonitoring/RegionMonitoring.html#//apple_ref/doc/uid/TP40009497-CH9-SW11)
