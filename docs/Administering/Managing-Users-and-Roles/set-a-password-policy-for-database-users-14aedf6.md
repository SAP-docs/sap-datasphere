<!-- loio14aedf6cecce474b93b2d5187662a090 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Set a Password Policy for Database Users

Users with an administrator role can set a password policy to cause database user passwords to expire after a specified number of days.



<a name="loio14aedf6cecce474b93b2d5187662a090__prereq_mpq_cqd_bgc"/>

## Prerequisites

To set a password policy for database user passwords, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Administration* and *Configuration* areas in the *System* tool.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loio14aedf6cecce474b93b2d5187662a090__context_y2d_1dr_1tb"/>

## Context

Users with a space administrator role can create database users in their spaces to allow the connection of ETL tools to write to and read from Open SQL schemas attached to the space schema \(see [Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/3de55a78a4614deda589633baea28645.html "Users with a space administrator role can create database users to read data exposed by the space and to write data to Open SQL schemas attached to space, providing a secure method for exchanging data with the space via ODBC access to the run-time SAP HANA Cloud database.") :arrow_upper_right:\).



<a name="loio14aedf6cecce474b93b2d5187662a090__steps_t4h_lbr_1tb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Security*.

2.  In the *Password Policy Configuration* section, enter the number of days after which a database user's password will expire.

    After this period, the user will be prompted to set a new password.

    > ### Note:  
    > The password policy applies only to database users where the *Enable Password Policy* property is selected, for both existing and new users. If a user does not log on with their initial password during this period, they will be deactivated until their password is reset.


