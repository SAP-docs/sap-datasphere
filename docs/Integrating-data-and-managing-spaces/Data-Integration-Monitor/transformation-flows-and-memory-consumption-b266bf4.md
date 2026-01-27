<!-- loiob266bf41f3e845b68519fca2b399a2c0 -->

# Transformation Flows and Memory Consumption

You want to run a transformation flow and consider how it affects the memory consumption.

When you run a transformation flow, all the data that is provided by the transformation flow is stored in SAP Datasphere. When the transformation flow is complex and consume a lot of data, some intermediate results have also to be stored in the memory so that they can be used as source for further calculations and subsequent transformation flow. The amount of memory that is needed for the runtime of the overall scenario can exceed the memory resources, and thus an out of memory exception is raised or the memory consumption is very high.



## Monitoring and Managing Memory Consumption

If your transformation flow is very complex, using remote or shared sources, you might get an out-of-memory error while running it. Several features allow you to manage memory consumption before or after a run:



### Monitor Memory Consumption

-   Analyze system memory usage and allocation limits using system monitoring tools. See [Monitoring SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/28910cded17a42a0bf16225309cb8bf6.html "Users with an administrator role have access to various monitoring logs and views and can, if necessary, create database analysis users to help troubleshoot issues.") :arrow_upper_right:.
-   Analyze your flow with the running tools providing the necessary information to optimize your data model when an out-of-memory error happens. See [Explore Transformation Flows](explore-transformation-flows-7588192.md).
-   Monitor your disk space using the SAP HANA Cockpit to check disk statistics to check that there’s enough space on disk for data volumes and log volumes. See [Disk Usage: Monitor Disk Volume](https://help.sap.com/docs/SAP_HANA_COCKPIT/afa922439b204e9caf22c78b6b69e4f2/5c947a6a2f0f4c3b95a9628d4441bd18.html).



### Manage Memory Consumption

-   Configure workload class limitations to optimize resource allocation without triggering OOM events. See [Set Priorities and Statement Limits for Spaces or Groups](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d66ac1efb5054068a104c4559b72d272.html "Prioritize between spaces or groups for resource consumption and set limits to the amount of memory and threads that a space or group can consume when processing statements.") :arrow_upper_right:.
-   Change the run mode for a transformation flow and choose between performance and memory consumption. See [Change the Run Mode for a Transformation Flow](change-the-run-mode-for-a-transformation-flow-f7da029.md).
-   Reclaim space by reclaiming freed log segments and unused space in data volumes. See [Reclaim Space](https://help.sap.com/docs/SAP_HANA_COCKPIT/afa922439b204e9caf22c78b6b69e4f2/77c0de2ecc2741758b12e22feffb8db6.html).



## Out-of-Memory Errors

There are a few reasons you may receive an out-of-memory error when trying to run a transformation flow:



### Types of Out-Of-Memory Errors


<table>
<tr>
<th valign="top">

Out-of-Memory Category

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Query

</td>
<td valign="top">

Receive an out-of-memory error if your transformation flow is too complex. Check your transformation flow to make sure you have enough memory.

Optimize your model and improve memory consumption of your transformation flow.

</td>
</tr>
<tr>
<td valign="top">

Composite Level

</td>
<td valign="top">

You can receive an out-of-memory error when you are running too many tasks simultaneously. Although your system and transformation flow may have sufficient memory, HANA distributes memory across your work environment. Make sure to distribute your work such as scheduling tasks and running task chains and transformation flows. Check your system monitor to look at your workload distribution.

</td>
</tr>
</table>



### Out-of-Memory Limitations


<table>
<tr>
<th valign="top">

Out-of-Memory Limitations

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

Workload Class

</td>
<td valign="top">

SAP HANA workload management allows optimization of system performance through defined limits on memory and CPU resources. Exceeding these limits, such as the statement thread limit or statement memory limit defined within a workload class, can lead to OOM situations.

Proper configuration of these limitations is crucial to avoid errors indicating memory limit violations.

</td>
</tr>
</table>

> ### Note:  
> This is not an exhaustive list of reasons out-of-memory limitations, but a list of some of the main examples.

