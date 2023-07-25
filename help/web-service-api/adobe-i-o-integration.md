---
title: Adobe I/O integration overview
description: Information about creating an Adobe I/O integration.
exl-id: d7d31938-6c0e-40f8-a9d3-30af96043119
---
# Places API access overview and prerequisites {#developer-prereqs}

This information shows you how to create a Project in the Adobe Developer Console and generate an access token to be used in Places API requests.

## Prerequisites for user access

Verify with your organization's System administrator that the following tasks have been completed:

* You have been added to the organization. 
* You have been added to a profile within the Adobe Experience Platform. 

  For more information, see *Add a user or a developer to your Places Service and Experience Platform Launch profiles* in [Gain access to Places Service](/help/places-gain-access.md).

### REST API requests

Each request to the Places Service REST API requires the following items:

* An organization ID
* An API key (also referred to as a Client ID)
* Client Secret
* A bearer token

A Project with the [Adobe Developer console](https://developer.adobe.com/console) provides these items.

* To create a Project for Places Service API, see the *Creating a Places Service Project* section below.

>[!IMPORTANT]
>
>If you cannot log in to [Adobe Developer console](https://developer.adobe.com/console), or if Places Service is not an option on the *Create Integrations page*, see *Organization requirements* in [Web services API overview](/help/web-service-api/places-web-services.md).

## Creating a Places Service API Project

To create a Project for Places Service API, complete the following:

1. Log in to [Adobe Developer website](https://developer.adobe.com) with your Adobe ID.
2. Click on **[!UICONTROL Console]** in the upper right corner of the page.
3. If you are assigned to more than one Adobe organization, select the correct organization from the drop-down list in the upper right corner of the page.
4. Click the **[!UICONTROL Create new project]** button.
5. Click on **[!UICONTROL Add API]** button in the Get started with your new project section.
6. Scroll down the page to find the Places card, and click on the checkbox in the upper right corner of the card.
7. Click the **[!UICONTROL Next]** button.
8. Select the OAuth Server-to-Server option (If there is a choice).
9. Name the credential and click **[!UICONTROL Next]**.
10. Select a profile (any should work if there is more than one).
11. Click **[!UICONTROL Save and configure API]**.
12. In the left panel, click on the **[!UICONTROL OAuth Server-to-Server]** link under CREDENTIALS
13. This page provides the following:
    * Ability generate an access token to be used in the Places Service REST API requests.
    * View a curl command for an example how you can genereate an access token from your own code.
    * View the Client ID (also referred to as an API key)
    * View the Client Secret
    * View the Organization ID
    * All of which are required in the requests to the Places Service REST API.
14. You can rename the project to something more descriptive by clicking on the Project name in the path in the upper left of the window
15. Then click on the **[!UICONTROL Edit project]** button in the upper right of the page.

>[!IMPORTANT]
>
>Adobe access tokens are valid **only** for 24 hours, so save the sample CURL command (step 5). If the access token is no longer valid, you need to regenerate the token.
