<!-- loiod66ac1efb5054068a104c4559b72d272 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Set Priorities and Statement Limits for Spaces or Groups

Prioritize between spaces or groups for resource consumption and set limits to the amount of memory and threads that a space or group can consume when processing statements.

This topic contains the following sections:

-   [Prerequisites](set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md#loiod66ac1efb5054068a104c4559b72d272__section_ogc_jrp_4fc)
-   [Set Priorities and Statement Limits by Space](set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md#loiod66ac1efb5054068a104c4559b72d272__section_hkh_55p_4fc)
-   [Set Priorities and Statement Limits by Group](set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md#loiod66ac1efb5054068a104c4559b72d272__section_a3p_1cq_4fc)
-   [Export Workload Management Settings](set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md#loiod66ac1efb5054068a104c4559b72d272__section_chn_wfq_4fc)
-   [Import Workload Management Settings](set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md#loiod66ac1efb5054068a104c4559b72d272__section_h1v_qmm_pfc)



<a name="loiod66ac1efb5054068a104c4559b72d272__section_ogc_jrp_4fc"/>

## Prerequisites

To set priorities and statement limits for spaces or groups, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Administration* and *Configuration* areas in the *System* tool.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

> ### Note:  
> Relevant only for spaces with a storage type *SAP HANA Database \(Disk and In-Memory\)*, and not for *SAP HANA Data Lake Files* spaces.

> ### Note:  
> You can use the SAP Datasphere command line interface, `datasphere`, to set space or group priorities and statement limits. See [Manage Priorities and Statement Limits for Spaces or Groups via the Command Line](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/9e3537b72e6c445d9f34201df650735b.html "You can use the SAP Datasphere datasphere command line interface to set priorities and statement limits for spaces or groups.") :arrow_upper_right:.



<a name="loiod66ac1efb5054068a104c4559b72d272__section_hkh_55p_4fc"/>

## Set Priorities and Statement Limits by Space

You can set priorities and statement limits by space \(default option\). Once you’ve created a space, a new row for the space is added in the *Workload Management* page with a default priority and default statement limits.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\)** \> *Workload Management*.
2.  If *Space* is not already selected, select it and click *Save*. Be aware that if you've modified the default settings for the *Group* option, once you confirm the reorganization by space, your settings will be deleted. To keep your settings, you can export them \(see [Export Workload Management Settings](set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md#loiod66ac1efb5054068a104c4559b72d272__section_chn_wfq_4fc)\).
3.  In the confirmation message that opens, click *Yes*. The process may take some time but you can continue to work in other areas of SAP Datasphere.
4.  Click on the row of the space for which you want to edit the properties.

    > ### Note:  
    > You can search for a space based on its ID by entering one or more characters in the *Search* field. Only the spaces whose space ID includes the entered characters are displayed in the table.

5.  To prioritize between spaces, specify in the *Space Priority* section the prioritization of this space when querying the database. You can choose a value from 1 \(lowest priority\) to 8 \(highest priority\). The default value is 5. In situations where spaces are competing for available threads, those with higher priorities have their statements run before those of spaces with lower priorities.
6.  To manage other workload parameters, you can select either of the following in the *Configuration* dropdown list:
    -   *Default*. The default configuration provides generous resource limits, while preventing any single space from overloading the system. The default configuration is applied by default to new spaces.

        These statement limit and admission control parameters are taken into account in the default configuration and cannot be changed:


        <table>
        <tr>
        <th valign="top">

        Parameter
        
        </th>
        <th valign="top">

        Value
        
        </th>
        </tr>
        <tr>
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

        Parameter
        
        </th>
        <th valign="top">

        Value
        
        </th>
        </tr>
        <tr>
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
        

7.  Click *Save*. The changes are reflected in the space details page in read-only.



<a name="loiod66ac1efb5054068a104c4559b72d272__section_a3p_1cq_4fc"/>

## Set Priorities and Statement Limits by Group

You can set priorities and statement limits by group \(which are groups of processes\) and distribute the workload between the 8 groups provided.

For example, you can choose a total thread and memory limit for the Analytic Consumption group that are higher than for the Modeling or the Data Management group, which can typically run more slowly in the background.

You distribute your workload management with these groups:


<table>
<tr>
<th valign="top">

Group

</th>
<th valign="top">

Processes

</th>
</tr>
<tr>
<td valign="top">

Analytic Consumption

</td>
<td valign="top">

Analytic data preview inside the *Analytic Model* editors.

Data consumption of SAP Datasphere models in SAP Analytics Cloud.

Consumption of SAP Datasphere data via OData.

</td>
</tr>
<tr>
<td valign="top">

Data Management

</td>
<td valign="top">

Actions related to data integration, such as running task chains, persisting data or importing data.

</td>
</tr>
<tr>
<td valign="top">

Modeling

</td>
<td valign="top">

Data preview actions in the *Business Builder* and the *Data Builder*.

</td>
</tr>
<tr>
<td valign="top">

SAP Analytics Cloud Data Management

</td>
<td valign="top">

Import and export of data in SAP Analytics Cloud.

</td>
</tr>
<tr>
<td valign="top">

SAP Analytics Cloud Interactive Operations

</td>
<td valign="top">

Navigation in SAP Analytics Cloud, primarily for loading stories.

</td>
</tr>
<tr>
<td valign="top">

SAP Analytics Cloud Long-Running Operations

</td>
<td valign="top">

Background jobs for planning workflows in SAP Analytics Cloud.

</td>
</tr>
<tr>
<td valign="top">

SAP Analytics Cloud System Operation

</td>
<td valign="top">

Background operations in SAP Analytics Cloud, such as collecting statistics and cleaning up jobs.

</td>
</tr>
<tr>
<td valign="top">

SQL Access

</td>
<td valign="top">

All actions related to space database users.

</td>
</tr>
</table>

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\)** \> *Workload Management*.
2.  If *Group* is not already selected, select it and click *Save*. Be aware that if you've modified the default settings for the option *Space*, once you confirm the reorganization by group, your settings will be deleted. To keep your settings, you can export them \(see [Export Workload Management Settings](set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md#loiod66ac1efb5054068a104c4559b72d272__section_chn_wfq_4fc)\).
3.  In the confirmation message that opens, click *Yes*. The process may take some time but you can continue to work in other areas of SAP Datasphere.

    The groups are provided with the following default priorities and statement limits:


    <table>
    <tr>
    <th valign="top">

    Group
    
    </th>
    <th valign="top">

    Priority
    
    </th>
    <th valign="top">

    ADMISSION CONTROL QUEUE CPU THRESHOLD
    
    </th>
    <th valign="top">

    ADMISSION CONTROL REJECT CPU THRESHOLD
    
    </th>
    <th valign="top">

    STATEMENT TIMEOUT
    
    </th>
    <th valign="top">

    TOTAL STATEMENT THREAD LIMIT
    
    </th>
    <th valign="top">

    TOTAL STATEMENT MEMORY LIMIT
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Analytic Consumption
    
    </td>
    <td valign="top">
    
    7
    
    </td>
    <td valign="top">
    
    90%
    
    </td>
    <td valign="top">
    
    99%
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    <td valign="top">
    
    70%
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Data Management
    
    </td>
    <td valign="top">
    
    5
    
    </td>
    <td valign="top">
    
    90%
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    <td valign="top">
    
    50%
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Modeling
    
    </td>
    <td valign="top">
    
    7
    
    </td>
    <td valign="top">
    
    90%
    
    </td>
    <td valign="top">
    
    99%
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    <td valign="top">
    
    40%
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Analytics Cloud Data Management
    
    </td>
    <td valign="top">
    
    5
    
    </td>
    <td valign="top">
    
    90%
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    <td valign="top">
    
    40%
    
    </td>
    <td valign="top">
    
    40%
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Analytics Cloud Interactive Operations
    
    </td>
    <td valign="top">
    
    5
    
    </td>
    <td valign="top">
    
    90%
    
    </td>
    <td valign="top">
    
    99%
    
    </td>
    <td valign="top">
    
    185 seconds
    
    </td>
    <td valign="top">
    
    70%
    
    </td>
    <td valign="top">
    
    70%
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Analytics Cloud Long-Running Operations
    
    </td>
    <td valign="top">
    
    5
    
    </td>
    <td valign="top">
    
    90%
    
    </td>
    <td valign="top">
    
    99%
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    <td valign="top">
    
    20%
    
    </td>
    <td valign="top">
    
    20%
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Analytics Cloud System Operation
    
    </td>
    <td valign="top">
    
    8
    
    </td>
    <td valign="top">
    
    90%
    
    </td>
    <td valign="top">
    
    99%
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    <td valign="top">
    
    50%
    
    </td>
    <td valign="top">
    
    50%
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SQL Access
    
    </td>
    <td valign="top">
    
    8
    
    </td>
    <td valign="top">
    
    90%
    
    </td>
    <td valign="top">
    
    99%
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    <td valign="top">
    
    60%
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    </tr>
    </table>
    
    The default configuration provides generous resource limits, while preventing any single group from overloading the system.

4.  To change the priority or statement limits of a group, click it and change the settings as follows:

    > ### Note:  
    > The statement timeout and admission control parameters mentioned in the table of the previous step are also taken into account in the custom configuration but you cannot change their values.


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Priority*
    
    </td>
    <td valign="top">
    
    To prioritize between groups, specify the priority of this group when querying the database. You can choose a value from 1 \(lowest priority\) to 8 \(highest priority\). The default value depends on the group. In situations where groups are competing for available threads, those with higher priorities have their statements run before those of groups with lower priorities.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Total Statement Thread Limit*
    
    </td>
    <td valign="top">
    
    Select *Configuration* \> *Custom* and enter the maximum number \(or percentage\) of threads that statements running concurrently in the group can consume. You can enter a percentage between 1% and 100% \(or the equivalent number\) of the total number of threads available in your tenant.

    Setting this limit prevents the group from consuming too many threads, and can help with balancing resource consumption between competing groups.

    > ### Caution:  
    > Be aware that setting this limit too low may impact statement performance, while excessively high values may impact the performance of statements in other groups.

    The default value is 70% for all groups.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Total Statement Memory Limit*
    
    </td>
    <td valign="top">
    
    Select *Configuration* \> *Custom* and enter the maximum number \(or percentage\) of GBs of memory that statements running concurrently in the group can consume. You can enter any value or percentage between 0 \(no limit\) and the total amount of memory available in your tenant.

    Setting this limit prevents the group from consuming all available memory, and can help with balancing resource consumption between competing groups.

    > ### Caution:  
    > Be aware that setting this limit too low may cause out-of-memory issues, while excessively high values or 0 may allow the group to consume all available system memory.

    The default value is 80% for all groups.
    
    </td>
    </tr>
    </table>
    
5.  Click *Save*.



<a name="loiod66ac1efb5054068a104c4559b72d272__section_chn_wfq_4fc"/>

## Export Workload Management Settings

To keep the workload settings, for spaces or groups, that you have customized, you can export them in a .json file.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\)** \> *Workload Management*.
2.  Click the export button. The .json is dowloaded to your computer.
3.  Save it.



<a name="loiod66ac1efb5054068a104c4559b72d272__section_h1v_qmm_pfc"/>

## Import Workload Management Settings

To apply the customized workload settings, for spaces or groups, that you have previously exported, you can import the saved .json file.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\)** \> *Workload Management*.
2.  Click the import button.
3.  Select the .json file that you have previously exported and click *Import*.

    The workload management settings are applied.


