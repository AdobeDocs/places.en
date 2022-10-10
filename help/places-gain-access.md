---
title: Gain access to Places Service 
description: This section provides information about how to add a user to Places Service and Experience Platform Launch, so that the user can access Places Service.
exl-id: f388945e-cf26-4694-9697-9fe564ae4b69
---
# Gain access to Places Service {#adding-user-launch-places}

Places Service is now available within the Data Collection UI. You can access Data Collection from the quick access menu on [Adobe Experience Cloud home](https://experience.adobe.com). 

![quick access menu](/help/assets/quickaccess.png)

You can also access Data Collection from the Adobe Experience Platform menu:

![Experience Platform menu](/help/assets/solutionaccessmenu.png)

If your user ID has access you will see the Places Service icon in the left panel under Data Management in Data Collection as indicated below:

![Data Collection left panel](/help/assets/places_in_data_collection.png)

If you do not see the Places Service in this location, contact an administrator in your organization to add your user ID to Adobe Experience Platform in the Admin Console. 

## Adding a user to access Places Service and Experience Adobe Experience Platform Data Collection

Places is now included with Adobe Experience Platform. To allow users to access the [Places Service](https://experience.adobe.com/#/data-collection/places), they need to be added to Adobe Experience Platform in the Admin Console as a user. To allow users to have access to Experience Platform Data Collection with the required permissions to configure mobile properties and use Places with the Adobe Experience Platform SDK, they need to also be added to Adobe Experience Platform Data Collection in the Admin Console and be given the following permissions for Adobe Experience Platform Data Collection:

* All permissions under Property Rights:
  * Approve
  * Develop
  * Edit Property
  * Manage Environments
  * Manage Extensions
  * Publish
* Manage Properties permission under Company Rights 

If this is the first time you are adding a user, complete the following steps to add users to Adobe Experience Platform Data Collection and Adobe Experience Platform. If you have added users before, multiple profiles might be displayed, so ensure that you select the correct profile.

>[!IMPORTANT]
>
>Only org administrators can access the Admin Console and add the users.

### 1. Verify that Adobe Experience Platform and Adobe Experience Platform Data Collection are provisioned 

1. Log in to your Experience Cloud organization, [Adobe Experience Cloud home](https://experience.adobe.com).
1. In the top-right side, click the Experience Cloud shell switcher to reveal a drop down menu.

    ![shell switcher](/help/assets/places_shell_switcher1.png)

1. At the bottom of the list, click **[!UICONTROL Admin Console]**. (A link to the **[!UICONTROL Admin Console]** can also be found in the Quick access section).

   If you do not see **[!UICONTROL Admin Console]** in the list, you are not an admin. You must contact your org admin to complete this procedure.

1. In the Admin Console, if you have access to several organizations, verify that the correct organization is selected in the top right of the page. 

    This is the organization to which you will add your users. If the correct organization has not been selected, click on the organization and select the correct organization from the drop-down list. 

    >[!IMPORTANT]
    >
    >If the desired organization is not in the drop down list, it means that you do not have admin access to that organization.

1. In the Admin Console, click on the Products tab and verify that the cards for **[!UICONTROL Adobe Experience Platform Data Collection]** and **[!UICONTROL Adobe Experience Platform]** are displayed.

    ![](/help/assets/places_provisioned1.png)

    These 2 products are automatically provisioned to all organizations, so they should be present.

   
### 2. Add user to these products

#### Add user to provide access to Places Service UI

1. From the Products tab, click on the **[!UICONTROL Adobe Experience Platform]** card.
2. A user can be added to any profile within **[!UICONTROL Adobe Experience Platform]** to gain access to Places, no specific permissions need to be set.
3. Choose a profile (if there is more than one) and click on it to open it. 
4. Click the blue **Add User** button, fill in the user with their AdobeID and name, then click Save to complete the addition.

#### Add user to Data Collection

1. From the Products tab, click on the **[!UICONTROL Adobe Experience Platform Data Collection]** card.
2. By default a profile named **Default Data Collection All Access** will have been created. Adding a user to this profile will ensure they have the proper permissions to work with Places Service and Data Collection. If a different profile is chosen, ensure the permissions are included that are mentioned above.
3. Choose a profile (if there is more than one) and click on it to open it.
4. Click the blue **Add User** button, fill in the user with their AdobeID and name, then click Save to complete the addition.

#### Add a user as a developer for Places Service.

For users who also need access to the Places Service REST API, you need to add them as a Developer.
1. From the Products tab, click on the **[!UICONTROL Adobe Experience Platform]** card.
2. If the user was already added to **[!UICONTROL Adobe Experience Platform]** card via the instructions above, choose the same previously used profile and click on it.
3. Within the profile, click on the **Developers** tab
4. Click the blue **Add Developer** button, fill in the user with their AdobeID and name, then click Save to complete the addition.

After completion of the above steps, the user will receive an email that notifies them they have access to **[!UICONTROL Adobe Experience Platform]** and **[!UICONTROL Adobe Experience Platform Data Collection]**. They can then log in to the [Adobe Experience Cloud](https://experience.adobe.com) for this organization and access Places Service and Data Collection. If you also complete the steps **[!UICONTROL Add a developer]**, the user can also log in to the [Adobe Developer Console](https://developer.adobe.com/console/home) to create a Project which would provide access to the Places Service REST API.
