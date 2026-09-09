<!-- loio3c9de9eb77e649a98450f4fd67a5f7ba -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitoring Your Partitions

You have created partitions for your local table in the *Data Builder*, and you now want to monitor the details of these partitions.

From :desktop_computer: *\(Monitoring\)* \> :fast_forward: *\(Data Integration\)* , go to the *Local Tables* monitor. Navigate to the details screen of the local table you want to monitor the partitions.

You can monitor the following information:


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

*Partition ID*

</td>
<td valign="top">

Displays the ID of the partition

</td>
</tr>
<tr>
<td valign="top">

*Number of Records*

</td>
<td valign="top">

Indicates the number of records contained in the partition

</td>
</tr>
<tr>
<td valign="top">

*Growth in 30 Days* 

</td>
<td valign="top">

Displays the growth in % of the number of records in the partition since the last month. It is computed by taking the difference between the number of records in the partition today and the number of records in the partition 30 days ago, and it calculates the growth in percentage.

</td>
</tr>
<tr>
<td valign="top">

*Size in-Memory*

</td>
<td valign="top">

Displays the quantity of memory required to fully load the partition data in-memory. 

> ### Note:  
> Value is set to Not Applicable for local tables that store data on disk.



</td>
</tr>
<tr>
<td valign="top">

*Size on Disk \(MiB\)*

</td>
<td valign="top">

Displays the disk storage used by the partition. 

> ### Note:  
> Value is set to Not Applicable for local tables that store data in-memory.



</td>
</tr>
<tr>
<td valign="top">

*Lower Bound \(Included\)*

</td>
<td valign="top">

\[Range Partitions Only\] Displays the lowest value that is taken as the first argument of the partition. Values of the lower bound are included.

</td>
</tr>
<tr>
<td valign="top">

*Upper Bound \(Excluded\)*

</td>
<td valign="top">

\[Range Partitions Only\] Displays the highest value that is taken as the last argument of the partition. Values of the upper bound are excluded.

</td>
</tr>
</table>

For more information, see [Partitioning Local Tables](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/03191f36e9144b2aaa47b8c9eea039c1.html "Create partitions for your local table to break your data down into smaller tables, and better manage tables with a large volume of data.") :arrow_upper_right:

