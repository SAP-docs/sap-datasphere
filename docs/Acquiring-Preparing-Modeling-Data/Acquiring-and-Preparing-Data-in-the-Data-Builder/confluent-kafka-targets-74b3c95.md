<!-- loio74b3c95464f246aa8c3fd510661daa6d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Confluent Kafka Targets

If you use Confluent Kafka as the target for your replication flow, you need to consider the following additional specifics and conditions.

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Premium Outbound Integration](premium-outbound-integration-4e9c6ac.md) and [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).
> 
> Consider also the following SAP Note content [3223810](https://me.sap.com/notes/3223810).

This topic contains the following sections:

-   [Additional Properties](confluent-kafka-targets-74b3c95.md#loio74b3c95464f246aa8c3fd510661daa6d__section_ReplFlow_Confluent_Properties) 
-   [Further Information](confluent-kafka-targets-74b3c95.md#loio74b3c95464f246aa8c3fd510661daa6d__section_ReplFlow_Confluent_Info) 



<a name="loio74b3c95464f246aa8c3fd510661daa6d__section_ReplFlow_Confluent_Properties"/>

## Additional Properties

In addition to the properties that apply to all targets \(see the list in [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md)\), there are the following properties that are only relevant for Confluent Kafka. You can review and change these properties for the replication flow itself \(by choosing <span class="FPA-icons-V3"></span> \(Browse target settings\)\) or for individual replication objects \(by selecting an object so that its properties get displayed in the side panel\).


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

Enter the number of Confluent partitions to be used for the Confluent topic. 

The default value is 1.

</td>
</tr>
<tr>
<td valign="top">

Replication Factor

</td>
<td valign="top">

Enter the Confluent replication factor to be used for the Confluent topic. 

The default value is 3.

</td>
</tr>
<tr>
<td valign="top">

Serialization Format

</td>
<td valign="top">

Select the serialization format for the Confluent topic. 

You can choose between AVRO \[default\] and JSON. If you select AVRO, the column name must consist of only alphanumeric and underscore characters, and it must start with a letter or an underscore.

</td>
</tr>
<tr>
<td valign="top">

Compression Type

</td>
<td valign="top">

Select the message compression type. 

You can choose between No Compression \[default\], Gzip, Snappy, LZ4, and ZStandard.

</td>
</tr>
<tr>
<td valign="top">

Use Schema Registry

</td>
<td valign="top">

If this option is enabled, the schema of the sent messages is registered in the provided schema registry. If it is disabled, the messages do not contain any schema information or schema-id. 

Using no schema registry is only allowed for serialization format JSON.

</td>
</tr>
<tr>
<td valign="top">

Record Name

</td>
<td valign="top">

\[only relevant if *Use Schema Registry* is enabled\] Enter the record name to be used in the schema that is registered in the schema registry. 

If you choose serialization type AVRO, the record name must consist of only alphanumeric and underscore characters, and it must start with a letter or an underscore.

</td>
</tr>
<tr>
<td valign="top">

Subject Name Strategy

</td>
<td valign="top">

\[only relevant if *Use Schema Registry* is enabled\] Select the strategy for building the subject name under which the schema will be registered in the schema registry. 

You can choose between Topic \[default\], Record, and Topic-Record.

</td>
</tr>
<tr>
<td valign="top">

Compatibility Mode

</td>
<td valign="top">

\[only relevant if *Use Schema Registry* is enabled\] Select the compatibility mode for the created subject in the schema registry. If the subject already exists and you choose a value other than DEFAULT, the system changes the compatibility mode of the subject to the provided value. If you leave the value as DEFAULT, the system uses the default value that has been defined for the Confluent cluster.

The following Confluent compatibility modes are available:

-   Backward

-   Backward Transitive

-   Forward

-   Forward Transitive

-   Full

-   Full Transitive

-   None




</td>
</tr>
<tr>
<td valign="top">

Clamp Decimal Floating Point Data Types

</td>
<td valign="top">

Clamping is enabled by default and cannot be switched off. 

See also below under Further Information.

</td>
</tr>
</table>



<a name="loio74b3c95464f246aa8c3fd510661daa6d__section_ReplFlow_Confluent_Info"/>

## Further Information

The **target container** is automatically set to "/" because Confluent Kafka does not have a superordinate container layer.

> ### Note:  
> If the Kafka cluster is behind an SAP Cloud Connector \(SCC\), the Kafka cluster and the SCC must be configured such that the broker addresses advertised by the cluster match the virtual hosts maintained for the brokers in the SCC. The simplest solution is to use the same value for virtual and internal hosts in the SCC and to maintain no dedicated advertised listeners for the Kafka brokers. When adding additional brokers to a cluster to scale up, the SCC mapping must be adapted to include the additional brokers.

Each record from the source system is transferred into a single **message** in the target topic. The key of the messages is the combination of all primary key values of the record concatenated by "\_".

**Clamping** is enabled on by default and cannot be switched off. The following decimal floating point and fixed point decimal values may be **clamped** according to the data type used in the target serialization:

-   decfloat16 and decfloat34 are clamped to DECIMAL\(28,6\) and DECIMAL\(38,6\), respectively, for AVRO and to double range \(set to +-inf\) for JSON.

-   DECIMAL\(p,s\) is clamped to double range \(set to +-inf\) for JSON.


Each topic contains the source columns as defined in the mapping for the replication object in the replication flow. The system **appends** the following **columns**:

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

You can **rename** target objects \(topics\). The following conditions apply:

-   The new name may consist of the following characters: small latin letters \(a-z\), capital latin letters \(A-Z\), numbers \(0-9\), period \(.\), underscore \(\_\), hyphen \(-\).

-   The maximum length for the new name is 249 characters.


