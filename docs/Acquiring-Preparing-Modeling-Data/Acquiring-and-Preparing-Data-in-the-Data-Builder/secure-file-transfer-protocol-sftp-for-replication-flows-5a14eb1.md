<!-- loio5a14eb1709a24a35821d1618285d021d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Secure File Transfer Protocol \(SFTP\) for Replication Flows

You want to replicate data using a secure file transfer protocol \(SFTP\) for secure and reliable file transfers.



<a name="loio5a14eb1709a24a35821d1618285d021d__section_rjr_4qq_dfc"/>

## General Information

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Premium Outbound Integration](premium-outbound-integration-4e9c6ac.md) and [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).
> 
> Consider also the following SAP Note content [3297105](https://me.sap.com/notes/3297105).

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

-   \_\_operation\_type: Identifies the type of target row:


    <table>
    <tr>
    <th valign="top">

    \_\_operation\_type
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    From Source System Connection Types
    
    </th>
    <th valign="top">

    Comments
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    L
    
    </td>
    <td valign="top">
    
    Written as operation type for all records during the initial load phase.
    
    </td>
    <td valign="top">
    
    All
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    I
    
    </td>
    <td valign="top">
    
    New source row added during delta load phase.
    
    </td>
    <td valign="top">
    
    All except SAP S/4HANA on-prem/cloud and ABAP.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    U
    
    </td>
    <td valign="top">
    
    Update \(after image\) to a source row during delta load phase.
    
    </td>
    <td valign="top">
    
    All except SAP S/4HANA on-prem/cloud and ABAP.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    U or A
    
    </td>
    <td valign="top">
    
    New source row or update to a source row during delta load phase.
    
    </td>
    <td valign="top">
    
    SAP S/4HANA on-prem/cloud and ABAP and Datasphere delta enabled local table.
    
    </td>
    <td valign="top">
    
    SAP S/4HANA and other ABAP sources do not distinguish between Insert and Update, and both operations are identified as *U* \(Upserts\). If you apply SAP Note [3044005](https://me.sap.com/notes/3044005) the system identifies all Upserts as *A* \(Autocorrect\). The `APE_KEEP_UPDATE_OPERATION` parameter is described in the SAP Note.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    B
    
    </td>
    <td valign="top">
    
    Update \(before image\) of an update to a source row during delta load phase.
    
    </td>
    <td valign="top">
    
    SAP HANA cloud/on-prem, Azure SQL, MSSQL.
    
    </td>
    <td valign="top">
    
    These records are only sent by some sources and only when the after-image of the update does not pass the filters specified in the replication task.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    X
    
    </td>
    <td valign="top">
    
    The Source row is deleted \(with primary key values only\) during the delta load phase.
    
    </td>
    <td valign="top">
    
    All except Datasphere delta enabled local table and Confluent depending on opcode specification.
    
    </td>
    <td valign="top">
    
    The only target columns to contain data for this operation code are codes that reflect the source key columns. All other target columns are empty.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    D
    
    </td>
    <td valign="top">
    
    The Source row is deleted with before image values during delta load phase.
    
    </td>
    <td valign="top">
    
    Datasphere Delta enabled local table, and Confluent - depending on opcode specification.
    
    </td>
    <td valign="top">
    
    Delete record contains the before image values.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    M
    
    </td>
    <td valign="top">
    
    Archiving operations after the initial load is complete.
    
    </td>
    <td valign="top">
    
    SAP S/4HANA on-prem/cloud and ABAP Datasphere Delta enabled local table.
    
    </td>
    <td valign="top">
    
     
    
    </td>
    </tr>
    </table>
    
-   *\_\_sequence\_number*: An integer value that reflects the sequential order of the delta row in relation to other deltas. This column is empty for initial load rows and is populated only for the following source systems: Microsoft Azure SQL, Microsoft SQL Server \(MSSQL\) and SAP HANA.
-   *\_\_timestamp*: The UTC date and time the system wrote the row.

These columns are needed to capture changes in the source so that they can be replicated to the target, and you cannot change their names or settings.

If a target column has the same name as one of the columns for change data capturing, the target column has to be renamed. Auto-Projection does this by adding the prefix AUTOPREFIX\_ to the name of the target column, for example AUTOPREFIX\_timestamp.

