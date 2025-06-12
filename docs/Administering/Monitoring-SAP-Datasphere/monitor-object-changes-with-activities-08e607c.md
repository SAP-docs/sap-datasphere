<!-- loio08e607c58e5343bd9c0287e7e22c452a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitor Object Changes with Activities

Monitor the changes that users perform on modeling objects \(such as spaces and tables\) as well as changes to the system configuration \(such as roles and users\).

This topic contains the following sections:

-   [Prerequisites](monitor-object-changes-with-activities-08e607c.md#loio08e607c58e5343bd9c0287e7e22c452a__section_of4_45q_hfc)
-   [Context](monitor-object-changes-with-activities-08e607c.md#loio08e607c58e5343bd9c0287e7e22c452a__section_elq_m5q_hfc)
-   [View all Activities and Filter on Specific Activities](monitor-object-changes-with-activities-08e607c.md#loio08e607c58e5343bd9c0287e7e22c452a__section_azg_szx_mdc)
-   [Download and Delete the Activity Log for a Specific Time Period](monitor-object-changes-with-activities-08e607c.md#loio08e607c58e5343bd9c0287e7e22c452a__section_wbw_szx_mdc)



<a name="loio08e607c58e5343bd9c0287e7e22c452a__section_of4_45q_hfc"/>

## Prerequisites

To monitor object changes with activities, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Activity Log* \(`-R------`\) - To view and download activities. The *DW Administrator* role template, for example, grants this privilege.
-   *Activity Log* \(`---D----`\) - To delete activity logs.

For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loio08e607c58e5343bd9c0287e7e22c452a__section_elq_m5q_hfc"/>

## Context

Actions that are performed by users are logged in *Security* \> *Activities*.

For example:

-   Space creation and changes

-   Table changes

-   Role changes and assignments

-   Logged users




<a name="loio08e607c58e5343bd9c0287e7e22c452a__section_azg_szx_mdc"/>

## View all Activities and Filter on Specific Activities

To view activities, you must have a global role that grants you the privilege:

-   *Activity Log* \(`-R------`\) – Read activities


The DW Administrator global role, for example, grants this privilege.

1.  In the side navigation area, click *Security* \> *Activities*.

2.  To filter for specific types of activities, select <span class="FPA-icons-V3"></span> \(Filter\).

    In the *Set Filters* dialog, you can select one or more parameters to filter in the *Available Filters* list. In the *Active Filters* list, type or choose a filter value for each parameter that you select. When you click *OK*, the log is filtered according to your selections.

    If you apply filters to the log, the entries that you filter out are also excluded if you download the activity data.




<a name="loio08e607c58e5343bd9c0287e7e22c452a__section_wbw_szx_mdc"/>

## Download and Delete the Activity Log for a Specific Time Period

To download and delete activity logs, you must have a global role that grants you the privilege:

-   *Activity Log* \(`-R-D----`\) – Read and delete activities


The DW Administrator global role, for example, grants this privilege.

When the size of the activity log approaches the limit, users who have the *Delete* permission for the *Activity Log* privilege will receive an email and an alert notification. Further alerts will be sent if the log continues to grow closer to the limit.

When the activity log reaches its limit, final notifications are sent, and then the oldest rows will be deleted from the system to keep the log size below the limit. To reduce the size of the log, you can first download part or all of the log as CSV files, and then delete those log entries from the system.

The default limit for the activity log is 500,000 rows. You can request that this number be changed to a higher number, or changed to a one-year rolling period, by entering a support ticket.

1.  In the side navigation area, click *Security* \> *Activities*.

    You can also open the *Activities* page directly from the link in the notification email.

2.  If you want to filter the activities that you will download, select <span class="FPA-icons-V3"></span> \(Filter\).

    > ### Tip:  
    > Filtering the activity log can be useful when collecting troubleshooting data, but is usually not necessary for archiving activity log data.

    In the *Set Filters* dialog, select the filters that you want to apply, and choose a value for each filter. *Time Stamp* filters will be overridden by your settings in the *Download Activities* dialog.

3.  Select *Download Options*

4.  In the *Download Activities* dialog, type a file name for the download in the *Name* field.

5.  Select a *Starting Date* and an *End Date*, and select *Download*.

    The rows within the dates and filters that you specified are downloaded as CSV files with up to 75 000 rows each.

6.  To delete activity data, select the \(Delete options\) icon.

7.  In the *Delete Activities* dialog, select a *Time* period.

8.  If you choose *Specific range*, set a *Starting Date* and an *End Date*.

    We recommend to delete the same range that you downloaded.

    > ### Note:  
    > Filters applied in the *Activities* page don't apply to the delete operation.

9.  Select *Delete*.

    All activity rows in the specified time period are deleted from the system.


