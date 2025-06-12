<!-- loio5a14eb1709a24a35821d1618285d021d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Secure File Transfer Protocol \(SFTP\) as Targets for Your Replication Flows

You want to replicate data using a secure file transfer protocol \(SFTP\) for secure and reliable file transfers.



<a name="loio5a14eb1709a24a35821d1618285d021d__section_rjr_4qq_dfc"/>

## General Information

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Premium Outbound Integration](premium-outbound-integration-4e9c6ac.md) and [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).

While replicating data to an SFTP connection, only the following load types are supported:

-   Initial Only
-   Initial and Delta

    > ### Note:  
    > The default delta load interval is set as 1 hour.




<a name="loio5a14eb1709a24a35821d1618285d021d__section_dpc_vqq_dfc"/>

## Additional Properties

The following properties are relevant for secure file transfer protocol \(SFTP\) targets. You can review these properties for the replication flow itself \(by choosing <span class="FPA-icons-V3"></span> \(Browse target settings\)\) or for individual replication objects \(by selecting an object so that its properties get displayed in the side panel\).


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

Group Delta by

</td>
<td valign="top">

\[only relevant for load type Initial and Delta\] Select *None* \[default\], *Date*, or *Hour* to specify whether you want to create additional folders for sorting updates based on the date or hour.

</td>
</tr>
<tr>
<td valign="top">

File Type

</td>
<td valign="top">

Select the file type. You can choose between CSV, JSON, JSONLines, and Parquet \[default\]. 

For JSON and JSON Lines, generated files are encoded in UTF-8 format.

</td>
</tr>
<tr>
<td valign="top">

Enable Apache Spark Compatibility

</td>
<td valign="top">

\[only relevant for file type Parquet\] Enable this option to convert and store time data type columns to int64 in the Parquet files. The int64 data type represents microseconds after midnight. This conversion allows the columns to be consumed by Apache Spark.

</td>
</tr>
<tr>
<td valign="top">

File Compression

</td>
<td valign="top">

\[only relevant for file type Parquet\] Select the file compression type. You can choose between None \[default\], Gzip, and Snappy.

</td>
</tr>
<tr>
<td valign="top">

Suppress Duplicates

</td>
<td valign="top">

Enable this option to avoid duplicate records in your target file. During initial load, if a data record already exists in the target, the default system behavior with cloud storage provider targets would be to write this record to the target once again, which results in duplicate records. However, this is not the desired behavior for many use cases of replication flows, and consequently duplicate suppression is active by default. You can deactivate it if required for your specific use case \(for example to continue using existing replication flows that do not support duplicate suppression\).

</td>
</tr>
<tr>
<td valign="top">

Delimiter

</td>
<td valign="top">

\[only relevant for file type CSV\] Select the character you want to use to separate the columns from each other. You can choose between Comma \[default\], Colon, Pipe, Semicolon, and Tab.

</td>
</tr>
<tr>
<td valign="top">

Header Line

</td>
<td valign="top">

\[only relevant for file type CSV\] Select True \[default\] or False to specify whether you want the file to have a header line or not.

</td>
</tr>
<tr>
<td valign="top">

Orient

</td>
<td valign="top">

\[only relevant for file type JSON\] Select the internal structure for the generated JSON files. Currently the only available option is Records: \[\{column -\> value\}, ... ,\{column -\> value\}\]

</td>
</tr>
</table>



<a name="loio5a14eb1709a24a35821d1618285d021d__section_l2r_ftq_dfc"/>

## Target Columns

The system automatically adds the following columns to the schema of the target table:


<table>
<tr>
<th valign="top">

Column

</th>
<th valign="top">

Data Type

</th>
</tr>
<tr>
<td valign="top">

\_\_operation\_type

</td>
<td valign="top">

String

</td>
</tr>
<tr>
<td valign="top">

\_\_sequence\_number

</td>
<td valign="top">

Unit64

</td>
</tr>
<tr>
<td valign="top">

\_\_timestamp

</td>
<td valign="top">

Timestamp

</td>
</tr>
</table>

These columns are needed to capture changes in the source so that they can be replicated to the target, and you cannot change their names or settings.

If a target column has the same name as one of the columns for change data capturing, the target column has to be renamed. Auto-Projection does this by adding the prefix AUTOPREFIX\_ to the name of the target column, for example AUTOPREFIX\_timestamp.

