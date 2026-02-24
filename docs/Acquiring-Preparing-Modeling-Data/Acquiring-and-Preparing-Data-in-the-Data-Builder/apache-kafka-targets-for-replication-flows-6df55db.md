<!-- loio6df55db4028842c1b1866e709ffef456 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Apache Kafka Targets for Replication Flows

If you use Apache Kafka as the target for your replication flow, you need to consider the following additional specifics and conditions.

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Premium Outbound Integration](premium-outbound-integration-4e9c6ac.md) and [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).
> 
> Consider also the following SAP Note content [3297105](https://me.sap.com/notes/3297105).

Each record from the source system is transferred into a single **message** in the target topic. The key of the messages is the combination of all primary key values of the record concatenated by "\_".

**Schema registries** are **not** supported. If you choose AVRO as the serialization format, the schema is contained in every message. For the JSON serialization format, no schema information is provided.

The **target container** is automatically set to "/" because Kafka does not have a superordinate container layer.

> ### Note:  
> If the Kafka cluster is behind an SAP Cloud Connector \(SCC\), the Kafka cluster and the SCC must be configured such that the broker addresses advertised by the cluster match the virtual hosts maintained for the brokers in the SCC. The simplest solution is to use the same value for virtual and internal hosts in the SCC and to maintain no dedicated advertised listeners for the Kafka brokers. If advertised listeners are maintained, these must be used as virtual hosts in SCC and as broker addresses in the connection definition.

The following decimal floating point and fixed point decimal values may be **clamped** according to the data type used in the target serialization:

-   decfloat16 and decfloat34 are clamped to DECIMAL\(28,6\) and DECIMAL\(38,6\), respectively, for AVRO and to double range \(set to +-inf\) for JSON.

-   DECIMAL\(p,s\) is clamped to double range \(set to +-inf\) for JSON.


You can **rename** target objects \(Kafka topics\). The following conditions apply:

-   The new name may consist of the following characters: small latin letters \(a-z\), capital latin letters \(A-Z\), numbers \(0-9\), period \(.\), underscore \(\_\), hyphen \(-\).

-   The maximum length for the new name is 249 characters.


For more information and examples, see also [SAP Datasphere Replication Flows Blog Series Part 3 – Integration with Kafka.](https://blogs.sap.com/2023/12/04/sap-datasphere-replication-flows-blog-series-part-3-integration-with-kafka/) and [Confluent as Replication Target](https://community.sap.com/t5/technology-blogs-by-sap/replication-flow-blog-part-6-confluent-as-replication-target/ba-p/13693888).

This topic contains the following sections:

-   [Additional Properties](apache-kafka-targets-for-replication-flows-6df55db.md#loio6df55db4028842c1b1866e709ffef456__section_ReplFlow_Kafka_Properties)

-   [Additional Message Headers](apache-kafka-targets-for-replication-flows-6df55db.md#loio6df55db4028842c1b1866e709ffef456__section_ReplFlow_Kafka_MessageHeaders)




<a name="loio6df55db4028842c1b1866e709ffef456__section_ReplFlow_Kafka_Properties"/>

## Additional Properties

In addition to the properties that apply to all targets \(see the list in [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md)\), there are the following properties that are only relevant for Apache Kafka. You can review and change these properties for the replication flow itself \(by choosing <span class="FPA-icons-V3"></span> \(Browse target settings\)\) or for individual replication objects \(by selecting an object so that its properties get displayed in the side panel\).


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

Number of Partitions

</td>
<td valign="top">

Enter the number of Kafka partitions to be used for the Kafka topic.

</td>
</tr>
<tr>
<td valign="top">

Replication Factor

</td>
<td valign="top">

Enter the Kafka replication factor to be used for the Kafka topic.

</td>
</tr>
<tr>
<td valign="top">

Message Encoder

</td>
<td valign="top">

Select the message format for the Kafka topic. 

You can choose between AVRO and JSON \[default\]. If you select AVRO, the column name must consist of only alphanumeric and underscore characters, and it must start with a letter or an underscore.

</td>
</tr>
<tr>
<td valign="top">

Message Compression

</td>
<td valign="top">

Select the message compression type. You can choose between No Compression \[default\], Gzip, Snappy, LZ4, and ZStandard.

</td>
</tr>
</table>



<a name="loio6df55db4028842c1b1866e709ffef456__section_ReplFlow_Kafka_MessageHeaders"/>

## Additional Message Headers

Each topic contains the source columns as defined in the mapping for the replication object in the replication flow. The system appends the following columns:

-   *kafkaSerializationType*: AVRO or JSON

-   *OpType*: Identifies the type of target row:
    -   *L*: Written as part of the initial load.

    -   *I*: New source row added after the initial load is complete.

    -   *U*: Update to a source row after the initial load is complete.

        > ### Note:  
        > SAP S/4HANA and other ABAP sources do not distinguish between Insert \(*I*\) and Update \(*U*\), and both operations are identified as Upserts \(U\). If you apply SAP Note [3044005](https://me.sap.com/notes/3044005) the system identifies all upserts as *A*. The `APE_KEEP_UPDATE_OPERATION` parameter is described in the SAP Note.

    -   *B*: Before image of an update to a source row after the initial load is completed. These records are only sent by some sources \(such as SAP HANA\) and only when the after-image of the update does not pass the filters specified in the replication task.

    -   *X*: The Source row is deleted after the initial load completes. The only target columns to contain data for this operation code are codes that reflect the source key columns. All other target columns are empty.

    -   *M*: Archiving operations after the initial load is complete.

    -   *D*: \[When the source is a delta enabled local table in SAP Datasphere\] Row deleted with before image values.


-   *Seq*: Sequence number, an integer value that reflects the sequential order of the delta row in relation to other deltas. This column is empty for initial load rows and is not populated for all source systems \(for example, ABAP\).

