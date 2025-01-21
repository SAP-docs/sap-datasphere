<!-- loio4f2d0a8f23384efdab6891b29093786a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Confluent Kafka Sources

If you use Confluent Kafka as the source for your replication flow, you need to consider the following additional specifics and conditions.

You can transfer Kafka messages from Confluent Platform and Confluent Cloud topics to all supported targets for replication flows. Only Kafka messages whose message body is associated with a fixed schema that is registered in the Confluent schema registry can be replicated.

The source container that you select for the replication is a schema registry context in Confluent, and the replication objects are Confluent topics. The default context of the Confluent schema registry is displayed as period \(.\).

All replication objects must have load type *Initial and Delta*.

After you confirm your selection of replication objects, the system tries to determine the relevant schema for each object. The schema is defined by pulling the first message from the topic, fetching its schema ID, and extracting the schema from the selected context. If the schema ID is not found in the context, the replication fails and a context with the corresponding schema must be selected. If no message exists in the topic, the system tries to find a subject following the topic name strategy in the context. If nothing is found, you can still use the object, but have to configure the schema manually as described below.

When getting the data from the source, the system flattens any existing nested structures, as this is necessary for the purposes of the replication. To see the nested structures, choose *Configure Schema* in the side panel and switch from *Flat* to *Nested*.

By default, the `__message_id` column is used as the primary key for the purposes of the replication. The \_\_message\_id is constructed based on the Kafka partition the message was consumed from and the message offset of the corresponding Kafka message. The \_\_message\_id for a specific record then takes the form <partition\>-<offset\>, for example, 2-1 for a Kafka message with offset 1 that is part of partition 2.



<a name="loio4f2d0a8f23384efdab6891b29093786a__section_c51_myq_5bc"/>

## Configuring Source Schemas

When you select a replication object, its properties, including schema-related information, are displayed in the side panel. To change the schema-related properties, choose *Configure Schema* in the side panel. You can then do the following:

-   View the technical name, data type, precision and scale, and key column status for each source column in the table.

-   Display either the flattened structure \(default\) or the nested structures.

    > ### Note:  
    > Array and map fields are not supported.

-   Select a subject name from the list of available values.

-   Select a schema version from the list of available values.


The property *Include Technical Key* is switched on by default and cannot be switched off. It ensures that the `__message_id` column is included as part of the selected table and treated as the primary key.

When you are done, choose *Update Schema* to save and apply your changes.



<a name="loio4f2d0a8f23384efdab6891b29093786a__section_ReplFlow_Confluent_Properties"/>

## Source Settings and Additional Properties

The following properties are relevant for Confluent Kafka \(in addition to the general properties\). You can review and change these properties for the replication flow itself \(by choosing <span class="FPA-icons-V3"></span> \(Browse source settings\)\) or for individual replication objects \(by selecting an object so that its properties get displayed in the side panel\).


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

Consume Other Schema Versions

</td>
<td valign="top">

Enable this option if you want the replication to consume other schema versions of the subject. 

By default, this property is deactivated, which means that the replication fails with an error if the system encounters a message whose version differs from the one it has determined for the topic. If you activate this property, the system automatically tries to consume other schema versions of the subject and match them with the schema that it determined earlier.

</td>
</tr>
<tr>
<td valign="top">

Ignore Schema Mismatch

</td>
<td valign="top">

\[only visible if Consume Other Schema Versions is enabled\] Enable this option if you want the replication to continue even when the schemas do not match. 

By default, this property is deactivated, which means that the replication fails with an error if it encounters a message with a different schema. If you activate this property, the system ignores messages whose schema differs from the previously determined one \(for example if it has a different serialization format\). Note that the replication always fails \(irrespective of the setting you make here\) if the different schemas belong to different subjects, have different key columns, or include a column whose data type is different for the different schemas.

</td>
</tr>
<tr>
<td valign="top">

Fail on Data Truncation

</td>
<td valign="top">

Enable this option if you want the replication to fail when the source data is too long. By default, the replication fails if a value exceeds either the field length for STRING \(5000\) or BINARY\(5000\) or the specified precision. If you deactivate this property, source values that are too long are automatically truncated.

</td>
</tr>
<tr>
<td valign="top">

Starting Point

</td>
<td valign="top">

Select from where to start the reading operation. 

By default, the topics are read starting from the oldest available partition offsets \(*Read from earliest offset*\). Alternatively, you can select *Read from latest offset*. If you do so, the system reads only messages newer than the ones present when the replication starts the delta mode phase.

</td>
</tr>
</table>

