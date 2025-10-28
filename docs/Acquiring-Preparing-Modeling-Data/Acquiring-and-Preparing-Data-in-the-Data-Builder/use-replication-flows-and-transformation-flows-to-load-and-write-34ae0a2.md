<!-- loio34ae0a2ea6e94483b19f632a2843d56d -->

# Use Replication Flows and Transformation Flows to Load and Write Data

Load, transform and write data to local tables with a combination of replication flow and transformation flow instead of using a data flow.

Replication flows \(offering improved connectivity and delta load processing\) and transformation flows \(offering many more transform capabilities\) are now the preferred ways to load and write data to local tables in SAP Datasphere, including in the object store.

When your data flow is eligible to be converted into a transformation flow or a combination of replication flow and transformation flow, you can see an information banner in the Data Flow editor.



<a name="loio34ae0a2ea6e94483b19f632a2843d56d__section_dhq_5wl_bgc"/>

## Use Replication Flows to Load and Write Data in Local Tables

Compared to a data flow, a replication flow offers many more possibilities, such as improved connectivity and delta load processing. You can also store the data inexpensively in file spaces in the SAP Datasphere object store. For more information, see [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md)



<a name="loio34ae0a2ea6e94483b19f632a2843d56d__section_zbb_1xl_bgc"/>

## Use Transformation Flows to get Additional Transformation Capabilities

Compared to a data flow, a transformation flow offers additional transformation capabilities. You can also prepare the data using Apache Spark transformation flows. For more information, see [Creating a Transformation Flow](../creating-a-transformation-flow-f7161e6.md) and [Creating a Transformation Flow in a File Space](creating-a-transformation-flow-in-a-file-space-b917baf.md).



<a name="loio34ae0a2ea6e94483b19f632a2843d56d__section_vdn_tlf_lgc"/>

## Data Flows, Replication Flows and Transformation Flows Comparison

The table below compares the main functionalities between *Data Flow*, *Replication Flow* and *Transformation Flow*. Refer to the dedicated documentation of each editor for a complete overview.


<table>
<tr>
<th valign="top">

 

</th>
<th valign="top">

*Data Flow*

</th>
<th valign="top">

*Replication Flow*

</th>
<th valign="top">

*Transformation Flow*

</th>
</tr>
<tr>
<td valign="top">

Supported Sources

</td>
<td valign="top">

SAP and non-SAP systems

</td>
<td valign="top">

SAP and non-SAP systems

</td>
<td valign="top">

SAP Datasphere only: It processes data from one local table to another local table

</td>
</tr>
<tr>
<td valign="top">

Supported Targets

</td>
<td valign="top">

Local table in SAP Datasphere only

</td>
<td valign="top">

SAP and non-SAP systems

</td>
<td valign="top">

SAP Datasphere only: It processes data from one local table to another local table

</td>
</tr>
<tr>
<td valign="top">

Data Load Types

</td>
<td valign="top">

Initial, Batch load

</td>
<td valign="top">

Initial Only, Initial and Delta, Delta Only

</td>
<td valign="top">

Initial Only and Initial and Delta

</td>
</tr>
<tr>
<td valign="top">

Supported Storage within SAP Datasphere \(Space or File Space\). See [Creating Spaces and Allocating Resources](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/2ace657356d54199b0b87d2327b1a70b.html "Users with an administrator role can create spaces and allocate resources to them.") :arrow_upper_right:

</td>
<td valign="top">

SAP HANA Database \(Disk and In-Memory\)

</td>
<td valign="top">

SAP HANA Database \(Disk and In-Memory\) or SAP HANA Data Lake Files \(Object Store\)

</td>
<td valign="top">

SAP HANA Database \(Disk and In-Memory\) or SAP HANA Data Lake Files \(Object Store\)

</td>
</tr>
<tr>
<td valign="top">

Parallelized Data Load and Scalability

</td>
<td valign="top">

Partial

</td>
<td valign="top">

Yes. Replication flow supports parallelization during initial load through partitioning to achieve a parallelized data load.

See [Replication Flow Blog Series Part 4 - Sizing](https://community.sap.com/t5/technology-blogs-by-sap/replication-flow-blog-series-part-4-sizing/ba-p/13579486)

</td>
<td valign="top">

Yes. You can define batches \(in the Flows monitor detail screen\) to divide large datasets.

</td>
</tr>
<tr>
<td valign="top">

Operators and Transform Capabilities

</td>
<td valign="top">

Join, Union, Projection, Calculated Column, Agregation, Pyhton script.

</td>
<td valign="top">

Projections and filters, for example adding, adjusting and removal of columns as well as the ability to provide row-level filters on one or multiple objects

</td>
<td valign="top">

Join, Aggregation, Filter, Projection, Calculated Columns, Phyton script

</td>
</tr>
<tr>
<td valign="top">

Data Recovery

</td>
<td valign="top">

No. When data flow runs fail, they restart from the beginning. However, users can select the *Automatic Restart on Failure* in the *Advanced Properties*.

</td>
<td valign="top">

Yes. If a replication flow run fails, it restarts where it failed. You can also pause/resume a replication flow, at the replication flow level or at an individual object level.

</td>
<td valign="top">

No

</td>
</tr>
</table>

For more information, see [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md),[Creating a Transformation Flow](../creating-a-transformation-flow-f7161e6.md) and [Creating a Transformation Flow in a File Space](creating-a-transformation-flow-in-a-file-space-b917baf.md).

