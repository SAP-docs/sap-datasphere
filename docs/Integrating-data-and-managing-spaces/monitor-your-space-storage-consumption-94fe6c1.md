<!-- loio94fe6c13f6a340288cd50ee355566591 -->

# Monitor Your Space Storage Consumption

View storage consumption for your space with detailed usage information.



<a name="loio94fe6c13f6a340288cd50ee355566591__section_hqj_whj_42c"/>

## Prerequisites

To monitor the storage consumption of your space, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-R------`\) - To open your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.
-   *Data Warehouse Data Integration* \(`-R------`\) - \[for file spaces\] To view data integration task logs.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio94fe6c13f6a340288cd50ee355566591__section_nlt_thj_42c"/>

## Monitor the Storage Consumption of a Standard Space

You can review the usage storage of your standard space \(spaces with a storage type of *SAP HANA Database \(Disk and In-Memory\)*.

1.  In the side navigation area, click ![](Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\).
2.  Locate and select your space, and click *Monitor* or alternatively open your space and click *Monitor* in the upper-right side of your space.


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Section

</th>
</tr>
<tr>
<td valign="top">

*Disk Used for Storage* and *Memory Used for Storage*

</td>
<td valign="top">

Displays the amount of disk storage and memory storage used by your space in the SAP HANA Database.

For more information about storage capacity, see [Allocate Storage to a Space](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f414c3d62bfe49b38e2cfdd7b4e7d786.html "Use the Space Storage properties to allocate disk and memory storage to the space and to choose whether it will have access to the SAP HANA data lake.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

*Schema* and *Table Type*

</td>
<td valign="top">

Filter by schema or by table storage type \(disk or memory\). You can filter values by adding or removing them from the drop-down menus.

The values are displayed in the graphs and the table of the page.

The hidden replica tables of SAP HANA virtual tables are stored in a separate schema named `_SYS_TABLE_REPLICA_DATA` \(see [Replicating Data and Monitoring Remote Tables](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html)\).

</td>
</tr>
<tr>
<td valign="top">

*Table Storage Consumption* 

</td>
<td valign="top">

Displays in a graph all the relevant tables according to your selected filter, which makes it easy to get an overview over the consumed storage.

</td>
</tr>
<tr>
<td valign="top">

*Table Details*

</td>
<td valign="top">

Displays in a table more information such as the name, schema, storage type, record count, and the used storage of each table.

You can sort your list of tables in ascending, descending order or group them together as well as search for certain values.

</td>
</tr>
</table>



## Monitor the Storage Consumption of a File Space

You can review the usage storage of your file space \(spaces with a storage type of *SAP HANA Data Lake Files*\).

1.  In the side navigation area, click ![](Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\).
2.  Locate and select your space, and click *Monitor* or alternatively open your space and click *Monitor* in the upper-right side of your space.

Review the following storage information that is displayed in the *Monitor* page:


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*File Storage Used*

</td>
<td valign="top">

Displays the total amount of storage that is used by your space in the SAP Datasphere object store.

</td>
</tr>
<tr>
<td valign="top">

*Storage Breakdown*

</td>
<td valign="top">

Displays the total amount of storage that is used by your space, broken down by:

-   *Local Tables \(File\) - Active Records* - Displays the size used by the active records only of the local tables \(file\).
-   *Local Tables \(File\) - Previous Versions* - Displays the size of previous versions of the local tables \(file\). This includes files of previous versions that are required for delta processing.
-   *Local Tables \(File\) - Inbound Buffer* - Displays the size of the inbound buffer \(temporary storage of incoming data, usually empty\).
-   *Delta Logs* - Displays the size of the delta data logs.
-   *Apache Spark Logs* - Displays the size of the logs for the Apache Spark configuration task runs.
-   *Other \(Backup & Intermediate Tables\)* - Displays the total size used by backups of deleted files \(which are kept for 14 days after deletion\) and intermediate Data Lake tables \(created by incremental aggregation in transformation flows\). See [Creating an Incremental Aggregation on a Target Table in a Transformation Flow on File](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/89cf2943253c4b02b8012ae58ec68f29.html "Incremental aggregation on target tables in transformation flows for efficiently maintaining aggregated results during incremental data loads. Use it to apply aggregation functions (SUM, COUNT, MIN, MAX, AVG, LAST) to numerical columns when delta capture is enabled on the source table.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

*Table Storage Consumption*

</td>
<td valign="top">

Displays in a graph the consumed storage for active records and previous versions of all the local tables \(file\) used in your space.

</td>
</tr>
<tr>
<td valign="top">

*Table Details*

</td>
<td valign="top">

Displays detailed information about each local table \(file\) in the file space, which you can also view in *Monitoring* \> *Data Integration*.

-   You can sort your list of tables in ascending, descending order or group them together as well as search for certain values.
-   You can navigate to the *Data Integration* page by selecting the *Data Integration Monitor* button or by selecting a specific table link from the *Table* column, which will open the page *Data Integration* on the table. See [Monitoring Local Tables \(File\)](Data-Integration-Monitor/monitoring-local-tables-file-6b2d007.md).



</td>
</tr>
</table>

