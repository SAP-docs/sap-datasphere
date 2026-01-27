<!-- loio03191f36e9144b2aaa47b8c9eea039c1 -->

# Partitioning Local Tables

Create partitions for your local table to break your data down into smaller tables, and better manage tables with a large volume of data.



<a name="loio03191f36e9144b2aaa47b8c9eea039c1__section_rzp_lhq_hhc"/>

## Prerequisites

To work with partitions in a standard space \(with **SAP HANA Database \(Disk and In-Memory\)** storage\), you must meet the following prerequisites:

-   To access SAP Datasphere, you must have *Data Warehouse General* \(-R------\) -
-   To create, update, or schedule partitions, you must have a scoped role that grants you access to a space with the following privileges: *Data Warehouse Data Integration* \(--UE----\) – The *DW Integrator* role template, for example, grants this privilege. Note that with this privilege, you will be able to create partitions both on empty tables and on tables that already contain data.
-   To create, see and monitor existing partitions, you must have a scoped role that grants you access to a space with the following privileges: *Data Warehouse Data Builder* \(-RU---\) – The *DW Modeler* role template, for example, grants this privilege. Note that with this privilege, you will be able to create partition on tables that don't have data only. To create partitions on tables that already contain data, you must add the *Data Warehouse Data Integration* permission.

    For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:.


To create partitions for local tables \(file\) stored in a file space \(with **SAP HANA Data Lake Files** storage\), see [Creating a Local Table \(File\)](creating-a-local-table-file-d21881b.md).



<a name="loio03191f36e9144b2aaa47b8c9eea039c1__section_dvb_fjh_1fc"/>

## Introduction to Partitioning

Working with a large volume of data can cause memory shortages and take many system resources. One solution can be to use partitions: You create partitions based on one or several columns of your table to break your data down into smaller and more manageable parts \(consider [SAP HANA recommendations for partitioning](https://help.sap.com/docs/hana-cloud-database/sap-hana-cloud-sap-hana-database-administration-guide/creating-effective-partitioning-scheme)\). When a table is partitioned, the split is done in such a way that each partition contains a different set of rows of the table, depending on the partition type you have chosen for your data load:

-   *Range*: You select one column of your table that will serve for the partitioning. The table will then be split into several partitions according to the different ranges you have defined. For example, you have set the column Year as the column to serve the partition. This column contains data from the year 2000 to the year 2025. You have defined the partition ranges as follows:

    -   Range 1: From the year 2000 to the year 2005
    -   Range 2: From the year 2006 to the year 2010
    -   Range 3: From the year 2011 to the Year 2015
    -   Range 4: From the year 2016 to the Year 2020
    -   Range 5: From the year 2021 to the Year 2025

    You will get 5 partitions, but they can contain different amounts of data.

-   *Hash*: You select one or more columns of your table that will serve for the partitioning. The table will then be split into the number of partitions you have defined. In our example above, if you have set 15 partitions on the Year column, you will have 15 partitions that will contain the same amount of data.

> ### Restriction:  
> -   Supported data types include:
> 
>     -   String
>     -   Integer, Integer 64, Decimal, hana.SMALLINT, hana.TINYINT
>     -   Date, DateTime, Timestamp
>     -   Binary
> 
>     For more information, see [Partitioning Limits](https://help.sap.com/docs/HANA_CLOUD_DATABASE/f9c5015e72e04fffa14d7d4f7267d897/8dd866a688ec4914a074727a2c800142.html) in the *SAP HANA Cloud, SAP HANA Database* documentation.



<a name="loio03191f36e9144b2aaa47b8c9eea039c1__section_c5k_hjh_1fc"/>

## Procedure

To create partitions for the local table:

1.  Go to the *Data Builder*
2.  Create your local table \(for more information, see [Creating a Local Table](creating-a-local-table-2509fe4.md)\)
3.  Go to the *Partitions* tab.
4.  Click *Define Partitions*, select the *Partition Type* and enter its definition:
    -   *Range* Partition:


        <table>
        <tr>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Column*
        
        </td>
        <td valign="top">
        
        Select the column from which the partition will be defined.

        > ### Note:  
        > If you have defined key columns, you can select only a key column. If you have no key columns defined, all columns with compatible data types can be selected. Note that you won’t be able to define a key column later, until the partitions are in place.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Partitions*
        
        </td>
        <td valign="top">
        
        Create the number of desired partitions by entering a range for each of them. Note that ranges can't overlap.

        > ### Note:  
        > If you have data outside the defined partition ranges, an *Others* partition will be created to store this data.


        
        </td>
        </tr>
        </table>
        
    -   *Hash* partition:


        <table>
        <tr>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Columns*
        
        </td>
        <td valign="top">
        
        Select one or several columns from which the partition will be defined.

        > ### Note:  
        > If your table have got key columns, only these columns will be displayed for selection. If you have no key columns defined, all columns with compatible data types can be selected. Note that you won’t be able to define a key column later, until the partitions are in place.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Number of Hash Partitions*
        
        </td>
        <td valign="top">
        
        Create the number of desired partitions.

        > ### Note:  
        > The default value is 10 and the maximum value is 9999.


        
        </td>
        </tr>
        </table>
        
        > ### Note:  
        > If your table was created during a data product installation, automatic hash partitioning will happen for entities of large tables. Based on key columns defined for this table, data will be partitioned into 8 partitions.


5.  Save the partition definition and deploy the table.



<a name="loio03191f36e9144b2aaa47b8c9eea039c1__section_a4y_s3q_hhc"/>

## Deployment and Partitioning

After you have created the partition definition, you must deploy the local table to create the partitions. The deployment will happen depending on whether your table contains data or not.

> ### Note:  
> Once deployed, you won’t be able to change the data type of the primary key that has been used for partitioning.



### Case 1: Your Table Does Not Contain Data

If your table does not contain data and was not deployed before you created the partition, the deployment will run immediately. You can still change or delete partitions until you add data to your table.



### Case 2: Your Table Contains Data

Partitioning large tables can be time- and resource-consuming. To ensure efficient deployment, the partitioning process must not block the deployment of the table or its dependent objects. Therefore, partitioning will be run as a separate task after the table has been successfully deployed.

Once your partition definition is saved and you click on *Deploy*, you are invited to decide how the partition creation task will happen:

-   *Automatically After Deployment*: Once the deployment is complete, the partition creation task will start automatically.
-   *Automatically at a Scheduled Time*: You define a timestamp when the partitions must be created. Once deployment is complete, the partition creation task will start automatically at the scheduled timestamp.
-   *Manually at Later Time* : Once the deployment is complete, you will be able to create the partitions when you want.

    > ### Note:  
    > After the deployment is complete, you can see in the validation message area that the partitions can be created. From this validation message, you can click *Create Partitions* to get the creation popup. Once again you can either create the partitions immediately or schedule the partition creation.


> ### Caution:  
> If your local table is consumed by flows, you might need to take actions on running flows to allow the partition creation:
> 
> -   You must pause any replication flow runs that consume this table.
> -   You must wait until the running flows are complete.

Note that defining partitions on a table that already contains data can be done only once. If later on you want to change the partition definition, data will have to be deleted first.

