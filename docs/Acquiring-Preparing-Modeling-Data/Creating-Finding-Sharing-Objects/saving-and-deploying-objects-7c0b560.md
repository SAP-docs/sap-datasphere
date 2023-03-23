<!-- loio7c0b560e2cb94eea86219d78d87f9623 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Saving and Deploying Objects

When you save an object, it is stored in the SAP Datasphere repository, which contains the design-time definitions of all your objects. When you deploy an object, you are creating a run-time version for use in the SAP Datasphere database.

This topic contains the following sections:

-   [Create a Copy of an Object](saving-and-deploying-objects-7c0b560.md#loio7c0b560e2cb94eea86219d78d87f9623__section_create_a_copy)
-   [Preview Data](saving-and-deploying-objects-7c0b560.md#loio7c0b560e2cb94eea86219d78d87f9623__section_preview_data)
-   [Deploy Objects](saving-and-deploying-objects-7c0b560.md#loio7c0b560e2cb94eea86219d78d87f9623__section_deploy_objects)
-   [Save Anyway and Deploy Anyway](saving-and-deploying-objects-7c0b560.md#loio7c0b560e2cb94eea86219d78d87f9623__section_save_anyway)
-   [Run-Time Database Unavailable](saving-and-deploying-objects-7c0b560.md#loio7c0b560e2cb94eea86219d78d87f9623__section_database_unavailable)



<a name="loio7c0b560e2cb94eea86219d78d87f9623__section_create_a_copy"/>

## Create a Copy of an Object

You can create a copy of most objects by:

-   Selecting the object in the Repository Explorer and clicking *Duplicate*.
-   Opening the object in its editor and clicking *Save* \> *Save As*



<a name="loio7c0b560e2cb94eea86219d78d87f9623__section_preview_data"/>

## Preview Data

Design-time objects do not contain any data, but you can preview the data they will contain when they are deployed to the run-time environment \(see [Viewing or Previewing Data in Data Builder Objects](../Acquiring-and-Preparing-Data-in-the-Data-Builder/viewing-or-previewing-data-in-data-builder-objects-b338e4a.md)\). You can save an object even if it contains validation errors.



<a name="loio7c0b560e2cb94eea86219d78d87f9623__section_deploy_objects"/>

## Deploy Objects

> ### Note:  
> All Data Builder objects and data access controls can be saved and deployed. In the Business Builder, only perspectives are saved and deployed. Other Business Builder objects do not need to be deployed.

The current status of an object is shown in its *Status* property, which can have the following values:

-   <span class="SAP-icons"></span> \(Not Deployed\) - The object has never been deployed and exists only as a design-time artifact.
-   :clock3: - The object is deployed to the run-time database and its design-time and run-time versions are identical.
-   <span class="SAP-icons"></span> \(Changes to Deploy\) - The design-time version of the object contains changes that need to be deployed to make them available in the run-time.
-   \(Design-Time Error\) - The design-time version of the object is invalid. You can save an object with design-time errors, but you cannot deploy it. To correct design-time errors, review each of the validation messages in the editor, make the necessary changes, and then save the object.
-   \(Run-Time Error\) - The run-time version of the object is invalid and can no longer be used. Run-time errors may be caused by changes in one or more of the object's sources \(see [Modifying Objects That Have Dependent Objects](modifying-objects-that-have-dependent-objects-f315863.md)\). To correct the errors, review each of the validation messages in the editor, make the necessary changes, and then save and deploy the object.

When you deploy a table or view, you create a run-time version, which can be used by other run-time objects.

> ### Note:  
> If your space is locked because it has reached its storage capacity, then you will not be allowed to deploy objects. Contact your DW Space Administrator.

The following types of object are automatically deployed upon creation and immediately available in the run-time:

-   Remote tables imported into the repository from a source system, database user schema or HDI container \(see [Importing Tables and Views from Sources](../Acquiring-and-Preparing-Data-in-the-Data-Builder/importing-tables-and-views-from-sources-7c4acd3.md)\).
-   Tables created by importing data from a `*.csv` file \(see [Creating a Local Table from a CSV File](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-from-a-csv-file-8bba251.md)\).



<a name="loio7c0b560e2cb94eea86219d78d87f9623__section_save_anyway"/>

## Save Anyway and Deploy Anyway

If other objects use your object as a source or otherwise depend on your object, then any changes you make to your object may impact \(change or break\) these other objects. If changes you have made to an object will impact its dependent objects, then validation messages are generated to warn you of these impacts.

When you try to save or deploy your object, the *Validation Messages* dialog opens to allow you to review these messages. You can still save or deploy your object \(by clicking *Save Anyway* or *Deploy Anyway*\), but you should aim to review and resolve these impacts as soon as possible. For more information, see [Modifying Objects That Have Dependent Objects](modifying-objects-that-have-dependent-objects-f315863.md).



<a name="loio7c0b560e2cb94eea86219d78d87f9623__section_database_unavailable"/>

## Run-Time Database Unavailable

The run-time database server might be unavailable under exceptional circumstances. In this case, a message strip is displayed informing you of the database status and the following features are disabled:

-   *Deploy*
-   *Share*
-   *Delete*
-   *Sources* Browser
-   *Preview Data*
-   *Import CSV File*
-   *Validate SQL and Preview Data*
-   *Run* a data flow

You can solve this problem by waiting a few minutes and refreshing your web browser. If the problem persists, [open a support ticket](https://launchpad.support.sap.com/#incident/solution).

