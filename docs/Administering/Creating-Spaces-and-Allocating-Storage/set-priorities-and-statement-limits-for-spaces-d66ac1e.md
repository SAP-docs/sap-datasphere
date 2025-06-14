<!-- loiod66ac1efb5054068a104c4559b72d272 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Set Priorities and Statement Limits for Spaces

Prioritize between spaces for resource consumption and set limits to the amount of memory and threads that a space can consume when processing statements.



<a name="loiod66ac1efb5054068a104c4559b72d272__prereq_dbt_dcp_hfc"/>

## Prerequisites

To set priorities and statement limits for spaces, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Administration* and *Configuration* areas in the *System* tool.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loiod66ac1efb5054068a104c4559b72d272__context_fml_vgc_r2c"/>

## Context

> ### Note:  
> Relevant only for spaces with a storage type *SAP HANA Database \(Disk and In-Memory\)*, and not for *SAP HANA Data Lake Files* spaces.



<a name="loiod66ac1efb5054068a104c4559b72d272__steps_abz_fhb_wrb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\)** \> *Workload Management*, then click on the row of the space for which you want to edit the properties.

    > ### Note:  
    > You can search for a space based on its ID by entering one or more characters in the *Search* field. Only the spaces whose space ID includes the entered characters are displayed in the table.

2.  To prioritize between spaces, specify in the *Space Priority* section the prioritization of this space when querying the database. You can choose a value from 1 \(lowest priority\) to 8 \(highest priority\). The default value is 5. In situations where spaces are competing for available threads, those with higher priorities have their statements run before those of spaces with lower priorities.

3.  To manage other workload parameters, you can select either of the following in the *Configuration* dropdown list:

    -   *Default*. The default configuration provides generous resource limits, while preventing any single space from overloading the system. The default configuration is applied by default to new spaces.

        These statement limit and admission control parameters are taken into account in the default configuration and cannot be changed:


        <table>
        <tr>
        <th valign="top">

        Parameter Type
        
        </th>
        <th valign="top">

        Parameter
        
        </th>
        <th valign="top">

        Value
        
        </th>
        </tr>
        <tr>
        <td valign="top" rowspan="2">
        
        Admission Control
        
        </td>
        <td valign="top">
        
        ADMISSION CONTROL QUEUE CPU THRESHOLD
        
        </td>
        <td valign="top">
        
        90%
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        ADMISSION CONTROL REJECT CPU THRESHOLD
        
        </td>
        <td valign="top">
        
        99%
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Statement Limits
        
        </td>
        <td valign="top">
        
        TOTAL STATEMENT THREAD LIMIT
        
        </td>
        <td valign="top">
        
        70%
        
        </td>
        </tr>
        </table>
        
    -   *Custom*. These statement limit and admission control parameters are taken into account in the custom configuration. You can specify only the value for statements limits to set maximum total thread and memory limits that statements running concurrently in the space can consume:

        > ### Caution:  
        > Be aware that changing the statement limits may cause performance issues.


        <table>
        <tr>
        <th valign="top">

        Parameter Type
        
        </th>
        <th valign="top">

        Parameter
        
        </th>
        <th valign="top">

        Value
        
        </th>
        </tr>
        <tr>
        <td valign="top" rowspan="2">
        
        Admission Control
        
        </td>
        <td valign="top">
        
        ADMISSION CONTROL QUEUE CPU THRESHOLD
        
        </td>
        <td valign="top">
        
        90%
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        ADMISSION CONTROL REJECT CPU THRESHOLD
        
        </td>
        <td valign="top">
        
        99%
        
        </td>
        </tr>
        <tr>
        <td valign="top" rowspan="2">
        
        Statement Limits
        
        </td>
        <td valign="top">
        
        TOTAL STATEMENT THREAD LIMIT
        
        </td>
        <td valign="top">
        
        In the *Total Statement Thread Limit* area, enter the maximum number \(or percentage\) of threads that statements running concurrently in the space can consume. You can enter a percentage between 1% and 100% \(or the equivalent number\) of the total number of threads available in your tenant.

        > ### Note:  
        > 100% represents the maximum of 80% of CPU resources reserved for workload generated by spaces, user group users and agent users. The remaining 20% of CPU resources are reserved to ensure that the system can respond under heavy load.

        Setting this limit prevents the space from consuming too many threads, and can help with balancing resource consumption between competing spaces.

        > ### Caution:  
        > Be aware that setting this limit too low may impact statement performance, while excessively high values may impact the performance of statements in other spaces.

        Default: 70%
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        TOTAL STATEMENT MEMORY LIMIT
        
        </td>
        <td valign="top">
        
        In the *Total Statement Memory Limit* area, enter the maximum number \(or percentage\) of GBs of memory that statements running concurrently in the space can consume. You can enter any value or percentage between 0 \(no limit\) and the total amount of memory available in your tenant.

        Setting this limit prevents the space from consuming all available memory, and can help with balancing resource consumption between competing spaces.

        > ### Caution:  
        > Be aware that setting this limit too low may cause out-of-memory issues, while excessively high values or 0 may allow the space to consume all available system memory.

        Default: 80%
        
        </td>
        </tr>
        </table>
        
        > ### Note:  
        > Admission control is designed to avoid overloading the system under peak load by denying any further SQL requests when the load on the system is equal to or exceeds a given threshold.
        > 
        > You can investigate why statements are being queued or rejected.
        > 
        > -   Events related to requests which have been queued for longer than 5 seconds are logged and can be reviewed in the M\_ADMISSION\_CONTROL\_EVENTS view. For more information, see [Managing Peak Load \(Admission Control\)](https://help.sap.com/viewer/f9c5015e72e04fffa14d7d4f7267d897/latest/en-US/8569dd96c6ab4849a21f4a97d1ffe832.html) in the *SAP HANA Cloud, SAP HANA Database Administration Guide*.
        > 
        > -   You can monitor the statements that are queued or rejected by viewing the cards dedicated to admission control in the *Dashboard* tab of the *System Monitor*. For more information, see [Monitoring SAP Datasphere](../Monitoring-SAP-Datasphere/monitoring-sap-datasphere-28910cd.md).
        > 
        > 
        > A statement which exceeds a reject threshold is rejected with the SQL error 616: 'rejected by workload class configuration'. A statement which exceeds a queue threshold is queued for up to 10 minutes, after this time the statement is rejected with the SQL error 616: 'queue wait timeout exceeded'. For more information, see [Properties for Workload Classes and Mappings](https://help.sap.com/viewer/f9c5015e72e04fffa14d7d4f7267d897/latest/en-US/3ae17c3b1d6c4adea6f0ddfec3041dd4.html) in the *SAP HANA Cloud, SAP HANA Database Administration Guide*.

        > ### Note:  
        > If too many statements are rejected, we recommend that you to perform these two actions:
        > 
        > -   **Decrease the total statement thread limit for the spaces which consume a large amount of CPU time**.
        > 
        >     First, identify the spaces which consume a large amount of CPU time: As a database analysis user, analyze the M\_WORKLOAD\_CLASS\_STATISTICS view in the Database Explorer, like in this example:
        > 
        >     ```
        >     SELECT "MD"."SPACE_ID", "WCS"."TOTAL_STATEMENT_CPU_TIME", "WCS"."TOTAL_STATEMENT_REJECT_COUNT"
        >     FROM "SYS"."M_WORKLOAD_CLASS_STATISTICS" AS "WCS"
        >     LEFT JOIN "DWC_TENANT_OWNER"."SPACE_METADATA" AS "MD" ON "WCS"."WORKLOAD_CLASS_NAME" = "MD"."VALUE"
        >     AND "MD"."SECTION" = '_workloadManagement' AND "MD"."KEY" = 'workloadClassName' 
        >     WHERE "MD"."SPACE_ID" IS NOT NULL AND "MD"."SPACE_ID" != '$$global$$' ORDER BY "WCS"."TOTAL_STATEMENT_CPU_TIME" DESC
        >     
        >     ```
        > 
        >     Using this sample code, all the spaces can be listed by the TOTAL\_STATEMENT\_CPU\_TIME descending order, which enables you to identify the spaces that consumed the most CPU time.
        > 
        >     As a second step, go to the *Workload Configuration* area of each identified space, select the configuration *Custom* and decrease the total statement thread limit. Some statements will take longer to run but will not be rejected.
        > 
        > -   **Avoid that tasks which consume a high load of CPU run at the same time**.
        > 
        >     You can adjust the task schedules in the *Data Integration Monitor*. See [Scheduling Data Integration Tasks](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7fa07621d9c0452a978cb2cc8e4cd2b1.html "Schedule data integration tasks to run periodically at a specified date or time.") :arrow_upper_right:.


4.  Click *Save*. The changes are reflected in the space details page in read-only.

    > ### Note:  
    > You can use the SAP Datasphere command line interface, `datasphere`, to set space priorities and statement limits for spaces. See [Manage Space Priorities and Statement Limits via the Command Line](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/9e3537b72e6c445d9f34201df650735b.html "You can use the SAP Datasphere datasphere command line interface to set space priorities and statement limits for spaces.") :arrow_upper_right:.


