<!-- loio6e9ba26e11dc4062801c1dfcbf9a1072 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Analyzing View Performance

Analyze the performance of a view directly in the *Data Builder* with the *Runtime Metrics* tool. Receive detailed information about your view by creating runtime metrics, creating an Explain Plan directly or starting the *View Analyzer* to improve the performance of your view.



## Context

The *Runtime Metrics* tool helps analyze the performance of your view by executing two benchmark queries on a view and measuring their runtime and consumed peak memory. Additionally, the lineage of the view is analyzed to determine the performance through important indications such as the number of sources, number of federated remote tables, and the number of local tables \(file\). You can review the metrics of your entire view or refine your metrics to look at only the metrics for remote statements.

> ### Note:  
> A view must be fully deployed to run the performance analysis. Views with parameters can be analyzed only if all parameters have default values.

> ### Note:  
> To get peak memory indicators, you must enable *Expensive Statement Tracing* in :wrench:. For more information, see [Configure Monitoring](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/9cd0691c44a74f2aa47b52f615f74433.html "You can control which monitoring data is collected and also obtain independent access to the underlying SAP HANA monitoring views that power the Monitoring app.") :arrow_upper_right:.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary. Select the view you want to analyze the performance of.

    -   The *Runtime Metrics* tool can be accessed from the *Data Builder* toolbar.
    -   The *Runtime Metrics* tool can be used in both Graphical and SQL views.

2.  Click on the <span class="SAP-icons-V5"></span> \(Runtime Metrics\) icon in the toolbar.

3.  From the drop down menu, click *Create Runtime Metrics*.

4.  Click *Start Run* to begin the performance analysis.

5.  \[optional\] Click on *Start View Analyzer* if you want more information to help optimize your view.

6.  \[optional\] Click on the <span class="SAP-icons-V5"></span> \(Runtime Metrics\) icon in the toolbar and *Create Runtime Metrics* again after making any changes to your model. This will show comparative metrics of your last two runs.




<a name="loio6e9ba26e11dc4062801c1dfcbf9a1072__result_km5_5pt_z2c"/>

## Results

**Main View**


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

Time

</td>
<td valign="top">

Shows the date and time of the latest run and the previous run.

</td>
</tr>
<tr>
<td valign="top">

Duration \(Statement Type: Select 1000 Rows\)

</td>
<td valign="top">

The duration of the Select \* From View Limit 1000 query run measured in seconds.

</td>
</tr>
<tr>
<td valign="top">

Peak Memory \(Statement type: Select 1000 Rows\)

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

Duration \(Statement Type: Count All Rows\)

</td>
<td valign="top">

The duration of the Select Count \* From View query run measured in seconds.

</td>
</tr>
<tr>
<td valign="top">

Peak Memory \(Statement Type: Count All Rows\)

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

Overall Number of Sources

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

Start Run

</td>
<td valign="top">

Click *Start Run* to start runtime metrics run.

</td>
</tr>
<tr>
<td valign="top">

Cancel Run

</td>
<td valign="top">

Click *Cancel Run* to cancel the current runtime metrics run.

</td>
</tr>
<tr>
<td valign="top">

Start View Analyzer

</td>
<td valign="top">

Click *Start View Analyzer* to navigate to the *View Analyzer* feature in the *Data Integration Monitor*. You need *DWC Data Integration \(Runtime\)* privilege to open the *View Analyzer*. For more information see, [Getting Started with View Analyzer](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e0aeddba00b14be29b5e49b47001d43b.html "Use the View Analyzer to explore graphical or SQL views and the entities they consume.") :arrow_upper_right:.

</td>
</tr>
</table>

The metrics of the last two runs will be shown to help evaluate changes in the performance of your view.

**Remote Statements**


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

Remote Tables

</td>
<td valign="top">

Shows the names of the entities that a remote query accessed. A query can reference one or multiple entities, depending on the available features of the underlying connection type. The remote statement type can be identified by the icon on the left side beside the name.

There are three types of remote statements that do not have an icon:

-   The term *Undetermined* is shown when the analysis of the remote query could not identify which modeling entity is accessed.
-   The term *Join Relocation*is shown when advanced HANA Cloud optimizations are applied. See [https://help.sap.com/docs/hana-cloud-database/sap-hana-cloud-sap-hana-database-data-access-guide/remote-join-relocation](https://help.sap.com/docs/hana-cloud-database/sap-hana-cloud-sap-hana-database-data-access-guide/remote-join-relocation) in *SAP HANA Cloud, SAP HANA Database Data Access Guide* for more information.
-   The term *Temporary Table* is shown if a view, when processing saved an intermediate result into a temporary table.



</td>
</tr>
<tr>
<td valign="top">

Space

</td>
<td valign="top">

Shows the name of the space that the remote table is in.

</td>
</tr>
<tr>
<td valign="top">

Connection

</td>
<td valign="top">

Shows the name of the connection the remote statement used.

> ### Note:  
> The connection name is not available for Local Table \(File\) entities.



</td>
</tr>
<tr>
<td valign="top">

Statement Type

</td>
<td valign="top">

Shows the statement type: Count all rows or Count 1000 rows. You can choose from the tabs above the table to view:

-   *All* - View all remote tables
-   *Statement Type: 1000 Rows*: View only remote tables labeled as "Select 1000 rows".
-   *Statement Type: Count All*: View only remote tables labeled as "Count all rows".



</td>
</tr>
<tr>
<td valign="top">

Start Time

</td>
<td valign="top">

Shows the date and time the latest remote processing started.

</td>
</tr>
<tr>
<td valign="top">

End Time

</td>
<td valign="top">

Shows the date and time the latest remote processing ended.

</td>
</tr>
<tr>
<td valign="top">

Duration

</td>
<td valign="top">

Shows the duration of the latest run of the remote statement on the tenant database.

</td>
</tr>
<tr>
<td valign="top">

Rows

</td>
<td valign="top">

Shows the number of rows transferred from the remote system.

</td>
</tr>
<tr>
<td valign="top">

Size \(MiB\)

</td>
<td valign="top">

Shows the size of the data exchange on protocol level during execution of the remote statement.

</td>
</tr>
<tr>
<td valign="top">

Open Remote Query Monitor

</td>
<td valign="top">

Click *Open Remote Query Monitor* above the table to go directly to the *Remote Queries Monitor*. See [Monitoring Remote Queries](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/806d7f0c45a14f1fb07db0a226b2b822.html "In the Remote Queries monitor, you track the queries sent to your remote connected source systems for your space. You can monitor the communication between the federation layer of SAP HANA Cloud and the connected remote source systems, and analyze them.") :arrow_upper_right:.

> ### Note:  
> The remote query monitor will only display remote statements in the space you are working in.

> ### Note:  
> Make sure you have the correct privileges to monitor remote queries. See details in the linked documentation.



</td>
</tr>
<tr>
<td valign="top">

Start Run

</td>
<td valign="top">

Click *Start Run* to start runtime metrics run.

</td>
</tr>
<tr>
<td valign="top">

Cancel Run

</td>
<td valign="top">

Click *Cancel Run* to cancel the current runtime metrics run.

</td>
</tr>
<tr>
<td valign="top">

Start View Analyzer

</td>
<td valign="top">

Click *Start View Analyzer* to navigate to the *View Analyzer* feature in the *Data Integration Monitor*. You need *DWC Data Integration \(Runtime\)* privilege to open the *View Analyzer*. For more information see, [Getting Started with View Analyzer](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e0aeddba00b14be29b5e49b47001d43b.html "Use the View Analyzer to explore graphical or SQL views and the entities they consume.") :arrow_upper_right:.

</td>
</tr>
</table>

> ### Note:  
> The *Runtime Metrics* tool will take time. The overall runtime is higher than the runtime of the two queries independently. This is due to the analysis of the metadata and the retrieval of runtime data of the tenant database required to get the runtime metric indicators.

> ### Note:  
> The values in the columns: Start Time, End Time, Duration, Rows and Size are taken directly from HANA remote monitoring view. See [https://help.sap.com/docs/hana-cloud-database/sap-hana-cloud-sap-hana-database-sql-reference-guide/m-remote-statements-system-view](https://help.sap.com/docs/hana-cloud-database/sap-hana-cloud-sap-hana-database-sql-reference-guide/m-remote-statements-system-view) in the *SAP HANA Cloud, SAP HANA Database SQL Guide* .

> ### Note:  
> Lineage objects with remote tables with input parameters cannot be analyzed as source objects.

