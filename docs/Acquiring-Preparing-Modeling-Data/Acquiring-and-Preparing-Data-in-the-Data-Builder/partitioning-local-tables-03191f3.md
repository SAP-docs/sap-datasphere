<!-- loio03191f36e9144b2aaa47b8c9eea039c1 -->

# Partitioning Local Tables

Create partitions based on one column of your local table to break your data down into smaller tables, and better manage tables with large volume of data.

Working with large volume of data can cause memory shortage and take many system resources. One of the solution is to use partitions: You create partitions based on one column of your table to break your data down into smaller and more manageable parts. When a table is partitioned, the split is done in such a way that each partition contains a different set of rows of the table, depending on the range definition you have set.

> ### Restriction:  
> -   If you have defined key columns for your table, only one of these key columns can be used as partitioning column.
> 
> -   Supported data types include:
> 
>     -   String
>     -   Integer, Integer 64, Decimal, hana.SMALLINT, hana.TINYINT
>     -   Date, DateTime, Time, Timestamp
>     -   Binary
> 
>     For more information, see [Partitioning Limits](https://help.sap.com/docs/HANA_CLOUD_DATABASE/f9c5015e72e04fffa14d7d4f7267d897/8dd866a688ec4914a074727a2c800142.html) in the *SAP HANA Cloud, SAP HANA Database* documentation.
> 
> -   Your table must not contain data yet.

To create partitions for local table, go to *Data Builder*, create your local table \(for more information, see [Creating a Local Table](creating-a-local-table-2509fe4.md)\), and then go to the *Partitions* tab.

Click *Define Partitions* and define the partitions ranges:


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

*Attribute*/*Column*

</td>
<td valign="top">

Select the column from which the partition will be defined.

> ### Note:  
> If you have defined key columns, you can select only a key column. If you have no key columns defined, all columns with compatible data types can be selected. Note that you won’t be able to define a key column later, until the partitions are in place.



</td>
</tr>
<tr>
<td valign="top">

*Partitions*

</td>
<td valign="top">

Create the number of desired partitions by entering a range for each of them. Note that ranges can't overlap.

> ### Note:  
> If you have data outside the defined partition ranges, an *Others* partition will be created to store this data



</td>
</tr>
</table>

Deploy the table.

> ### Note:  
> Once deployed, you won’t be able to change the data type of the primary key that has been used for partitioning. But you can still change or delete the partitions until you have added data in your table.

