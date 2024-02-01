<!-- loio43d93a27150a4a218e3df14e3abdf456 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Using a Cloud Storage Provider As the Target

If you use a cloud storage provider as the target for your replication flow, you need to consider additional specifics and conditions.

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).

This topic contains the following sections:

-   [Available Targets](using-a-cloud-storage-provider-as-the-target-43d93a2.md#loio43d93a27150a4a218e3df14e3abdf456__section_ReplTargets_NonSAPTargets)

-   [Additional Properties](using-a-cloud-storage-provider-as-the-target-43d93a2.md#loio43d93a27150a4a218e3df14e3abdf456__section_ReplFlow_NonSAP_Targets_Properties)

-   [Files](using-a-cloud-storage-provider-as-the-target-43d93a2.md#loio43d93a27150a4a218e3df14e3abdf456__section_ReplFlow_Files)




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

In addition to the properties that apply to all targets \(see the list in [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md)\), there are the following properties that are only relevant for cloud storage providers. You can review and change these properties for the replication flow itself \(by choosing <span class="FPA-icons"></span> \(Browse target settings\)\) or for individual replication objects \(by selecting an object so that its properties get displayed in the side panel\).


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

Enable this option to avoid duplicate records in your target file. During initial load, if a data record already exists in the target, the default system behavior with cloud storage provider targets is to write this record to the target once again, which results in duplicate records. If this is not the desired behavior for your use case, you can change it by enabling this option.

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

The `.sap.partfile.metadata` objects include metadata information for the replication object. It exists in the root of each data file directory and is created and referenced as part of replication flow processing. Additionally, you can leverage these objects for interpreting and processing the data files.

The replication flow creates multiple files \(<code>part-*.<i class="varname">&lt;extension&gt;</i></code>\) during initial and delta loading. The number and size of these files depends on the source table size and structure as well as change frequency \(during delta loading\).

Each file contains the source columns as defined in the mapping for the replication object in the replication flow. The system appends the following columns:

-   *\_\_operation\_type*: Identifies the type of target row:
    -   *L*: Written as part of the initial load.

    -   *I*: After the initial load completed, new source row added.

    -   *U*: After the initial load completed, after image of an update to a source row.

        > ### Note:  
        > For some sources, the system switches the value *U* to *A* after you apply SAP Note [3044005](https://me.sap.com/notes/3044005). The APE\_KEEP\_UPDATE\_OPERATION parameter is described in the SAP Note.

    -   *B*: After the initial load completed, before image of an update to a source row. These records are only sent by some sources \(like SAP HANA\) and only when the after image of the update is not passing the filters specified in the replication task.

    -   *X*: After the initial load completed, source row deleted. The only target columns to contain data for this operation code are codes that reflect the source key columns. All other target columns are empty.

    -   *M*: After the initial load completed, archiving operations.


-   *\_\_sequence\_number*: An integer value that reflects the sequential order of the delta row in relation to other deltas. This column is empty for initial load rows and is not populated for all source systems \(for example, ABAP\).
-   *\_\_timestamp*: The UTC date and time the system wrote the row.

