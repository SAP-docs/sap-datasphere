<!-- loio94fe6c13f6a340288cd50ee355566591 -->

# Monitor Your Space Storage Consumption

See the storage amount assigned to and used by your space.

To open the monitoring page, select your space and click *Monitor* from the *Space Management* page or alternatively open your space and click *Monitor* on the upper-right side of your space.


<table>
<tr>
<th valign="top">

Action



</th>
<th valign="top">

Example



</th>
</tr>
<tr>
<td valign="top">

See the amount of disk storage and in-memory storage used in your space.

For more information about storage capacity, see [Allocate Storage to a Space](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/f414c3d62bfe49b38e2cfdd7b4e7d786.html "Use the Storage Assignment properties to allocate disk and in-memory storage to the space and to choose whether it will have access to the SAP HANA data lake.") :arrow_upper_right:.



</td>
<td valign="top">

![](images/DWC_Monitoring_fb786ae.jpg)



</td>
</tr>
<tr>
<td valign="top">

Filter by schema or by storage type. Filter values by adding or removing them from the drop-down menu.

The values are displayed in a doughnut and bar chart.

The hidden replica tables of SAP HANA virtual tables are stored in a separate schema named `_SYS_TABLE_REPLICA_DATA`.

For more information about replica tables, see [Replicating Data and Monitoring Remote Tables](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html).



</td>
<td valign="top">

![](images/Monitor_Drop-Down_1669061.jpg)

![](images/Monitor_Overview_532de1b.jpg)



</td>
</tr>
<tr>
<td valign="top">

See the *Table Storage Consumption* graph that displays all the relevant tables according to your selected filter, which makes it easy to get an overview over the consumed storage.



</td>
<td valign="top">

![](images/DWC_Table_Consumption_29e97f7.jpg)



</td>
</tr>
<tr>
<td valign="top">

See *Table Details* that provides more information such as the name, schema, storage type, record count, and the used storage of each table.

Sort your list of tables in ascending, descending order or group them together as well as search for certain values.



</td>
<td valign="top">

![](images/Monitoring_Tabel_Details_DWC_de3fb75.jpg)



</td>
</tr>
</table>

