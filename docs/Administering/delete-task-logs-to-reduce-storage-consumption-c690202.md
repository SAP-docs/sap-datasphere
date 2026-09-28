<!-- loioc6902024ecd74956b4ba2d1c67ccb073 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Delete Task Logs to Reduce Storage Consumption

In the *Configuration* area, you can check how much space the task logs are using on your tenant, and decide to delete the obsolete ones to reduce storage consumption.



<a name="loioc6902024ecd74956b4ba2d1c67ccb073__prereq_mtr_4jb_q2c"/>

## Prerequisites

To delete task logs and reduce storage consumption, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *System* tool.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loioc6902024ecd74956b4ba2d1c67ccb073__context_j5v_tkc_xlb"/>

## Context

Each time an activity is running in SAP Datasphere \(for example, replicate a remote table\), task logs are created to allow you to check if the activity is running smoothly or if there is an issue to solve. You access these detailed task logs by navigating to the Data Integration Monitor - Details screen of the relevant object. For example, clicking the button ![](images/Remote_Table_Logs_Button_a6170ee.png) of the relevant remote table. See [Managing and Monitoring Data Integration](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4cbf7c7fc64645bfa364332827557267.html "Users with a space administrator or integrator role can use the  (Data Integration) app to schedule, run, and monitor data replication and persistence tasks for remote tables and views, track queries sent to remote source systems, and manage other tasks through flows and task chains.") :arrow_upper_right:.

However, task logs can consume a lot of space in a tenant. Deleting old task logs that are no longer needed can be useful to release storage space. This is why SAP Datasphere has a log deletion schedule activated by default. You can change the schedule defining your own criteria or decide to take immediate deletion actions.



<a name="loioc6902024ecd74956b4ba2d1c67ccb073__steps_r4h_kkc_xlb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(Configuration\) → *Tasks*.

2.  Under *Storage Consumption*, you can review how much space task logs are using within your tenant. The following details are provided:

    -   *Last Deletion Run*: The date and time when the most recent task for deleting logs finished, along with whether the task was executed manually or via a scheduled run.
    -   *Memory Used for Storage*: The total memory currently occupied by logs across all SAP spaces in the tenant.
    -   *Disk Used for Storage*: The total disk space consumed by logs across all SAP spaces in the tenant.
    -   *Disk Used for Storage \(Spark\)*: The amount of disk space used for logs storage within all SAP HANA Data Lake Files spaces \(file space\). After a deletion task runs, this metric is updated to show the reduction \(e.g., “reduced from X MB to X MB”\), so you can easily see how much space has been freed.
    -   *Number of Tasks With Deleted Logs*: The count of tasks that have associated deletion logs.

3.  If needed, decide how you want to delete the task logs.

    -   Schedule Task Log Deletion: SAP Datasphere automatically runs logs deletion using the following default criteria:

        -   Deletion tasks will be run every 4 months
        -   Task logs older than 200 days will be deleted

        You can set the options to run the task deletion every x days or months, and then clean up logs every x days or weeks. Click *Save*.

    -   Manual Deletion: You want to manually delete task logs to take immediate action. Go to the *Manually Delete Task Log* section and determine how long you want to keep the logs. For example, delete the logs that are older than 100 days.

        Click *Delete*.

        > ### Note:  
        > Deleting these logs do not set the storage to zero because some files remain. Running procedures may take longer to run and can incur costs due to using Object Store Requests \(API Requests\).
        > 
        > The displayed size of log files in the Object Store \(*Disk used for storage \[Spark\]*\) is calculated before and after a deletion run and remains unchanged until the next deletion run completes. This approach helps avoid unnecessary resource usage for frequent size recalculations.



