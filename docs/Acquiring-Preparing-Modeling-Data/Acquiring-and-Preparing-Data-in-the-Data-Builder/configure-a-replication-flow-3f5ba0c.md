<!-- loio3f5ba0c5ae3944c1b7279bb989a2a5b5 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure a Replication Flow

Define settings and properties for your replication flow and individual replication objects.



## Procedure

1.  On the *Settings* tab of the canvas, select the relevant load type:

    -   *Initial Only*: Load all selected data once.

    -   *Initial and Delta*: After the initial load, the system checks for source data changes \(delta\) at regular intervals and copies the changes to the target. The default value for the delta load frequency is 60 minutes but you can change it in the Run Settings. See the step 5 below.

        > ### Note:  
        > -   A replication flow that contains objects with load type *Initial and Delta* does not have an end date. Once started, it remains in status *Active* until it is stopped or paused or an issue occurs.
        > 
        >     > ### Caution:  
        >     > You must always stop or pause a running replication flow before a source system downtime. For more information, see [Working With Existing Replication Flow Runs](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/da62e1ee746448e8bc043e1be4377cbe.html "You can pause a replication flow run and resume it later, or stop it completely when it's no longer needed. You can also schedule, monitor premium outbound volume, and configure email notifications for replication flow failures. For more information on how to make changes to an existing replication flow in the Data Builder, see .") :arrow_upper_right:.
        > 
        > -   The system load caused by the delta load operations can vary substantially depending on the frequency of changes in your data source in combination with the interval length you define. Make sure that your tenant configuration supports your settings. For more information, see [Configure the Size of your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).
        > 
        > -   The next interval starts after all changes from the previous interval have been replicated. For example, if replicating a set of changes starts at 10:30 a. m. and takes until 10:45 a. m., and you have defined one-hour intervals, the next delta replication starts at 11:45 a. m.
        > 
        > -   If your source object is a local table, you can only use load type *Initial and Delta* if *Delta Capture* is switched on for the local table \(see [Capturing Delta Changes in Your Local Table](https://help.sap.com/docs/SAP_DATASPHERE/c8a54ee704e94e15926551293243fd1d/154bdffb35814d5481d1f6de143a6b9e.html)\).

    -   *Delta Only*: Perform replications on changed records \(inserted, updated or deleted records\).

        While choosing this load type, you may consider:

        -   Not all targets and sources support this load type. If it is not supported, it will not be available in the load type selection.
        -   The *Delta Only* load type should not be used for data migration purposes, but it can be useful for transactional data where the history of data is not relevant, and therefore only the newly provided data being generated should be used in the target system of the replication flow. Indeed, since the initial load is skipped, data consistency cannot be guaranteed between the source and target. As a result, there may be time gaps between the completion of the initial load and the initiation of delta capture in the delta-only task, potentially leading to missing transaction records in the delta capture log and resulting in data inconsistencies.

            > ### Example:  
            > -   If data has not changed in the source when you start a replication with the *Delta Only* load type, then no data will be seen in the target. Hence, the target table does not capture a complete snapshot of the source table.
            > -   If the source table has two records with a primary key \(key 1 and key 2\), and after you've started the replication with the *Delta Only* load type the record with key1 does not contain changes in the source table. Hence, it won't be replicated to the target table, making it inconsistent.

            > ### Note:  
            > If you want to automate your replication flow run with a task chain or a schedule, you can’t use the *Delta Only* load type as it is not supported.

        -   *Delta Only* is a long running task similar to *Initial and Delta*.

        > ### Note:  
        > For more information on supported load types and connections, see [Load Types and Connections for Your Replication Flows](load-types-and-connections-for-your-replication-flows-1089119.md).


2.  On the *Settings* tab of the canvas, review the *Delete All Before Loading* setting and change it as required. This setting is only relevant if the target structure already exists and contains data. If the target structure does not yet exist or is empty, you can ignore the *Delete All Before Loading* setting.

    -   If *Delete All Before Loading* is activated for a **database table**, when you start the replication run, the system deletes the table content, but leaves the table structure intact and fills it with the relevant data from the source.

        If not, the system inserts new data records after the existing data in the target. For data records that already exist in the target and have been changed in the source, the system updates the target records with the changed data from the source using the UPSERT mode.

    -   For cloud storage provider targets, *Delete All Before Loading* must always be set. \(If you still try to run a replication flow for an existing target without the *Delete All Before Loading* option, you get an error message.\) When you start the replication run, the system deletes the object completely \(data and structure\) and re-creates it based on the source data.
    -   For Apache Kafka and Confluent Kafka, when *Delete All Before Loading* is enabled, the target topic is re-created. This means that all existing records in that topic are deleted as well. Truncation has no effect on the schema registry.


3.  Click <span class="FPA-icons-V3"></span> \(Browse source settings\) to review the source settings and change them as appropriate.

    -   For **delta loading**, you can specify the number of threads to be used for parallel processing at replication object level. The default value is 1 \(no parallel processing\). The maximum possible value is 10. This option is only available for SLT tables, CDS views, and CDS view entities that have load type *Initial and Delta* or *Delta Only*.

    -   Overwrite Source Settings at Object Level: \[only relevant if the source is a cloud storage provider\] By default, any settings that you have made at replication object level are kept intact if you make a different setting at replication flow level. To change this, enable this option.

    -   Additional settings that are only relevant for a specific source type and can be made for the replication flow itself as well as for individual replication objects. For more information, see

        -   [Cloud Storage Provider Sources for Replication Flows](cloud-storage-provider-sources-for-replication-flows-4d481a2.md)

        -   [Confluent Kafka Sources for Replication Flows](confluent-kafka-sources-for-replication-flows-4f2d0a8.md)

        -   [Secure File Transfer Protocol \(SFTP\) as Targets for Your Replication Flows](secure-file-transfer-protocol-sftp-as-targets-for-your-replicati-5a14eb1.md)


4.  Click <span class="FPA-icons-V3"></span> \(Browse target settings\) to review the target settings and change them as appropriate.

    -   Overwrite Target Settings at Object Level: \[only relevant if the target is a cloud storage provider\] By default, any settings that you have made at replication object level are kept intact if you make a different setting at replication flow level. To change this, enable this option.

    -   Additional settings that are only relevant for a specific target type and can be made for the replication flow itself as well as for individual replication objects. For more information, see

        -   [Cloud Storage Provider Targets](cloud-storage-provider-targets-43d93a2.md)

        -   [Google BigQuery Targets](google-bigquery-targets-56d4472.md)

        -   [Apache Kafka Targets](apache-kafka-targets-6df55db.md)

        -   [Confluent Kafka Targets](confluent-kafka-targets-74b3c95.md)



5.  Change the **Run Settings** if needed.

    > ### Note:  
    > Run settings can be updated when the following requirements are met:
    > 
    > -   The replication flow is successfully deployed. Until it is deployed, the *Edit* button is not accessible.
    > -   You must have the DW Integrator role.

    To change the settings, click *Edit*:

    -   Source Thread Limit \(1-100\): You can increase or decrease the number of replication threads to be used by your replication flow to load data from the source as appropriate for your use case. In particular, the value you enter here determines how many partitions can be processed in parallel during and initial load. Possible values are integers between 1 and 100, the default is 10. When replicating data from SAP HANA, specify an even number for the maximum number of threads, ideally a multiple of 10, as this helps to improve performance. See also [Replication Flow Blog Series Part 4 - Sizing](https://blogs.sap.com/2023/12/15/replication-flow-blog-series-part-4-sizing/).
    -   Target Thread Limit \(1-100\) You can increase or decrease the number of replication threads to be used by your replication flow to write data to the target as appropriate for your use case. In particular, the value you enter here determines how many partitions can be processed in parallel during and initial load. Possible values are integers between 1 and 100, the default is 10. We recommend using the same value for the source and the target. When replicating data from SAP HANA, specify an even number for the maximum number of threads, ideally a multiple of 10, as this helps to improve performance.
    -   Delta Load Frequency: The default value for the delta load frequency is 60 minutes. You can change it by entering an integer between 0 and 24 for hours and 0 and 59 for minutes, respectively. The maximum allowed value is 24 hours 0 minutes. If you enter 0 hours and 0 minutes, the system replicates any source changes immediately

6.  Review the settings for the individual replication objects and change or complete them as appropriate.

    To do so, select the relevant replication object. Its properties are then displayed in the side panel.

    For a list of properties and further information, see [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md).


