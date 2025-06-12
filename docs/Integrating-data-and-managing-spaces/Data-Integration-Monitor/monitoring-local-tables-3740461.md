<!-- loio374046156e5b47599fc9b96c8c3a4dce -->

# Monitoring Local Tables

Monitor all the local tables created for a space in the *Data Builder* and check their metrics.



<a name="loio374046156e5b47599fc9b96c8c3a4dce__section_fml_rfb_t2c"/>

## Prerequisites

To monitor local tables, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.


The *DW Integrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio374046156e5b47599fc9b96c8c3a4dce__section_ljm_3y1_t2c"/>

## Monitoring Local Tables

Local tables can be used as source data or target data by SAP Datasphere apps. As a Data Integrator you might want to monitor all local tables which have been created in the current space to check data size, updates in these tables, etc.

Go to *Data Integration Monitor* \> *Local Tables*. All local tables that have been created in the *Data Builder* are listed.

> ### Note:  
> Tables created in Open SQL schemas are not listed. For more information, see [Integrating Data via Database Users/Open SQL Schemas](../Integrating-Data-Via-Database-Users/Open-SQL-Schema/integrating-data-via-database-users-open-sql-schemas-3de55a7.md).

The monitor displays the following properties:


<table>
<tr>
<th valign="top">

Properties

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

*Number of records*

</td>
<td valign="top">

Indicates the number of records contained in the table.

</td>
</tr>
<tr>
<td valign="top">

*Growth in 30 Days*

</td>
<td valign="top">

Displays the growth in % of the number of records since the last month. It is computed by taking the difference between the number of records in the table today and the number of records in the table 30 days ago, and it calculates the growth in percentage.

> ### Note:  
> Figures are only available for large tables \(superior of 1 megabyte\). It takes the value N/A if the table is smaller than 1 megabyte and O if no changes have been made during the month.



</td>
</tr>
<tr>
<td valign="top">

*Size on Disk \(MiB\)*

</td>
<td valign="top">

Displays the disk storage currently used by the local table in MiB.

> ### Note:  
> Value is set to Not Applicable for local tables that store data in-memory.



</td>
</tr>
<tr>
<td valign="top">

*Size in-Memory \(MiB\)*

</td>
<td valign="top">

Displays the memory currently used by the local table in MiB.

> ### Note:  
> Value is set to Not Applicable for local tables that store data on disk.



</td>
</tr>
<tr>
<td valign="top">

*Last updated*

</td>
<td valign="top">

Displays the timestamp when the local table was last updated.

> ### Restriction:  
> If the local table is updated through a replication flow, the information is not available if the flow is running via the load type *Initial and Delta*.



</td>
</tr>
<tr>
<td valign="top">

*Last updated by*

</td>
<td valign="top">

Indicates how the table was last updated. For example, name of the flow if it was updated by a flow.

> ### Note:  
> If you are authorized to navigate to the relevant object, a clickable link is provided and you can navigate to the object details. If you are not authorized to navigate to the object, you’ll get the value unauthorized.

> ### Restriction:  
> If the local table is updated through a replication flow, the information is not available if the flow is running via the load type *Initial and Delta*.



</td>
</tr>
<tr>
<td valign="top">

*Number of partitions*

</td>
<td valign="top">

Displays the number of partitions defined on the local table.

> ### Note:  
> Displays 0 if no partitions have been defined on the local table. For more information, see [Partitioning Local Tables](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/03191f36e9144b2aaa47b8c9eea039c1.html "Create partitions for your local table to break your data down into smaller tables, and better manage tables with large volume of data.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

*Delta capture*

</td>
<td valign="top">

Indicates if the local table allows delta capture. For more information, see [Capturing Delta Changes in Your Local Table](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/154bdffb35814d5481d1f6de143a6b9e.html "Track the changes that will be made later on your local table after you have deployed it.") :arrow_upper_right:.

</td>
</tr>
</table>

