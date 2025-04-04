<!-- loio9cd0691c44a74f2aa47b52f615f74433 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Monitoring

You can control which monitoring data is collected and also obtain independent access to the underlying SAP HANA monitoring views that power the *System Monitor*.

You need the DW Administrator role to access the *Monitoring* page.



<a name="loio9cd0691c44a74f2aa47b52f615f74433__section_jt3_hfb_xpb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) and then select the *Monitoring* tab.
2.  To obtain independent access to the underlying SAP HANA monitoring views that power the *System Monitor*:

    1.  Select a space from the drop-down list and click *Confirm Selected Space*.

        > ### Note:  
        > File spaces are not available in the list as they cannot be chosen as the monitoring space.

    2.  If you've created the *<SAP\_ADMIN\>* space and you want to enable it, click *Enable access to SAP Monitoring Content Space*. If there isn't any space named *<SAP\_ADMIN\>* in your tenant, this is not available for selection.

    For more information, see [Working with SAP HANA Monitoring Views](working-with-sap-hana-monitoring-views-4ab4509.md).

3.  Analyze individual SQL queries whose execution exceeds one or more thresholds, select *Enable Expensive Statement Tracing*. Keep the default settings or specify the following parameters to configure and filter the trace details, then save your changes.


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
    
    Memory Tracing Records
    
    </td>
    <td valign="top">
    
    Specify the maximum number of records that are stored in the monitoring tables.

    For example, if about 5 days are traced in the expensive statement tables and you don’t want to change the thresholds, you can double the number of records in *In-Memory Tracing Records* so that about 10 days are traced. Be aware that increasing this number will also increase the used storage.

    Default: 30,000

    Maximum: 100,000
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Threshold CPU Time
    
    </td>
    <td valign="top">
    
    Specify the threshold CPU time of statement execution.

    When set to 0, all SQL statements are traced.

    Default: 0
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Threshold Memory
    
    </td>
    <td valign="top">
    
    Specify the threshold memory usage of statement execution.

    When set to 0, all SQL statements are traced.

    Default: 1,024MB

    Maximum: 1 GB
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Threshold Duration
    
    </td>
    <td valign="top">
    
    Specify the threshold execution time.

    When set to 0, all SQL statements are traced.

    Default: 50000 Microseconds
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Trace Parameter Values
    
    </td>
    <td valign="top">
    
    In SQL statements, field values may be specified as parameters \(using a "?" in the syntax\). If these parameter values are not required, then do not select the option to reduce the amount of data traced.

    Default: False
    
    </td>
    </tr>
    </table>
    
    If expensive statement tracing is not enabled, then statement information and errors are not traced and you cannot see them in the *System Monitor* \(see [Monitoring SAP Datasphere](monitoring-sap-datasphere-28910cd.md)\).

    For more information about these parameters, see [Expensive Statements Trace](https://help.sap.com/viewer/f9c5015e72e04fffa14d7d4f7267d897/latest/en-US/5faf04f17830464eacdb7938b383d2ab.html) in the *SAP HANA Cloud, SAP HANA Database Administration Guide*.

4.  To analyze individual SAP HANA multi-dimensional services \(MDS\) queries, select *Enable MDS Information Tracing* and save.


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
    
    MDS Tracing Records
    
    </td>
    <td valign="top">
    
    Specify the maximum number of records that are stored for MDS requests in the monitoring tables.

    You can increase this number in order to trace more data in the *System Monitor*. 

    Default \(max\): 100,000
    
    </td>
    </tr>
    </table>
    
    If the tracing is enabled, you can view information on MDS queries when clicking *More* in the column *Statement Details* of the *Statement Logs* tab in the *System Monitor* \(see [Monitoring SAP Datasphere](monitoring-sap-datasphere-28910cd.md)\).

5.  To trace elastic compute node data, select *Enable Elastic Compute Node Data Tracing* and save.
    -   If the tracing is disabled, only the statements of currently running nodes are displayed in the *System Monitor*. If a node is stopped, its information is deleted.
    -   If the tracing is enabled and a node is started and stopped more than once, only the information about the previous run is displayed. The information is kept for 10 days or is deleted if more than 100 individual elastic compute nodes have run.


