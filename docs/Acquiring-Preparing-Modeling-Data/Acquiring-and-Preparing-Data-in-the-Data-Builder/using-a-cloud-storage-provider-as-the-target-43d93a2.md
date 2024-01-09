<!-- loio43d93a27150a4a218e3df14e3abdf456 -->

# Using a Cloud Storage Provider As the Target

If you use a cloud storage provider as the target for your replication flow, you need to consider additional specifics and conditions.

This topic contains the following sections:

-   [Loading Data to Cloud Storage Providers](using-a-cloud-storage-provider-as-the-target-43d93a2.md#loio43d93a27150a4a218e3df14e3abdf456__section_General_AllNonSAPTargets)

-   [Premium Outbound Integration for Non-SAP Targets](using-a-cloud-storage-provider-as-the-target-43d93a2.md#loio43d93a27150a4a218e3df14e3abdf456__section_PremiumOutbound)




<a name="loio43d93a27150a4a218e3df14e3abdf456__section_General_AllNonSAPTargets"/>

## Loading Data to Cloud Storage Providers

The following cloud storage providers can be used as the target of a replication flow.

-   Data lake Files from SAP HANA Cloud, data lake

-   Amazon Simple Storage Service

-   Google Cloud Storage

-   Microsoft Azure Data Lake Gen2


For more information about the corresponding connection types, see [Integrating Data via Connections](https://help.sap.com/docs/SAP_DATASPHERE/be5967d099974c69b77f4549425ca4c0/eb85e157ab654152bd68a8714036e463.html).

Upon completion of the initial load, the system writes a `_SUCCESS` file. Downstream applications that can access the object store directly can use this file to verify that the replication completed successfully without having to check the replication flow status. This `_SUCCESS` file is provided for all cloud storage providers listed above except BigQuery.

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



<a name="loio43d93a27150a4a218e3df14e3abdf456__section_PremiumOutbound"/>

## Premium Outbound Integration for Non-SAP Targets

You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).

