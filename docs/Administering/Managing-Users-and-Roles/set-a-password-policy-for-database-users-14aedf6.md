<!-- loio14aedf6cecce474b93b2d5187662a090 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Set a Password Policy for Database Users

You can set a password policy for database users with complexity requirements, expiration periods, and reuse restrictions.



<a name="loio14aedf6cecce474b93b2d5187662a090__prereq_mpq_cqd_bgc"/>

## Prerequisites

To set a password policy for database user passwords, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Configuration* area in the *System* tool.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Application RolesStandard Roles Delivered with SAP Datasphere](standard-application-rolesstandard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loio14aedf6cecce474b93b2d5187662a090__context_y2d_1dr_1tb"/>

## Context

Users with a space administrator role can create database users in their spaces to allow the connection of ETL tools to write to and read from Open SQL schemas attached to the space schema \(see [Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/3de55a78a4614deda589633baea28645.html "Users with a space administrator role can create database users to read data exposed by the space and to write data to Open SQL schemas attached to space, providing a secure method for exchanging data with the space via ODBC access to the run-time SAP HANA Cloud database.") :arrow_upper_right:\).



<a name="loio14aedf6cecce474b93b2d5187662a090__steps_t4h_lbr_1tb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Security*.

2.  In the *Password Policy Configuration* section, complete the properties as appropriate and click *Save*:


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
    
    Number of Days to Expiration
    
    </td>
    <td valign="top">
    
    Enter the number of days that database user passwords are valid before they expire. After this period, the user will be prompted to set a new password.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Number of Last Used Passwords That Cannot Be Reused
    
    </td>
    <td valign="top">
    
    Enter the number of last used passwords that users are not allowed to reuse when changing their current password.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Password Change Required on First Logon
    
    </td>
    <td valign="top">
    
    Specify whether users have to change their initial passwords immediately the first time they log on.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Minimum Password Length
    
    </td>
    <td valign="top">
    
    Enter the minimum number of characters that the password must contain.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Minimum Number of Uppercase Letters
    
    </td>
    <td valign="top">
    
    Enter the minimum number of uppercase letters that the password must contain.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Minimum Number of Lowercase Letters
    
    </td>
    <td valign="top">
    
    Enter the minimum number of lowercase letters that the password must contain.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Minimum Number of Digits
    
    </td>
    <td valign="top">
    
    Enter the minimum number of digits that the password must contain.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Minimum Number of Special Characters
    
    </td>
    <td valign="top">
    
    Enter the minimum number of special characters that the password must contain.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > The *Number of Days to Expiration* and *Password Change Required on First Logon* settings apply only to database users with the *Enable Password Lifetime* option selected in their configuration dialog. If a user does not log on with their initial password during this period, they will be deactivated until their password is reset.


