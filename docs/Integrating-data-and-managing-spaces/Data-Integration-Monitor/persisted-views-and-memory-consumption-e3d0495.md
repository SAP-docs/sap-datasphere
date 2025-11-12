<!-- loioe3d04951a4a344c28b25b2b1b13bf3d8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Persisted Views and Memory Consumption

You want to persist a complex view and consider how it affects the memory consumption.

When you persist a view, all the data that is provided by the view is stored in SAP Datasphere. When the view is complex and consume a lot of data, some intermediate results have also to be stored in the memory so that they can be used as source for further calculations and subsequent views. The amount of memory that is needed for the runtime of the overall scenario can exceed the memory resources, and thus an out of memory exception is raised or the memory consumption is very high.



<a name="loioe3d04951a4a344c28b25b2b1b13bf3d8__section_kvs_jyh_rwb"/>

## Reducing Memory Consumption while Persisting Complex Views

If your view is very complex, using other views or remote tables, you might get an out of memory or increase the memory consumption in SAP HANA Cloud while persisting it.

You might need to think about the following steps before persisting the view:

-   Persist intermediate views: Identify views that combine a lot of data and are perhaps also used in other scenarios. These views might read data from different sources and combine them. The memory consumption could already be quite high, and the result of the view may have to be stored as intermediate result in the memory. If this view is persisted, then the top views that do also heavy calculations can be optimized: They reach out directly to the same SAP HANA instance and no additional memory for the pre-calculations is needed. It could also be a good idea to split the large view into two or several smaller views, and to persist these smaller views first. In most cases, the data persistence on a deeper level in the view graph is more effective than just persisting the top view, because the data retrieval and the calculations can be optimized if internal SAP HANA tables can be used. You might need to consider the *View Analyzer* to check the memory consumptions and to identify views that can be optimized. For more information, see [Exploring Views with View Analyzer](exploring-views-with-view-analyzer-8921e5a.md).
-   Partition your data: While partitioning your data, not all the data is retrieved and stored at once in the persisted views: The data is divided into several batches \(partitions\). Each partition is retrieved and stored on its own, and thus consume less memory. For more information, see [Creating Partitions for Your Persisted Views](creating-partitions-for-your-persisted-views-9b1b595.md).
-   Handling of remote tables: The memory consumption can increase with usage of remote tables, especially when filters used in the view definition can't be pushed down to remote tables. Make sure that the statistics for the remote tables are up to date. If the remote tables are part of joins or aggregations are existing, then statistics could optimize the data retrieval. The statistics can be run from the *Remote Queries* \> *Remote Tables Statistics*. For more information, see [Creating Statistics for Your Remote Tables](creating-statistics-for-your-remote-tables-e4120bb.md).

    You can check the SQL statement that is used to retrieve the data for a remote source in *Remote Queries*. For more information, see [Monitoring Remote Queries](monitoring-remote-queries-806d7f0.md). If the needed filter condition is not part of the SELECT statement, then the filter is applied on all the data. This leads to a higher memory consumption and a performance decrease. It might be a solution to replicate the data for some remote tables where the data does not change regularly, for example master data tables. You can also try to persist views that just do basic joins/unions on some remote tables, and are used in more than one view. If these remote tables and views are persisted, then the data retrieval for other scenarios is highly improved in terms of memory consumption and performance, because the top views can use tables in the same SAP HANA instance.

-   You can change the run mode of your data persistence and choose between performance and memory consumptions. For more information, see [Data Persistence and Run Mode](data-persistence-and-run-mode-d04f5dd.md).



<a name="loioe3d04951a4a344c28b25b2b1b13bf3d8__section_jfs_3sx_5sb"/>

## Monitoring Memory Consumption While Persisting Views

Persisting views can consume a lot of memory and it might be useful to keep an eye on memory figures that are stored with task logs.

You can monitor memory consumption in the task logs if you switch on the option *Expensive Statement Tracing* \(under <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*\).

> ### Note:  
> -   The memory consumption is measured at runtime only.
> 
> -   The memory and disk size consumed by the data persistence table are not available on partition-level, but only for the entire table.

You can also use SAP HANA Views:

-   [M\_EXPENSIVE\_STATEMENT](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/2021_4_QRC/en-US/20af736e751910148162e2ab1982f035.html): This view provides all statements, for which memory consumption, CPU time or duration exceed the corresponding specified thresholds. For more information, see [Configure Monitoring](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/9cd0691c44a74f2aa47b52f615f74433.html "You can control which monitoring data is collected and also obtain independent access to the underlying SAP HANA monitoring views that power the System Monitor.") :arrow_upper_right:

-   Memory consumed during insert statements can be tracked using the view: [M\_ACTIVE\_PROCEDURES](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/2021_4_QRC/en-US/f3d23305d0dd495590e0061c3546de9a.html).

For more information on how to use system view, see [Working with SAP HANA Monitoring Views](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/4ab45090c5684ebf8765757a1dfc4e5d.html "You can obtain independent access to the underlying SAP HANA monitoring views that power the System Monitor to do additional analysis on them and visualize them in SAP Analytics Cloud.") :arrow_upper_right:.



<a name="loioe3d04951a4a344c28b25b2b1b13bf3d8__section_ihh_flw_42c"/>

## Out-of-Memory Errors

An out-of-memory event occurs when HANA is unable to persist a view. There are a few reasons you may receive an out-of-memory error when trying to persist a view:

****


<table>
<tr>
<th valign="top">

Out of Memory Category

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Query Level

</td>
<td valign="top">

Receive an out-of-memory error if your view is too complex. Check your view to make sure you have enough memory. Run *View Analyzer* to optimize your model and improve memory consumption of your view.

For more information see, [Getting Started with View Analyzer](getting-started-with-view-analyzer-e0aeddb.md).

</td>
</tr>
<tr>
<td valign="top">

Composite Level

</td>
<td valign="top">

You can receive an out-of-memory error when you are running too many tasks simultaneously. Although your system and view may have sufficient memory, HANA distributes memory across your work environment. Make sure to distribute your work such as scheduling tasks and running task chains and transformation flows. Check your system monitor to look at your workload distribution.

</td>
</tr>
</table>

Out of Memory Limitations -

****


<table>
<tr>
<th valign="top">

Out of Memory Limitation

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Global Allocation Limit

</td>
<td valign="top">

The global allocation limit is a predefined maximum for system-wide memory allocation. When this limit is reached, a global allocation limit OOM event occurs, leading to aborted statements or data ejection from memory to manage the situation.

</td>
</tr>
<tr>
<td valign="top">

Statement Memory Limit

</td>
<td valign="top">

The statement memory limit restricts the memory allocated for specific SQL statements. When a statement surpasses this limit, it results in a statement memory limit OOM event, commonly due to complex queries requiring excessive memory.

</td>
</tr>
<tr>
<td valign="top">

Workload Class Limitations

</td>
<td valign="top">

SAP HANA workload management allows optimization of system performance through defined limits on memory and CPU resources. Exceeding these limits, such as the statement thread limit or statement memory limit defined within a workload class, can lead to OOM situations.

Proper configuration of these limitations is crucial to avoid errors indicating memory limit violations.

</td>
</tr>
</table>

> ### Note:  
> This is not an exhaustive list of reasons out of memory limitations, but a list of some of the main examples.

Preventing and Managing Out of Memory Situations

-   Regularly analyze system memory usage and allocation limits using system monitoring tools. For more information see, [Monitoring SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/28910cded17a42a0bf16225309cb8bf6.html "Users with an administrator role have access to various monitoring logs and views and can, if necessary, create database analysis users to help troubleshoot issues.") :arrow_upper_right:.
-   Carefully configure workload class limitations to optimize resource allocation without triggering OOM events. For more information see, [Set Priorities and Statement Limits for Spaces or Groups](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d66ac1efb5054068a104c4559b72d272.html "Prioritize between spaces or groups for resource consumption and set limits to the amount of memory and threads that a space or group can consume when processing statements.") :arrow_upper_right:.
-   Run View Analyzer to optimize your model and improve memory consumption of your view. For more information see, [Getting Started with View Analyzer](getting-started-with-view-analyzer-e0aeddb.md).

