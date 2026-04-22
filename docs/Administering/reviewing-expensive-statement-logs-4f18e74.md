<!-- loio4f18e743a6464d878f6e10b56461df3e -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Reviewing Expensive Statement Logs

Monitor SQL statements exceeding configured thresholds, including execution details such as duration, memory usage, CPU time, errors, and object information to identify performance issues and resource bottlenecks.



## Prerequisites

To monitor expensive statement logs, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access *Expensive Statement Logs* in the *Monitoring* app.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Application RolesStandard Roles Delivered with SAP Datasphere](Managing-Users-and-Roles/standard-application-rolesstandard-roles-delivered-with-sap-datasphere-a50a51d.md). 



## Reviewing Expensive Statement Logs

In the side navigation area, click :desktop_computer: *Monitoring* \> <span class="SAP-icons-V5"></span> *Expensive Statement Logs* . The *Expensive Statement Logs* app lists the logs of SQL statement runs that exceed the specified thresholds.

> ### Note:  
> This app contains data if the *Enable Expensive Statement Tracing* \(in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*\) is enabled. See [Configure Monitoring](configure-monitoring-9cd0691.md).

The table contains the following columns:


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

*Start Date and Time*

</td>
<td valign="top">

Time \(date and hour\) the expensive statement has started to run.

</td>
</tr>
<tr>
<td valign="top">

*Duration*

</td>
<td valign="top">

How long in milliseconds the expensive statement has run.

</td>
</tr>
<tr>
<td valign="top">

*Object Type*

</td>
<td valign="top">

-   Type of object that was run in the expensive statement \(for example: view, remote table, data flow\).

-   Or area where the expensive statement was run:

    -   MDS - this is an SAP HANA multi-dimensional services \(MDS\) expensive statement, which is caused for example by stories when SAP Analytics Cloud queries SAP Datasphere.

    -   Data Flow - run by a data flow.

    -   Analysis - run by a database analysis user.

    -   Space SQL - run by a database user of a space.

    -   Business Layer Modeling - run in the *Business Builder*.

    -   Data Layer Modeling - run in the data preview of the view editor in the *Data Builder*.

    -   DWC Space Management - run in the *Space Management*, for example, when deploying an object.

    -   DB Usergroup - run by a user of a database user group.

    -   DWC Administration - run for an administration task such as writing a task framework status.

    -   System - any other SAP HANA system expensive statement.





</td>
</tr>
<tr>
<td valign="top">

*Activity*

</td>
<td valign="top">

Action that was performed. For example: update, compile, select.

</td>
</tr>
<tr>
<td valign="top">

*Object Name*

</td>
<td valign="top">

Name of the object for which the task-related expensive statement was run.

</td>
</tr>
<tr>
<td valign="top">

*Schema Name* 

</td>
<td valign="top">

Name of the schema in which the expensive statement is run.

</td>
</tr>
<tr>
<td valign="top">

*SAP HANA Peak Memory \(MB\)*

</td>
<td valign="top">

Maximum amount of memory \(in MB\) the expensive statement has used during the runtime in SAP HANA.

> ### Note:  
> You can see the information if the option *Enable Expensive Statement Tracing* is enabled and if the expensive statement exceeds the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*. See [Configure Monitoring](configure-monitoring-9cd0691.md).
> 
> Otherwise, no number is displayed.



</td>
</tr>
<tr>
<td valign="top">

*SAP HANA CPU Time \(ms\)*

</td>
<td valign="top">

Amount of CPU time \(in ms\) the expensive statement has used in SAP HANA.

> ### Note:  
> You can see the information if the option *Enable Expensive Statement Tracing* is enabled and if the expensive statement exceeds the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*. See [Configure Monitoring](configure-monitoring-9cd0691.md).
> 
> Otherwise, no number is displayed.

> ### Note:  
> CPU time measures the time used by all threads. If it's much higher than the expensive statement's duration, it indicates heavy thread usage. Prolonged high thread usage can lead to resource bottlenecks and task cancellations, so no other tasks should be scheduled then.



</td>
</tr>
<tr>
<td valign="top">

*Statement Details*

</td>
<td valign="top">

Shows the *More* link that you can click to view the complete SQL statement.

> ### Note:  
> For MDS queries - If you’ve enabled the tracing of MDS information \(see [Configure Monitoring](configure-monitoring-9cd0691.md)\), the payload of the MDS query that is run by SAP Analytics Cloud is displayed. If identified in the payload, the following information is also displayed: story ID, story name and data sources. You can copy or download the displayed information.



</td>
</tr>
<tr>
<td valign="top">

*Parameters*

</td>
<td valign="top">

Values of the parameters of the expensive statement that are indicated by the character "?" in the popup that opens when clicking *More* in the *Statement Details* column.

</td>
</tr>
<tr>
<td valign="top">

*Out-of-memory*

</td>
<td valign="top">

Shows if the expensive statement has an out-of-memory error. If there is one, a timestamp is displayed. It is empty if there is none.

</td>
</tr>
<tr>
<td valign="top">

*Task Log ID*

</td>
<td valign="top">

If the expensive statement is related to a task, it shows the identifier of the task within a link, which takes you to the *Tasks Logs* app filtered on this task.

</td>
</tr>
<tr>
<td valign="top">

*Elastic Compute Node*

</td>
<td valign="top">

If the expensive statement exceeds the thresholds specified in the option *Enable Expensive Statement Tracing* in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring* \(see [Configure Monitoring](configure-monitoring-9cd0691.md)\):

-   Name of the elastic compute node if the expensive statement is run on an elastic compute node.

-   Shows a hyphen \(-\) if the expensive statement is run on the main instance.




</td>
</tr>
<tr>
<td valign="top">

*Error Code*

</td>
<td valign="top">

Numeric code of the SQL error if the expensive statement has failed. See [SQL Error Codes](https://help.sap.com/docs/SAP_HANA_PLATFORM/4fe29514fd584807ac9f2a04f6754767/20a78d3275191014b41bae7c4a46d835.html) in the *SAP HANA SQL Reference Guide for SAP HANA Platform*.

</td>
</tr>
<tr>
<td valign="top">

*Error Message*

</td>
<td valign="top">

Description of the SQL error if the expensive statement has failed.

</td>
</tr>
<tr>
<td valign="top">

*Workload Class*

</td>
<td valign="top">

If the expensive statement has an out-of-memory error, it shows the name of the workload class whose limit has been exceeded.

</td>
</tr>
<tr>
<td valign="top">

*Statement ID*

</td>
<td valign="top">

Identifier of the expensive statement.

</td>
</tr>
<tr>
<td valign="top">

*Connection ID*

</td>
<td valign="top">

ID used to connect to the database.

</td>
</tr>
<tr>
<td valign="top">

*Start Date*

</td>
<td valign="top">

Date the expensive statement has started to run.

</td>
</tr>
</table>

> ### Note:  
> Data on expensive statements are kept for a time that depends on the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring* \(see [Configure Monitoring](configure-monitoring-9cd0691.md)\). As a certain number of expensive statements are kept \(30.000 by default\), if very low thresholds are set, the time period may be very low \(for example, only a few hours\). To keep the expensive statements for a longer time, the thresholds should be set accordingly.



## Show/Hide, Filter, Sort and Reorder Columns

You can control the display of entries as follows:

-   Reorder the columns by drag and drop.
-   Sort on a column by clicking the column header and then clicking <span class="SAP-icons-V5"></span> \(Sort Ascending\) or <span class="SAP-icons-V5"></span> \(Sort Descending\).
-   Filter on a column by using the quick filtering or the advanced filtering options.

    -   **Quick Filters** 


        <table>
        <tr>
        <th valign="top">

        Filter
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Date and Time Range*
        
        </td>
        <td valign="top">
        
        Enter one date and time range or click <span class="SAP-icons-V5"></span> to see the available options:

        -   Single Dates - *Today*, *Yesterday*
        -   Date Ranges - *From/To*, *From/To \(Date and Time\)*, *From*, *To*, *From \(Date and Time\)*,*To \(Date and Time\)*, *Last X Minutes/Hours/Days/Weeks* 
        -   Custom Options - *Last 1 Hour*, *Last 6 Hours*, *Last 24 Hours*


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Spaces*
        
        </td>
        <td valign="top">
        
        Select or enter the name of at least one space. All spaces of the tenant are available, even the ones you are not added to.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Statuses*
        
        </td>
        <td valign="top">
        
        Select or enter at least one status: *Completed*, *Failed*, or *Running*.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Space Storage Type*
        
        </td>
        <td valign="top">
        
        Select one type of space storage: *SAP HANA Database* or *SAP HANA Data Lake Files*.
        
        </td>
        </tr>
        </table>
        
        > ### Example:  
        > You are looking for all failed and running records that happened last week in the space *ACME\_TF*. Define the time range by clicking <span class="SAP-icons-V5"></span> to display the list of available options and selecting *From/To* in *Date and Time Range* and selecting the dates relevant to you in the calendar. Then, select the space *ACME\_TF* in the *Space* filter drop down list. Finally, select *Failed* and *Running* in the *Statuses* drop down list. The log list automatically updates after each filter definition.

        > ### Note:  
        > -   Defined quick filters are shown in the *Define Filter* dialog. If you add an advanced filter in the *Define Filter* dialog, the quick filters fields will be cleared. The filters are not deleted.
        > -   Filters defined in the *Define Filter* dialog are not shown in the quick filters fields.

    -   **Advanced Filters** 
        1.  Click a column header, then click <span class="FPA-icons-V3"></span> \(Filter\). The *Define Filter* dialog opens and advanced filtering options are available.
        2.  Chose the appropriate section for your filter. If your filter is meant to include data in the table \(you could say "I want my Data Preview to show"\), add your filter in the *Include* section. If your filter is meant to exclude data from the table \(you could say "I want my Data Preview to hide"\), add your filter in the *Exclude* section. When in the appropriate section, click <span class="FPA-icons-V3"></span> \(Add Filter\) to add a filter.
        3.  Select a column to filter on, a filtering option, and a value. You can add several filters. Click *OK* to apply the filter\(s\). The currently applied filters are displayed above the table.

            > ### Example:  
            > To only see the tasks that have failed on remote tables, in the *Include* area, select the column *Object Type*, then the filtering value *contains* and enter "REMOTE". Then, add a filter, select the column *Status*, then the filtering value *contains* and enter "FAILED". Once applied, the filter is displayed above the table.

        4.  Click *Clear Filter* in the filter strip or <span class="FPA-icons-V3"></span> \(Remove Filter\) in the *Define Filter* dialog to remove the filter.


    > ### Note:  
    > -   The filtering options available depend on the data type of the column you filter on.
    > -   Filters applied to text columns are case-sensitive.
    > -   You can enter filter or sort values in multiple columns.
    > -   To increase performance, only the first 1,000 rows are displayed. Use filters to find the data you are looking for. Filters are applied to all rows, but only the first filtered 1,000 rows are displayed.

    > ### Note:  
    > If you filter on one of the following columns and you enter a number, use the “.” \(period\) character as the decimal separator, regardless of the decimal separator used in the number formatting that you’ve chosen in the general user settings \(*Settings* \> *Language & Region*\): *SAP HANA Peak Memory*, *SAP HANA CPU Time*, *SAP HANA Used Memory* and *SAP HANA Used Disk*.

-   Show or hide columns by clicking :gear: to open the *Columns Settings* dialog, selecting columns as appropriate. To return to the default preview columns, click *Reset*.
-   Refresh the table at any time by clicking *Refresh*.

