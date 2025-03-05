<!-- loio6b2d0073a8684ee6a59d6f47d00ec895 -->

# Monitoring Local Tables \(File\)

Monitor your local tables \(file\). Check how and when they were last updated and if new data has still to be merged.

> ### Note:  
> The object store is not enabled by default in SAP Datasphere tenants. To enable it in your tenant, see SAP note [3525760](https://me.sap.com/notes/3525760).
> 
> For additional information on working with data in the object store, see SAP Note [3538038](https://me.sap.com/notes/3538038).
> 
> The object store cannot be enabled in SAP Datasphere tenants provisioned prior to version 2021.03. To request the migration of your tenant, see SAP note [3268282](https://me.sap.com/notes/3268282).

Local tables can be used as source data or target data by SAP Datasphere apps. As a Data Integrator you might want to monitor all local tables \(file\) deployed in your space and check how and when data has been last updated and if some data must still be merged.

Go to *Data Integration Monitor* \> *Local Tables \(Files\)*. All local tables \(file\) that have been created in the *Data Builder* are listed. For more information on local tables \(file\), see [Creating a Local Table (File)](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/d21881b121bc4703861be6ead4aea2ab.html "Create a local table (file) to store data in the object store. Load data to your local table (file) via replication flows and transform the data with transformation flows.") :arrow_upper_right:.

The monitor displays the following properties:


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

*Technical Name*or *Business Name*

</td>
<td valign="top">

Displays the technical name or the business name of the table, depending on how you have configured your UI settings in *Your Profile* \> *Settings*.

</td>
</tr>
<tr>
<td valign="top">

*Buffer Merge Status*

</td>
<td valign="top">

Status of the data merge.

Data updates are waiting in the Inbound Buffer until they are merged.

They can have the following status:

-   Running: a merge task is still running.
-   Failed: Last merge run task has failed. You might need to check the log for more details.
-   Merged: All data have been merged with the last merge task.
-   New Data: Data are waiting to be merged.
-   Empty: There is no new data waiting in the inbound buffer.



</td>
</tr>
<tr>
<td valign="top">

*Last updated*

</td>
<td valign="top">

Displays the timestamp when the local table \(file\) was last updated.

</td>
</tr>
<tr>
<td valign="top">

*Last updated by*

</td>
<td valign="top">

Indicates how the local table \(file\) was last updated. For example, name of the task chain that updated it.

</td>
</tr>
<tr>
<td valign="top">

*Buffer Last Updated*

</td>
<td valign="top">

Displays the timestamp when the inbound buffer was last updated by a replication flow.

</td>
</tr>
<tr>
<td valign="top">

*Buffer Last Updated by*

</td>
<td valign="top">

Indicates the name of the replication flow that last updated the inbound buffer.

</td>
</tr>
<tr>
<td valign="top">

*Delta capture*

</td>
<td valign="top">

Indicates if the local table \(file\) allows delta capture. For more information, see [Capturing Delta Changes in Your Local Table](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/154bdffb35814d5481d1f6de143a6b9e.html "Track the changes that will be made later on your local table after you have deployed it.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

*Partitions*

</td>
<td valign="top">

Indicates if the local table \(file\) contains partitions.

</td>
</tr>
</table>

