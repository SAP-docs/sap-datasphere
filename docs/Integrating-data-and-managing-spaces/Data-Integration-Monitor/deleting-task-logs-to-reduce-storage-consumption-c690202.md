<!-- loioc6902024ecd74956b4ba2d1c67ccb073 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Deleting Task Logs to Reduce Storage Consumption

In the *Configuration* area, you can check how much spaces the task logs are using on your tenant, and decide to delete the obsolete ones to reduce storage consumption.



<a name="loioc6902024ecd74956b4ba2d1c67ccb073__context_j5v_tkc_xlb"/>

## Context

Each time an activity is running in SAP Datasphere \(for example, replicate a remote table\), task logs are created to allow you to check if the activity is running smoothly or if there is an issue to solve. You access these detailed task logs by navigating to the Data Integration Monitor - Details screen of the relevant object. For example, clicking the button ![](images/Remote_Table_Logs_Button_a6170ee.png) of the relevant remote table.

However, task logs can consume a lot of spaces in a tenant. Deleting old task logs that are no longer needed can be useful to release storage space. This is why SAP Datasphere has a log deletion schedule activated by default. You can change the schedule defining your own criteria or decide to take immediate deletion actions.



<a name="loioc6902024ecd74956b4ba2d1c67ccb073__steps_r4h_kkc_xlb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons"></span> \(Configuration\) → *Tasks*.

2.  Check how much size the task logs consume on your tenant. If needed, decide how you want to delete the task logs.

    -   Manually Delete Task Log: SAP Datasphere automatically triggers logs deletion using the following default criteria:

        -   Deletion tasks will be run every 4 months
        -   Task logs older than 200 days will be deleted

        Go to the section *Schedule Task Log Deletion*, update the deletion criteria following your needs and click *Save*.

    -   Manual Deletion: You want to manually delete task logs to take immediate action. Go to the *Manually Delete Task Log* section and determine how long you want to keep the logs. For example, delete the logs that are older than 100 days.

        Click *Delete*.



