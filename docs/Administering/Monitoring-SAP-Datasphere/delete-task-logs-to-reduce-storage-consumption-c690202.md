<!-- loioc6902024ecd74956b4ba2d1c67ccb073 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Delete Task Logs to Reduce Storage Consumption

In the *Configuration* area, you can check how much spaces the task logs are using on your tenant, and decide to delete the obsolete ones to reduce storage consumption.



<a name="loioc6902024ecd74956b4ba2d1c67ccb073__prereq_mtr_4jb_q2c"/>

## Prerequisites

To delete task logs and reduce storage consumption, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Administration* and *Configuration* areas in the *System* tool.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md).



<a name="loioc6902024ecd74956b4ba2d1c67ccb073__context_j5v_tkc_xlb"/>

## Context

Each time an activity is running in SAP Datasphere \(for example, replicate a remote table\), task logs are created to allow you to check if the activity is running smoothly or if there is an issue to solve. You access these detailed task logs by navigating to the Data Integration Monitor - Details screen of the relevant object. For example, clicking the button ![](images/Remote_Table_Logs_Button_a6170ee.png) of the relevant remote table. See [Managing and Monitoring Data Integration](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4cbf7c7fc64645bfa364332827557267.html "Users with a space administrator or integrator role can use the Data Integration Monitor app to schedule, run, and monitor data replication and persistence tasks for remote tables and views, track queries sent to remote source systems, and manage other tasks through flows and task chains.") :arrow_upper_right:.

However, task logs can consume a lot of spaces in a tenant. Deleting old task logs that are no longer needed can be useful to release storage space. This is why SAP Datasphere has a log deletion schedule activated by default. You can change the schedule defining your own criteria or decide to take immediate deletion actions.



<a name="loioc6902024ecd74956b4ba2d1c67ccb073__steps_r4h_kkc_xlb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(Configuration\) → *Tasks*.

2.  Check how much size the task logs consume on your tenant. If needed, decide how you want to delete the task logs.

    -   Manually Delete Task Log: SAP Datasphere automatically triggers logs deletion using the following default criteria:

        -   Deletion tasks will be run every 4 months
        -   Task logs older than 200 days will be deleted

        Go to the section *Schedule Task Log Deletion*, update the deletion criteria following your needs and click *Save*.

    -   Manual Deletion: You want to manually delete task logs to take immediate action. Go to the *Manually Delete Task Log* section and determine how long you want to keep the logs. For example, delete the logs that are older than 100 days.

        Click *Delete*.



