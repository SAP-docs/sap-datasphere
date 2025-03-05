<!-- loioc28145bcb76c4415a1ec6265dd2a4c11 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Database Analysis User to Debug Database Issues

Database analysis users are SAP HANA Cloud database users who have read-only access to all space schemas, and all their activities are recorded in audit logs. You create a database user to monitor, analyze, trace, or debug your SAP Datasphere database, and resolve a specific database issue.



## Context

A user with an administrator role can create a database analysis user.

> ### Note:  
> You should only create a database analysis user to resolve a specific database issue and then delete it immediately after the issue is resolved \(see [Manage Database Analysis Users](manage-database-analysis-users-4bb6d37.md)\). This user can access all SAP HANA Cloud monitoring views and all SAP Datasphere data in all spaces, including any sensitive data stored there.



<a name="loioc28145bcb76c4415a1ec6265dd2a4c11__steps_yv4_3q1_d5b"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Database Access* \> *Database Analysis Users*.

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
    
    Enter the suffix, which is used to create the full name of the user. Can contain a maximum of 31 uppercase letters or numbers and must not contain spaces or special characters other than `_` \(underscore\). See [Rules for Technical Names](../Creating-Spaces-and-Allocating-Storage/rules-for-technical-names-982f9a3.md).
    
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
    </table>
    
3.  Click *Create* to create the user.

    The host name and port, as well as the user password are displayed. Note these for later use.

4.  Select your user in the list and then click one of the following and enter your credentials:

    -   *Open SAP HANA Cockpit* - Open the *Database Overview* \> *Monitoring* page for the SAP Datasphere run-time database, which offers various monitoring tools. 

        For more information, see [Using the Database Overview Page to Manage a Database](https://help.sap.com/docs/HANA_CLOUD/9630e508caef4578b34db22014998dba/1115707b7dc846c99c3b2dac97520cf7.html)\).

    -   *Open Database Explorer* - Open an SQL Console for the SAP Datasphere run-time database. 

        For more information, see [Getting Started With the SAP HANA Database Explorer](https://help.sap.com/docs/SAP_HANA_COCKPIT/e8d0ddfb84094942a9f90288cd6c05d3/7fa981c8f1b44196b243faeb4afb5793.html)\).

        A database analysis user can run a procedure in Database Explorer to stop running statements. For more information, see [Stop a Running Statement With a Database Analysis User](stop-a-running-statement-with-a-database-analysis-user-0cf11ed.md).


    > ### Note:  
    > All actions of the database analysis user are logged in the `ANALYSIS_AUDIT_LOG` view, which is stored in the space that has been assigned to store audit logs \(see [Logging Read and Change Actions for Audit](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/266553976e1c4db9aaa28a75e2308b77.html "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who performed which action at which point in time.") :arrow_upper_right:\).
    > 
    > Audit logs can consume a large quantity of GB of disk in your SAP Datasphere tenant database. The audit log entries for database analysis users are kept for 180 days, after which they are automatically deleted. You can also manually delete the audit logs to free up disk space \(see [Delete Audit Logs](delete-audit-logs-589fa42.md)\). Also, a database analysis user can be automatically deactivated due to a large amount of disk storage consumed by audit logs \(see [Manage Database Analysis Users](manage-database-analysis-users-4bb6d37.md)\).


