<!-- loioc28145bcb76c4415a1ec6265dd2a4c11 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create a Database Analysis User to Debug Database Issues

Database analysis users are SAP HANA Cloud database users who have read-only access to all space schemas, and all their activities are recorded in audit logs. You create a database user to monitor, analyze, trace, or debug your SAP Datasphere database, and resolve a specific database issue.

This topic contains the following sections:

-   [Prerequisites](create-a-database-analysis-user-to-debug-database-issues-c28145b.md#loioc28145bcb76c4415a1ec6265dd2a4c11__section_prereq)
-   [Introduction to Database Analysis Users](create-a-database-analysis-user-to-debug-database-issues-c28145b.md#loioc28145bcb76c4415a1ec6265dd2a4c11__section_intro)
-   [Create a Database Analysis User with Certificate-Based Authentication](create-a-database-analysis-user-to-debug-database-issues-c28145b.md#loioc28145bcb76c4415a1ec6265dd2a4c11__section_create_dbauser_certificate)
-   [Create a Database Analysis User with Password-Based Authentication](create-a-database-analysis-user-to-debug-database-issues-c28145b.md#loioc28145bcb76c4415a1ec6265dd2a4c11__section_create_dbauser_password)
-   [Switch Database Analysis User Authentication from Password to Certificate-Based](create-a-database-analysis-user-to-debug-database-issues-c28145b.md#loioc28145bcb76c4415a1ec6265dd2a4c11__section_switch_to_certificate_dbauser)
-   [Reactivate a Database Analysis User](create-a-database-analysis-user-to-debug-database-issues-c28145b.md#loioc28145bcb76c4415a1ec6265dd2a4c11__section_reactivate_dbauser)
-   [Unlock a Database Analysis User](create-a-database-analysis-user-to-debug-database-issues-c28145b.md#loioc28145bcb76c4415a1ec6265dd2a4c11__section_unlock_dbauser)
-   [Extend a Database Analysis User](create-a-database-analysis-user-to-debug-database-issues-c28145b.md#loioc28145bcb76c4415a1ec6265dd2a4c11__section_extend_dbauser)
-   [Delete a Database Analysis User](create-a-database-analysis-user-to-debug-database-issues-c28145b.md#loioc28145bcb76c4415a1ec6265dd2a4c11__section_delete_dbauser)



<a name="loioc28145bcb76c4415a1ec6265dd2a4c11__section_prereq"/>

## Prerequisites

To create a database user to monitor, analyze, trace, or debug your SAP Datasphere database, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Configuration* area in the *System* tool.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loioc28145bcb76c4415a1ec6265dd2a4c11__section_intro"/>

## Introduction to Database Analysis Users

You should create a database analysis user only when necessary to investigate a specific database issue and only for a limited period. Because this user can access all SAP HANA Cloud monitoring views and SAP Datasphere data across all spaces, including sensitive information, you should delete it immediately after the issue is resolved.

If further access is required, you can reactivate, unlock, or extend the user as needed.

Database analysis users can have one of the following statuses:


<table>
<tr>
<th valign="top">

Status

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Active*

</td>
<td valign="top">

The database analysis user is active and can be used.

</td>
</tr>
<tr>
<td valign="top">

*Deactivated*

</td>
<td valign="top">

The database analysis user has been deactivated because its audit logs have exceeded the disk storage threshold.

</td>
</tr>
<tr>
<td valign="top">

*Locked*

</td>
<td valign="top">

The database analysis user has been locked after too many failed login attempts. 

</td>
</tr>
<tr>
<td valign="top">

*Expired*

</td>
<td valign="top">

The database analysis user has passed the expiration date that you've set when creating it.

</td>
</tr>
</table>



<a name="loioc28145bcb76c4415a1ec6265dd2a4c11__section_create_dbauser_certificate"/>

## Create a Database Analysis User with Certificate-Based Authentication

You can create a database analysis user with certificate-based authentication provided that a X.509 root certificate \(root CA\) has been uploaded for the tenant by a user with an administrator role \(see [Manage Certificates](Preparing-Connectivity/manage-certificates-46f5467.md)\), who will be able to query the SAP HANA Cloud database using SAP HANA Database Explorer.

Any tool that supports X.509 client certificate authentication can connect using a certificate-based database analysis user.

> ### Note:  
> The SAP HANA Cockpit does not support certificate-based authentication. To use the SAP HANA Cockpit, create a database analysis user with password-based authentication instead.

1.  In the side navigation area, select <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Database Access* \> *Database Analysis Users*.
2.  Click *Create* and complete the following properties in the *Create Database Analysis User* dialog that opens:


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
    
    Database Analysis User Name Suffix
    
    </td>
    <td valign="top">
    
    Enter the suffix, which is used to create the full name of the user. Can contain a maximum of 31 uppercase letters or numbers and must not contain spaces or special characters other than `_` \(underscore\). See [Rules for Technical Names](Creating-Spaces-and-Allocating-Storage/rules-for-technical-names-982f9a3.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Space Schema Access
    
    </td>
    <td valign="top">
    
    Select only if you need to grant the user access to space data.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Database analysis user expires in
    
    </td>
    <td valign="top">
    
    Select the number of days after which the user will be deactivated. We strongly recommend creating this user with an automatic expiration date.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication Type
    
    </td>
    <td valign="top">
    
    Select *Certificate-Based Authentication*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    X.509 Certificate
    
    </td>
    <td valign="top">
    
    Upload a X.509 client certificate in PEM format. Supported file extensions are: .pem and .crt. Once the certificate has been uploaded, its subject and issuer distinguished names are displayed.

    > ### Note:  
    > The certificate will work if a X.509 root certificate \(root CA\) has been uploaded for the tenant by a user with an administrator role \(see [Manage Certificates](Preparing-Connectivity/manage-certificates-46f5467.md)\).

    > ### Note:  
    > Once you've uploaded a certificate for the database analysis user:
    > 
    > -   You cannot switch to password-based authentication.
    > -   You cannot upload another certificate later for this user. Also, you cannot use the same certificate for several database analysis users.

    Client certificates have an expiry date. If your certificate expires, contact the administrator who issued it to obtain a replacement.
    
    </td>
    </tr>
    </table>
    
3.  Click *Create* to create the user.

    The *Database Analysis User Details* dialog displays the host name and port.

4.  Note these for later use and click *Close*.
5.  Select your user in the list and then click the following button and enter your credentials:

    -   *Open Database Explorer* - Open an SQL Console for the SAP Datasphere run-time database. 

        For more information, see [Getting Started With the SAP HANA Database Explorer](https://help.sap.com/docs/SAP_HANA_COCKPIT/e8d0ddfb84094942a9f90288cd6c05d3/7fa981c8f1b44196b243faeb4afb5793.html)\).


    A database analysis user can run a procedure in Database Explorer to stop running statements. For more information, see [Stop a Running Statement With a Database Analysis User](stop-a-running-statement-with-a-database-analysis-user-0cf11ed.md).

    > ### Note:  
    > All actions of the database analysis user are logged in the `ANALYSIS_AUDIT_LOG` view, which is stored in the space that has been assigned to store audit logs \(see [Logging Read and Change Actions for Audit](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/266553976e1c4db9aaa28a75e2308b77.html "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who performed which action at which point in time.") :arrow_upper_right:\).
    > 
    > Audit logs can consume a large quantity of GB of disk in your SAP Datasphere tenant database. The audit log entries for database analysis users are kept for 180 days, after which they are automatically deleted. You can also manually delete the audit logs to free up disk space \(see [Monitor Read and Change Actions with Audit Logs](monitor-read-and-change-actions-with-audit-logs-110404a.md)\). Also, a database analysis user can be automatically deactivated due to a large amount of disk storage consumed by audit logs \(see [Create a Database Analysis User to Debug Database Issues](create-a-database-analysis-user-to-debug-database-issues-c28145b.md)\).




<a name="loioc28145bcb76c4415a1ec6265dd2a4c11__section_create_dbauser_password"/>

## Create a Database Analysis User with Password-Based Authentication

You can create a database analysis user with password-based authentication, who will be able to query the SAP HANA Cloud database using the SAP HANA Cockpit or SAP HANA Database Explorer.

1.  In the side navigation area, select <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Database Access* \> *Database Analysis Users*.
2.  Click *Create* and enter the following properties in the dialog:


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
    
    Database Analysis User Name Suffix
    
    </td>
    <td valign="top">
    
    Enter the suffix, which is used to create the full name of the user. Can contain a maximum of 31 uppercase letters or numbers and must not contain spaces or special characters other than `_` \(underscore\). See [Rules for Technical Names](Creating-Spaces-and-Allocating-Storage/rules-for-technical-names-982f9a3.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Space Schema Access
    
    </td>
    <td valign="top">
    
    Select only if you need to grant the user access to space data.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Database analysis user expires in
    
    </td>
    <td valign="top">
    
    Select the number of days after which the user will be deactivated. We strongly recommend creating this user with an automatic expiration date.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication Type
    
    </td>
    <td valign="top">
    
    \[Default\] *Password-Based Authentication*.
    
    </td>
    </tr>
    </table>
    
3.  Click *Create* to create the user.

    The *Database Analysis User Details* dialog displays the host name and port, as well as the user password.

4.  To copy the password for your user:
    1.  Click *Show*, which displays the password and enable the *Copy Password* button.
    2.  Click *Copy Password*.

5.  Copy also the following properties: Database Analysis User Name, Host Name, and Port.
6.  Click *Close*.
7.  Select your user in the list and then click one of the following and enter your credentials:
    -   *Open SAP HANA Cockpit* - Open the *Database Overview* \> *Monitoring* page for the SAP Datasphere run-time database, which offers various monitoring tools. 

        For more information, see [Using the Database Overview Page to Manage a Database](https://help.sap.com/docs/HANA_CLOUD/9630e508caef4578b34db22014998dba/1115707b7dc846c99c3b2dac97520cf7.html)\).

    -   *Open Database Explorer* - Open an SQL Console for the SAP Datasphere run-time database. 

        For more information, see [Getting Started With the SAP HANA Database Explorer](https://help.sap.com/docs/SAP_HANA_COCKPIT/e8d0ddfb84094942a9f90288cd6c05d3/7fa981c8f1b44196b243faeb4afb5793.html)\).

        A database analysis user can run a procedure in Database Explorer to stop running statements. For more information, see [Stop a Running Statement With a Database Analysis User](stop-a-running-statement-with-a-database-analysis-user-0cf11ed.md).

        > ### Note:  
        > All actions of the database analysis user are logged in the `ANALYSIS_AUDIT_LOG` view, which is stored in the space that has been assigned to store audit logs \(see [Logging Read and Change Actions for Audit](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/266553976e1c4db9aaa28a75e2308b77.html "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who performed which action at which point in time.") :arrow_upper_right:\).
        > 
        > Audit logs can consume a large quantity of GB of disk in your SAP Datasphere tenant database. The audit log entries for database analysis users are kept for 180 days, after which they are automatically deleted. You can also manually delete the audit logs to free up disk space \(see [Monitor Read and Change Actions with Audit Logs](monitor-read-and-change-actions-with-audit-logs-110404a.md)\). Also, a database analysis user can be automatically deactivated due to a large amount of disk storage consumed by audit logs \(see [Create a Database Analysis User to Debug Database Issues](create-a-database-analysis-user-to-debug-database-issues-c28145b.md)\).





<a name="loioc28145bcb76c4415a1ec6265dd2a4c11__section_switch_to_certificate_dbauser"/>

## Switch Database Analysis User Authentication from Password to Certificate-Based

You can change a database analysis user's authentication from password-based to certificate-based, but you cannot change it back from certificate-based to password-based.

1.  In the side navigation area, select <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Database Access* \> *Database Analysis Users*.
2.  Click the <span class="FPA-icons-V3"></span> button for your user to open the *Database Analysis User Details* dialog.
3.  In the *Switch to X.509 Authentication* section, upload a X.509 client certificate in PEM format \(supported file extensions are: .pem and .crt\). The certificate's subject and issuer distinguished names are displayed.

    > ### Note:  
    > The certificate will work if a X.509 root certificate \(root CA\) has been uploaded for the tenant by a user with an administrator role \(see [Manage Certificates](Preparing-Connectivity/manage-certificates-46f5467.md)\).

    > ### Note:  
    > Once you select a certificate, you cannot switch to password-based authentication.

4.  Click *Apply*.



<a name="loioc28145bcb76c4415a1ec6265dd2a4c11__section_reactivate_dbauser"/>

## Reactivate a Database Analysis User

A database analysis user is deactivated and its status set to *Deactivated* because its audit logs have exceeded the disk storage threshold.

If the total size of all audit logs in the tenant has reached more than 40% of the tenant disk storage, the system automatically deactivates any analysis database users - and locks any spaces - whose audit logs consume more than 30% of the total audit log size.

You can reactivate a deactivated database analysis user by deleting its audit log entries so that they fall below the threshold \(see [Monitor Read and Change Actions with Audit Logs](monitor-read-and-change-actions-with-audit-logs-110404a.md)\). The database analysis user will be automatically reactivated after a few minutes.



<a name="loioc28145bcb76c4415a1ec6265dd2a4c11__section_unlock_dbauser"/>

## Unlock a Database Analysis User

After too many failed login attempts, a database analysis user is locked and its status set to *Locked*.

You can unlock a locked database analysis user by requesting a new password for it.

1.  In the side navigation area, select <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Database Access* \> *Database Analysis Users*.
2.  Click the icon next to the *Locked* status of the database analysis user.
3.  In the dialog box that opens, click *Request New Password*.

    A new password is automatically generated.




<a name="loioc28145bcb76c4415a1ec6265dd2a4c11__section_extend_dbauser"/>

## Extend a Database Analysis User

If the expiration date of an analysis database user has been reached, the user is automatically deactivated and its status set to *Expired*.

You can extend the validity period of an expired database analysis user.

1.  In the side navigation area, select <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Database Access* \> *Database Analysis Users*.
2.  Click the icon next to the *Expired* status of the analysis database user.
3.  In the dialog box that opens, select the number of days after which the user will expire and click *Reactivate Analysis User*.



<a name="loioc28145bcb76c4415a1ec6265dd2a4c11__section_delete_dbauser"/>

## Delete a Database Analysis User

Delete your database analysis user immediately after the issue is resolved to avoid misuse of sensitive data.

1.  In the side navigation area, select <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Database Access* \> *Database Analysis Users*.
2.  Select the user you want to delete and then click *Delete*.

Deleting a database analysis user does not delete its audit logs. The audit logs will be deleted after a retention period of 180 days. As they can consume a large amount of disk storage, you may want to manually delete them before the end of the retention period \(see [Monitor Read and Change Actions with Audit Logs](monitor-read-and-change-actions-with-audit-logs-110404a.md)\).

