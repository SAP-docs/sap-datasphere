<!-- loio6e9ba26e11dc4062801c1dfcbf9a1072 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Analyze View Performance in Data Builder

Analyze the performance of a view directly in *Data Builder* with the *Runtime Metrics* tool in the toolbar. Receive detailed information about your view and generate an Explain Plan directly in the *Data Builder* or choose to go directly into *View Analyzer* to improve the performance of your view.



## Context

The *Runtime Metrics* tool helps analyze the performance of your view by executing two benchmark queries on a view and measuring their runtime and consumed peak memory. Additionally, the lineage of the view is analyzed to determine the performance through important indications such as the number of sources, number of federated remote tables, and the number of local tables \(file\).

> ### Note:  
> A view must be fully deployed to run the performance analysis. Parameters with default values will be supported.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary. Select the view you want to analyze the performance of.

    -   The *Runtime Metrics* tool can be accessed from the *Data Builder* toolbar.
    -   The *Runtime Metrics* tool can be used in both Graphical and SQL views.

2.  Click on the <span class="SAP-icons-V5"></span> \(Runtime Metrics\) icon in the toolbar.

3.  Click *Run* to execute the performance analysis and receive runtime metrics.

4.  \[optional\] Click on *Generate Explain Plan* or *Open View Analyzer* if you want more information to help optimize your view.

5.  \[optional\] Click on the <span class="SAP-icons-V5"></span> \(Runtime Metrics\) icon in the toolbar again after making any changes to your model. This will show comparative metrics of your last two runs.




<a name="loio6e9ba26e11dc4062801c1dfcbf9a1072__result_km5_5pt_z2c"/>

## Results

****


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

Select \* from View Limit 1000

</td>
<td valign="top">

A database query that selects 1000 records from a view. This is a query to retrieve runtime metrics to evaluate the performance of a view.

</td>
</tr>
<tr>
<td valign="top">

Duration

</td>
<td valign="top">

The duration of the Select \* From View Limit 1000 query run measured in seconds.

</td>
</tr>
<tr>
<td valign="top">

Peak Memory

</td>
<td valign="top">

Peak memory usage of the run of the query Select \* From View Limit 1000.

</td>
</tr>
<tr>
<td valign="top">

Select Count \* From View

</td>
<td valign="top">

A database query to get the number of records of a view. This is a query to retrieve runtime metrics to evaluate the performance of a view.

</td>
</tr>
<tr>
<td valign="top">

Duration

</td>
<td valign="top">

The duration of the Select Count \* From View query run measured in seconds.

</td>
</tr>
<tr>
<td valign="top">

Peak Memory

</td>
<td valign="top">

Peak memory usage of the run of the query Select Count \* From View.

</td>
</tr>
<tr>
<td valign="top">

Number of Rows

</td>
<td valign="top">

Shows the number of rows contained in the view.

</td>
</tr>
<tr>
<td valign="top">

Number of Overall Sources

</td>
<td valign="top">

Shows the number of sources contained in the view.

</td>
</tr>
<tr>
<td valign="top">

Data Access

</td>
<td valign="top">

Shows how you currently access your view.

-   *Persisted*: The view is persisted can be used immediately.
-   *Partially Persisted*: Not all view data has been persisted. If your view contains an input parameter, only records that match the input parameter default value are persisted.
-   *Virtual*: The view is accessed directly, no intermediate persistence is used. Or the view was persisted and has now been turned into virtual to free up memory space, for example.



</td>
</tr>
<tr>
<td valign="top">

Local Tables \(File\)

</td>
<td valign="top">

Shows the number of number of local tables \(file\).

</td>
</tr>
<tr>
<td valign="top">

Federated Remote Tables \(with Limited Adapter Capabilities\)

</td>
<td valign="top">

Shows the number of federated remote tables \(with limited adapter capabilities\).

</td>
</tr>
<tr>
<td valign="top">

Generate Explain Plan

</td>
<td valign="top">

Click *Generate Explain Plan* to generate and download the Explain Plan for a select statement on the view. You must have either the scoped role **DW Administrator** or an additional custom role that includes **Data Warehouse Runtime \(Read\)** privilege. privilege to generate the Explain Plan. For more information see, [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

Open View Analyzer

</td>
<td valign="top">

Click *Open View Analyzer* to navigate to the *View Analyzer* feature in the *Data Integration Monitor*. You need *DWC Data Integration \(Runtime\)* privilege to open the *View Analyzer*. For more information see, [Getting Started with View Analyzer](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/e0aeddba00b14be29b5e49b47001d43b.html "Use the View Analyzer to explore graphical or SQL views and the entities they consume.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

Cancel

</td>
<td valign="top">

Click *Cancel* to cancel the runtime query.

</td>
</tr>
</table>

The metrics of the last two runs will be shown to help evaluate changes in the performance of your view.

> ### Note:  
> The *Runtime Metrics* tool will take time. The overall runtime is higher than the runtime of the two queries independently. This is due to the analysis of the metadata required to get the runtime metric indicators.

> ### Note:  
> To get peak memory indicators, you must enable *Expensive Statement Tracing* in :wrench:. For more information, see [Configure Monitoring](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/9cd0691c44a74f2aa47b52f615f74433.html "You can control which monitoring data is collected and also obtain independent access to the underlying SAP HANA monitoring views that power the System Monitor.") :arrow_upper_right:.

