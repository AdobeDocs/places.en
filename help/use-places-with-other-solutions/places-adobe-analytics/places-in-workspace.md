---
title: Report on location data in Analytics Workspace
description: This section provides information about how to report on location data in Analytics Workspace.
exl-id: 45ca3c80-71b7-41de-9b00-645504061935
---
# Report on location data in the Analytics Workspace {#places-in-workspace}

This document shows an example of how to report on your location data in the Analytics Workspace. Each step will contain a high-level summary, with details provided by referencing other documentation pages. 

## Prerequisites

This document assumes the following:

1. The Places extension is implemented in your application. 

   For more information about implementing the Places extension, see [Places extensions](/help/places-ext-aep-sdks/places-extension/places-extension.md).

1. The Adobe Analytics user is an admin and has access to processing rules. 
  
   For more information about processing rules, see [Processing rules overview](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/c-processing-rules/processing-rules.html).

1. In Launch property, data elements have been created for the Places Service variables that you want. 

   For more information about data elements in Launch, see [Define a data element](/help/use-places-launch-workflow/define-data-elements.md).


## 1. Create a Launch rule

Create a rule that will cause the SDK to send data to Analytics when the device enters a POI. Creating this kind of rule is described on the [Send POI entry and exit data to Analytics](/help/use-places-with-other-solutions/places-adobe-analytics/use-places-adobe-analytics.md) page.

In this example, the rule's action has the following values defined for the Analytics request:

* **[!UICONTROL Action]** is provided a value of **[!UICONTROL Places Entry]**.

* The context data key **[!UICONTROL poi.name]** is set to the value of data element **[!UICONTROL {%%POI Name%%}]**.

!["set an action"](/help/assets/pt-setAction.png)

## 2. Create Analytics variables

To map the context data (sent in step 1), variables must first be created for the Analytics report suite. For more information about creating variables in Analytics, see [Conversion variables (eVars)](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/evar.html).

In this example, a conversion variable, **[!UICONTROL Evar2]**, has been created and named **[!UICONTROL Places POI Name]**. Additional variables will need to be created for each location variable you want to expose in reporting.

!["create an analytics variable"](/help/assets/aa-evar.png)

## 3. Create processing rules

This step is needed to map context data (step 1) to Analytics variables (step 2). For more information on creating processing rules, see [Processing rules overview](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/c-processing-rules/processing-rules.html).

In this example, a processing rule has been created to map the context data value **[!UICONTROL poi.name]** into **[!UICONTROL Places POI Name (eVar2)]**. Additional processing rules will need to be created for each location variable created.

!["create a processing rule"](/help/assets/aa-processing-rule.png)

## 4. Generate a report in Workspace

This step shows a basic report in Analytics Workspace to view the data collected in steps 1-3. For more information about how to use Analytics Workspace, see [Analytics Workspace overview](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html).

In this example, the report has the following settings:

* Metric - **[!UICONTROL Occurrences]**

* Dimension - **[!UICONTROL Action Name]**

  * Broken down by Dimension - **[!UICONTROL Places POI Name]**

!["create a report in workspace"](/help/assets/aa-workspace.png)
