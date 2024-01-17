<!-- loio6df55db4028842c1b1866e709ffef456 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Using Apache Kafka As the Target

If you use Apache Kafka as the target for your replication flow, you need to consider the following additional specifics and conditions.

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).

This topic contains the following sections:

-   [Additional Properties](using-apache-kafka-as-the-target-6df55db.md#loio6df55db4028842c1b1866e709ffef456__section_ReplFlow_Kafka_Properties)

-   [Further Information](using-apache-kafka-as-the-target-6df55db.md#loio6df55db4028842c1b1866e709ffef456__section_ReplFlow_Kafka_Info)




<a name="loio6df55db4028842c1b1866e709ffef456__section_ReplFlow_Kafka_Properties"/>

## Additional Properties

In addition to the properties that apply to all targets \(see the list in [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md)\), there are the following properties that are only relevant for Apache Kafka. You can review and change these properties for the replication flow itself \(by choosing <span class="FPA-icons"></span> \(Browse target settings\)\) or for individual replication objects \(by selecting an object so that its properties get displayed in the side panel\).


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

Select the message format for the Kafka topic You can choose between AVRO and JSON \[default\].

</td>
</tr>
<tr>
<td valign="top">

File Compression

</td>
<td valign="top">

Select the file compression type. You can choose between No Compression \[default\], Gzip, Snappy, LZ4, and ZStandard.

</td>
</tr>
</table>



<a name="loio6df55db4028842c1b1866e709ffef456__section_ReplFlow_Kafka_Info"/>

## Further Information

If you want to use an **existing Kafka topic** as the target, keep in mind that schema registry is currently not supported.

The **target container** is automatically set to "/" because Kafka does not have a superordinate container layer.

You can **rename** target objects \(Kafka topics\). The following conditions apply:

-   The new name may consist of the following characters: small latin letters \(a-z\), capital latin letters \(A-Z\), numbers \(0-9\), period \(.\), underscore \(\_\), hyphen \(-\).

-   The maximum length for the new name is 249 characters.


For more information and examples, see also [SAP Datasphere Replication Flows Blog Series Part 3 – Integration with Kafka.](https://blogs.sap.com/2023/12/04/sap-datasphere-replication-flows-blog-series-part-3-integration-with-kafka/)

