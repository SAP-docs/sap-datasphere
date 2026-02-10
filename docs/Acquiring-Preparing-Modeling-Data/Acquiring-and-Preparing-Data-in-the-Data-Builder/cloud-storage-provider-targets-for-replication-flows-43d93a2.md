<!-- loio43d93a27150a4a218e3df14e3abdf456 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Cloud Storage Provider Targets for Replication Flows

If you use a cloud storage provider as the target for your replication flow, you need to consider additional specifics and conditions.

This topic contains the following sections:

-   [Prerequisites](cloud-storage-provider-targets-for-replication-flows-43d93a2.md#loio43d93a27150a4a218e3df14e3abdf456__section_ReplTargets_NonSAPTargets_Prerequisites)

-   [Available Targets](cloud-storage-provider-targets-for-replication-flows-43d93a2.md#loio43d93a27150a4a218e3df14e3abdf456__section_ReplTargets_NonSAPTargets)

-   [Additional Properties](cloud-storage-provider-targets-for-replication-flows-43d93a2.md#loio43d93a27150a4a218e3df14e3abdf456__section_ReplFlow_NonSAP_Targets_Properties)

-   [Files](cloud-storage-provider-targets-for-replication-flows-43d93a2.md#loio43d93a27150a4a218e3df14e3abdf456__section_ReplFlow_Files)

-   [Naming Conventions](cloud-storage-provider-targets-for-replication-flows-43d93a2.md#loio43d93a27150a4a218e3df14e3abdf456__section_ReplFlow_NonSAP_Targets_Naming)




<a name="loio43d93a27150a4a218e3df14e3abdf456__section_ReplTargets_NonSAPTargets_Prerequisites"/>

## Prerequisites

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Premium Outbound Integration](premium-outbound-integration-4e9c6ac.md) and [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).
> 
> Consider also the following SAP Note content [3223810](https://me.sap.com/notes/3223810).

You have a folder in the target environment \(object store provider\) into which the data can be replicated.



<a name="loio43d93a27150a4a218e3df14e3abdf456__section_ReplTargets_NonSAPTargets"/>

## Available Targets

The following cloud storage providers can be used as the target of a replication flow.

-   Data lake Files from SAP HANA Cloud, data lake

-   Amazon Simple Storage Service

-   Google Cloud Storage

-   Microsoft Azure Data Lake Gen2


For more information about the corresponding connection types, see [Integrating Data via Connections](https://help.sap.com/docs/SAP_DATASPHERE/be5967d099974c69b77f4549425ca4c0/eb85e157ab654152bd68a8714036e463.html).



<a name="loio43d93a27150a4a218e3df14e3abdf456__section_ReplFlow_NonSAP_Targets_Properties"/>

## Additional Properties

In addition to the properties that apply to all targets \(see the list in [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md)\), there are the following properties that are only relevant for cloud storage providers. You can review and change these properties for the replication flow itself \(by choosing <span class="FPA-icons-V3"></span> \(Browse target settings\)\) or for individual replication objects \(by selecting an object so that its properties get displayed in the side panel\).


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

Enable this option to avoid duplicate records in your target file. During initial load, if a data record already exists in the target, the default system behavior with cloud storage provider targets would be to write this record to the target once again, which results in duplicate records. However, this is not the desired behavior for many use cases of replication flows, and consequently, duplicate suppression is active by default. You can deactivate it if required for your specific use case \(for example, to continue using existing replication flows that do not support duplicate suppression\).

> ### Note:  
> To accomplish duplicate suppression in initial load replications, a unique filename for the target storage is generated using an algorithm. Note that the algorithm is subject to change at any time for internal SAP reasons, which may affect the suppression mechanism. This can result in some duplicate records appearing during the migration process.



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



<a name="loio43d93a27150a4a218e3df14e3abdf456__section_ReplFlow_Files"/>

## Files

Running a replication flow with a cloud storage target creates various files and structures:

Upon completion of the initial load, the system writes a `_SUCCESS` file. Downstream applications that can access the object store directly can use this file to verify that the replication completed successfully without having to check the replication flow status.

The `.sap.partfile.metadata` objects include metadata information for the replication object. It exists in the root of each data file directory and is created and referenced as part of replication flow processing. It is intended for internal usage and its format and content might be subject to change without notice.

The replication flow creates multiple files \(<code>part-*.<i class="varname">&lt;extension&gt;</i></code>\) during initial and delta loading. The number and size of these files depends on the source table size and structure as well as change frequency \(during delta loading\).

> ### Note:  
> Parquet name files are generated using this logic:
> 
> The name pattern is part-<Replication Flow Task ID \(UUID, SAP internal\)\>-<delimitation number of the task \(01 to 60, SAP internal\)\>.parquet. This is just a random UUID+NN that is unique to the whole replication task process, to avoid accidentally overwriting an existing file.

Each file contains the source columns as defined in the mapping for the replication object in the replication flow. The system appends the following columns:

-   *\_\_operation\_type*: Identifies the type of target row:
    -   *L*: Written as part of the initial load.

    -   *I*: New source row added after the initial load is complete.

    -   *U*: Update to a source row after the initial load is complete.

        > ### Note:  
        > SAP S/4HANA and other ABAP sources do not distinguish between Insert \(*I*\) and Update \(*U*\), and both operations are identified as Upserts \(U\). If you apply SAP Note [3044005](https://me.sap.com/notes/3044005) the system identifies all upserts as *A*. The `APE_KEEP_UPDATE_OPERATION` parameter is described in the SAP Note.

    -   *B*: Before image of an update to a source row after the initial load is completed. These records are only sent by some sources \(such as SAP HANA\) and only when the after-image of the update does not pass the filters specified in the replication task.

    -   *X*: The Source row is deleted after the initial load completes. The only target columns to contain data for this operation code are codes that reflect the source key columns. All other target columns are empty.

    -   *M*: Archiving operations after the initial load is complete.

    -   *D*: \[When the source is a delta enabled local table in SAP Datasphere\] Row deleted with before image values.


-   *\_\_sequence\_number*: An integer value that reflects the sequential order of the delta row in relation to other deltas. This column is empty for initial load rows and is populated only for the following source systems: Microsoft Azure SQL, Microsoft SQL Server \(MSSQL\) and SAP HANA.
-   *\_\_timestamp*: The UTC date and time the system wrote the row.



<a name="loio43d93a27150a4a218e3df14e3abdf456__section_ReplFlow_NonSAP_Targets_Naming"/>

## Naming Conventions

The name of the **target container** must meet the following requirements:

-   Length must be from 1 to 127 characters

-   The following ASCII characters are allowed:

    -   Lower case \(a-z\) and upper-case letters \(A-Z\)

    -   Numbers \(0-9\)

    -   Space \(<blank\>\)

    -   Period \(.\)

    -   Slash \(/\)

    -   Hyphen \(-\)

    -   Underscore \(\_\)

    -   Apostrophe \('\)

    -   Parentheses \( \( and \) \)


-   Leading and Trailing spaces are not allowed.


