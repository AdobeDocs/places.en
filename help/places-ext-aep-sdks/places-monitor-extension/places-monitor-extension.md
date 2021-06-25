---
title: Places Monitor extension
description: The Places Monitor extension handles the interactions with the operating system to register and monitor the POIs that are closest to the user.
exl-id: 254b33a0-79c4-4d51-8835-16e60f5c055e
---
# Places Monitor extension {#places-monitor-extension}

The Places Monitor extension handles the interactions with the operating system to register and monitor the POIs that are closest to the user. This extension retrieves the POIs that need to be registered from the Places extension and passes the entry and exit notifications to the Places extension. These notifications will be available in Experience Platform Launch rules as events.

The Monitor extension is optional, because some customers might already be monitoring regions with the operating system. If this is the case, ensure that you add the Places extension APIs to receive the nearest POIs from the Places Service database and to also pass the entry and exit events so that the appropriate actions can be taken.

# Places Monitor Deprecation

On August 31, 2021, the Places Monitor extension for the Adobe Experience Platform Mobile SDKs will be deprecated. The Places Monitor extension will not receive further updates or support beyond August 31st.

Customers that currently use the Places Monitor extension can continue usage of this extension with the understanding that no additional updates or support will be available through Adobe.

The deprecation of the Places Monitor extension has no bearing or negative impact on the Places Service extension which will continue to be supported with enhancements and updates.

Customers that are looking to transition away from the Places Monitor extension to their own monitoring solution should review the documentation for: [Use Places Service with your own monitoring solution](https://experienceleague.adobe.com/docs/places/using/using-your-own-monitor.html?lang=en). This document explains how to interact with the Places Service by implementing [Core Location services](https://developer.apple.com/documentation/corelocation) on iOS or [Location Services](https://developers.google.com/android/reference/com/google/android/gms/location/package-summary) from Google Play.
