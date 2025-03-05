<!-- loio2a6bc3f6d79b4c39a01b6d58d043fbaf -->

# Acquiring and Preparing Data in the Object Store

Users with a modeler role can load large quantities of data via replication flows and store them inexpensively in file spaces in the object store. You can prepare the data using transformation flows and then share data to a standard space to be used as a source of flows, views, and analytic models.

This topic contains the following sections:

-   [Introduction to the SAP Datasphere Object Store](acquiring-and-preparing-data-in-the-object-store-2a6bc3f.md#loio2a6bc3f6d79b4c39a01b6d58d043fbaf__section_intro_to_big_data)
-   [Create a File Space in the Object Store](acquiring-and-preparing-data-in-the-object-store-2a6bc3f.md#loio2a6bc3f6d79b4c39a01b6d58d043fbaf__section_create_file_space)
-   [Load Data with Replication Flows](acquiring-and-preparing-data-in-the-object-store-2a6bc3f.md#loio2a6bc3f6d79b4c39a01b6d58d043fbaf__section_load_big_data)
-   [Prepare Data with Apache Spark Transformation Flows](acquiring-and-preparing-data-in-the-object-store-2a6bc3f.md#loio2a6bc3f6d79b4c39a01b6d58d043fbaf__section_prepare_big_data)
-   [Share Data to Standard Spaces](acquiring-and-preparing-data-in-the-object-store-2a6bc3f.md#loio2a6bc3f6d79b4c39a01b6d58d043fbaf__section_share_big_data)



<a name="loio2a6bc3f6d79b4c39a01b6d58d043fbaf__section_intro_to_big_data"/>

## Introduction to the SAP Datasphere Object Store

> ### Note:  
> The object store is not enabled by default in SAP Datasphere tenants. To enable it in your tenant, see SAP note [3525760](https://me.sap.com/notes/3525760).
> 
> For additional information on working with data in the object store, see SAP Note [3538038](https://me.sap.com/notes/3538038).
> 
> The object store cannot be enabled in SAP Datasphere tenants provisioned prior to version 2021.03. To request the migration of your tenant, see SAP note [3268282](https://me.sap.com/notes/3268282).

The object store provides an inbound layer for staging large quantities of data in a cost-effective object store. Users with a modeler role can use replication flows to replicate data to local tables \(file\) and you can optionally further prepare the data with Apache Spark transformation flows. You can then share the tables to standard spaces, where they can be used as sources for flows, views, and analytic models.![](images/BigData_Overview_09644c8.png)



<a name="loio2a6bc3f6d79b4c39a01b6d58d043fbaf__section_create_file_space"/>

## Create a File Space in the Object Store

A user with an administrator role can create a space with SAP HANA data lake files storage in the object store. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area \(see [Create a File Space to Load Data in the Object Store](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/947444683e524cfd9169d7671b72ba0c.html "Create a space with SAP HANA data lake files storage in the object store, allocate compute resources and assign one or more users to allow them to start acquiring and preparing data. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area.") :arrow_upper_right:\).

> ### Note:  
> You cannot create views, data flows, data access controls, analytic models, intelligent lookups, E/R models or use the *Business Builder* in a file space. You cannot import or export objects via CSN/JSON files and you cannot import CSV files, entities, remote tables or currency conversion tables.



<a name="loio2a6bc3f6d79b4c39a01b6d58d043fbaf__section_load_big_data"/>

## Load Data with Replication Flows

Users with a modeler role can use replication flows to load data in local tables \(file\) that are stored in a file space \(see [SAP Datasphere Targets](sap-datasphere-targets-12c45eb.md)\). A replication flow writes data files to the inbound buffer \(specific folder in file storage\) of a target local table \(File\). To process data updates from this inbound buffer to the local table \(File\), and therefore make data visible, a merge task has to run via a task chain \(see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md)\). You can monitor the buffer merge status using the *Local Tables \(File\)* monitor \(See [Monitoring Local Tables (File)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/6b2d0073a8684ee6a59d6f47d00ec895.html "Monitor your local tables (file). Check how and when they were last updated and if new data has still to be merged.") :arrow_upper_right:\).



<a name="loio2a6bc3f6d79b4c39a01b6d58d043fbaf__section_prepare_big_data"/>

## Prepare Data with Apache Spark Transformation Flows

Users with a modeler role can use Apache Spark transformation flows to clean and otherwise prepare data in a file space \(see [Creating a Transformation Flow in a File Space](creating-a-transformation-flow-in-a-file-space-b917baf.md)\). Transformation flows can take one or more local tables \(file\) as sources, combine them, filter data, add or remove columns, and perform other transformations and output the result to another local table \(file\) \(see [Creating a Local Table \(File\)](creating-a-local-table-file-d21881b.md)\).



<a name="loio2a6bc3f6d79b4c39a01b6d58d043fbaf__section_share_big_data"/>

## Share Data to Standard Spaces

Users with a modeler role can share local tables \(file\) to standard spaces to allow the data to be used as a source for flows, views, and analytic models \(see [Sharing Entities and Task Chains to Other Spaces](../Creating-Finding-Sharing-Objects/sharing-entities-and-task-chains-to-other-spaces-64b318f.md)\).

