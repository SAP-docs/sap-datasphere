<!-- loio1097a470be40432e89f91288bdc14378 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Database User Group

Users with an administrator role can create database user groups in SAP Datasphere to allow users to work in a sandboxed area in the underlying SAP HANA Cloud database, unattached to any space. These users can transfer an existing data warehouse implementation into the SAP Datasphere database or do any other work in SAP HANA Cloud and then make it available to one or more spaces as appropriate.



<a name="loio1097a470be40432e89f91288bdc14378__prereq_yx4_t2p_hfc"/>

## Prerequisites

To create database user groups, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Administration* and *Configuration* areas in the *System* tool.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



## Context

When creating a database user group, an administrator is also created. This administrator can create other users, schemas, and roles using SAP Datasphere stored procedures. The administrator and their users can create data entities \(DDL\) and ingest data \(DML\) directly into their schemas and prepare them for consumption by spaces.

For detailed information about user groups, see [User Groups](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-database-administration-with-sap-hana-cockpit/user-groups) in the *SAP HANA Cloud* documentation.

> ### Note:  
> Users with the DW Space Administrator role can create database users, which are associated with their space \(see [Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/3de55a78a4614deda589633baea28645.html "Users with a space administrator role can create database users to read data exposed by the space and to write data to Open SQL schemas attached to space, providing a secure method for exchanging data with the space via ODBC access to the run-time SAP HANA Cloud database.") :arrow_upper_right:\).



<a name="loio1097a470be40432e89f91288bdc14378__steps_azw_fmb_rwb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Database Access* \> *Database User Groups*.

2.  On the *Database User Group* page, click *Create*.

3.  Enter a suffix for your database user group and click *Create*.

    The group is created and the connection details and administrator credentials are displayed.

    If you want to work with the SAP HANA database explorer, you will need to enter your password to grant the explorer access to the database user group schema. When connecting to SAP HANA Cloud with other tools, users will need the following properties:

    -   Database Group Administrator \(name and password\)
    -   Host Name
    -   Port

4.  Click *Close* to close the dialog.


