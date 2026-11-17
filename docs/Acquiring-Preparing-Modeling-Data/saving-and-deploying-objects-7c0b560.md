<!-- loio7c0b560e2cb94eea86219d78d87f9623 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Saving and Deploying Objects

Save objects to the SAP Datasphere design-time repository, and then deploy your changes to the runtime.

This topic contains the following sections:

-   [Save an Object](saving-and-deploying-objects-7c0b560.md#loio7c0b560e2cb94eea86219d78d87f9623__section_save)
-   [Create a Copy of an Object](saving-and-deploying-objects-7c0b560.md#loio7c0b560e2cb94eea86219d78d87f9623__section_copy)
-   [Deploy an Object](saving-and-deploying-objects-7c0b560.md#loio7c0b560e2cb94eea86219d78d87f9623__section_deploy)
-   [Deployment Status](saving-and-deploying-objects-7c0b560.md#loio7c0b560e2cb94eea86219d78d87f9623__section_status)
-   [Debug View Deployment Issues with the View Analyzer](saving-and-deploying-objects-7c0b560.md#loio7c0b560e2cb94eea86219d78d87f9623__section_debug_deploy_views)
-   [Save Anyway and Deploy Anyway](saving-and-deploying-objects-7c0b560.md#loio7c0b560e2cb94eea86219d78d87f9623__section_save_anyway)
-   [Run-Time Database Unavailable](saving-and-deploying-objects-7c0b560.md#loio7c0b560e2cb94eea86219d78d87f9623__section_database_unavailable)



<a name="loio7c0b560e2cb94eea86219d78d87f9623__section_save"/>

## Save an Object

When you save an object, it is stored in the SAP Datasphere repository, which contains the design-time definitions of all your objects.

Design-time objects do not contain any data, but you can preview the data they will contain when they are deployed to the run-time environment \(see [Viewing Object Data](viewing-object-data-b338e4a.md)\). You can save an object even if it contains validation errors.

> ### Note:  
> Graphical views and other SAP Datasphere objects are stored in CSN format files, with a maximum file size of 25MB. If your view has many sources, many columns, or very complex logic, you may encounter issues when saving or transporting it. For information about simplifying your view structure or otherwise working around the size limit, see SAP Note [3768744](https://me.sap.com/notes/3768744).



<a name="loio7c0b560e2cb94eea86219d78d87f9623__section_copy"/>

## Create a Copy of an Object

You can create a copy of many types of objects by:

-   Selecting the object in the Repository Explorer and clicking *Duplicate*.
-   Opening the object in its editor and clicking *Save* \> *Save As*



<a name="loio7c0b560e2cb94eea86219d78d87f9623__section_deploy"/>

## Deploy an Object

All *Data Builder* objects must be deployed to be used productively. When you deploy an object, you create a run-time version for use in SAP Datasphere's underlying SAP HANA database.

When you deploy an object, SAP Datasphere will:

-   Compare the design-time and run-time versions and, if there are differences, deploy the design-time version to the runtime. It will change the object's status to *Deployed* and augment its version number.

    For more information, see [Reviewing and Restoring Object Versions](reviewing-and-restoring-object-versions-4f717cc.md)\).

-   Review the deployment status of all the objects in the selected object's lineage, and deploy any that do not already have a status of *Deployed* to ensure run-time consistency.

    For more information, see [Impact and Lineage Analysis](impact-and-lineage-analysis-9da4892.md)

    > ### Note:  
    > Multidimensional objects \(analytic models and views with a semantic usage of *Analytical Dataset*\) must be deployed to the SAP HANA database even if there are no changes to deploy, in order to trigger their lineage analysis. However, the SAP Datasphere design-time version number is not augmented in this case.
    > 
    > You can review all object deployments in the *Activities* list \(see [Monitor Object Changes with Activities](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/08e607c58e5343bd9c0287e7e22c452a.html "Monitor the changes that users perform on modeling objects (such as spaces and tables) as well as changes to the system configuration (such as roles and users).") :arrow_upper_right:\).


The following types of object are automatically deployed upon creation and immediately available in the run-time database:

-   Remote tables imported into the repository from a source system, database user schema or HDI container \(see [Importing Tables and Views from Sources](Acquiring-and-Preparing-Data-in-the-Data-Builder/importing-tables-and-views-from-sources-7c4acd3.md)\).
-   Tables created by importing data from a `*.csv` file \(see [Creating a Local Table from a CSV File](Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-from-a-csv-file-8bba251.md)\).

> ### Note:  
> If your space is locked because it has reached its storage capacity, then you are not allowed to deploy objects.



<a name="loio7c0b560e2cb94eea86219d78d87f9623__section_status"/>

## Deployment Status

The deployment status of an object is shown in its *Status* property, which can have the following values:

-   <span class="SAP-icons-V5"></span> \(Not Deployed\) - The object has never been deployed and exists only as a design-time artifact.
-   :clock3: - The object is deployed to the run-time database and its design-time and run-time versions are identical.
-   <span class="SAP-icons-V5"></span> \(Changes to Deploy\) - The design-time version of the object contains changes that need to be deployed to make them available in the run-time.
-   \(Design-Time Error\) - The design-time version of the object is invalid. You can save an object with design-time errors, but you cannot deploy it. To correct design-time errors, review each of the validation messages in the editor, make the necessary changes, and then save the object.
-   \(Run-Time Error\) - The run-time version of the object is invalid and can no longer be used. Run-time errors may be caused by changes in one or more of the object's sources \(see [Modifying Objects That Have Dependent Objects](modifying-objects-that-have-dependent-objects-f315863.md)\). To correct the errors, review each of the validation messages in the editor, make the necessary changes, and then save and deploy the object.



<a name="loio7c0b560e2cb94eea86219d78d87f9623__section_save_anyway"/>

## Save Anyway and Deploy Anyway

When you try to save or deploy your object, the *Validation Messages* dialog opens to allow you to review these messages. You can still save or deploy your object \(by clicking *Save Anyway* or *Deploy Anyway*\), but you should aim to review and resolve these impacts as soon as possible. For more information, see [Modifying Objects That Have Dependent Objects](modifying-objects-that-have-dependent-objects-f315863.md).



<a name="loio7c0b560e2cb94eea86219d78d87f9623__section_debug_deploy_views"/>

## Debug View Deployment Issues with the View Analyzer

If your view contains very complex calculations or subqueries, includes multiple unions of large views, or has a complicated or deep dependency tree, then you may encounter performance issues \(or even, very occasionally, out of memory errors\) when deploying.

In such situations, you may be able to improve deployment performance or resolve the errors by persisting one or more of your view's sources. We recommend that you use the *View Analyzer* and look at the peak memory usage and duration values to guide you in these decisions \(see [Exploring Views with View Analyzer](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/8921e5acf2ad4c8a98073edae4c214c7.html "Use the View Analyzer to explore graphical or SQL views and the entities they consume.") :arrow_upper_right:\).



<a name="loio7c0b560e2cb94eea86219d78d87f9623__section_database_unavailable"/>

## Run-Time Database Unavailable

The run-time database server might be unavailable under exceptional circumstances. In this case, a message strip is displayed informing you of the database status and the following features are disabled:

-   *Deploy*
-   *Share*
-   *Delete*
-   *Source Browser*
-   *Preview Data*
-   *Import CSV File*
-   *Validate SQL and Preview Data*
-   *Run* a flow

You can try to solve this issue by waiting a few minutes and refreshing your web browser. If the problem persists, [open a support ticket](https://launchpad.support.sap.com/#incident/solution).

