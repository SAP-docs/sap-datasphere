<!-- loio4f2d0a8f23384efdab6891b29093786a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Confluent Kafka Sources for Replication Flows

If you use Confluent Kafka as the source for your replication flow, you need to consider the following additional specifics and conditions.

You can transfer Kafka messages from Confluent Platform and Confluent Cloud topics to all supported targets for replication flows. Only Kafka messages whose message body is associated with a fixed schema that is registered in the Confluent schema registry can be replicated.

The source container that you select for the replication is a schema registry context in Confluent, and the replication objects are Confluent topics. The default context of the Confluent schema registry is displayed as period \(.\).

All replication objects must have load type *Initial and Delta* \(other load types are not supported\).

After you confirm your selection of replication objects, the system tries to determine the relevant schema for each object. The schema is defined by pulling the first message from the topic, fetching its schema ID, and extracting the schema from the selected context. If the schema ID is not found in the context, the replication fails and a context with the corresponding schema must be selected. If no message exists in the topic, the system tries to find a subject following the topic name strategy in the context. If nothing is found, you can still use the object, but have to configure the schema manually as described below.

When getting the data from the source, the system flattens any existing nested structures, as this is necessary for the purposes of the replication. To see the nested structures, choose *Configure Schema* in the side panel and switch from *Flat* to *Nested*.

By default, the `__message_id` column is used as the primary key for the purposes of the replication. The \_\_message\_id is constructed based on the Kafka partition the message was consumed from and the message offset of the corresponding Kafka message. The \_\_message\_id for a specific record then takes the form <partition\>-<offset\>, for example, 2-1 for a Kafka message with offset 1 that is part of partition 2.



<a name="loio4f2d0a8f23384efdab6891b29093786a__section_y3h_lg3_y2c"/>

## Configuring Source Schemas

When you select a replication object, its properties, including schema-related information, are displayed in the side panel. To change the schema-related properties,

1.  Open the relevant replication flow in the replication flow editor.
2.  Select the relevant replication object.
3.  Click *Configure Schema* in the side panel.

    The configure schema dialog opens in 2 sections:

    -   The *Properties* section, where you can select properties that will affect the schema:


        <table>
        <tr>
        <th valign="top">

        Properties
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Subject Name*
        
        </td>
        <td valign="top">
        
        Select the schema you want to use from the list of available values.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Schema Version*
        
        </td>
        <td valign="top">
        
        Select the schema version to use from the list of available values.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Expand Array or Map*
        
        </td>
        <td valign="top">
        
        In case the selected Kafka Schema contains arrays or maps, you can select at most one field for expansion.

        > ### Note:  
        > Array\_index or map\_key can serve as primary keys. However, if you configure the Opcode, array\_index should not be used as a primary key, and you must select another item-level field as the item key.

        When an array or a map is expanded, you must select at least 2 primary keys: one at the header level and one at the item level.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Omit Non-Expanded Arrays/Maps
        
        </td>
        <td valign="top">
        
        When this option is enabled, all array/map fields that are not selected for expansion will be removed from the schema.

        > ### Note:  
        > If this option is unchecked, the content of all non-expanded array and map fields will be marshaled into a string. If *Fail on Data Truncation* is enabled and the marshaled string exceeds 5,000 characters, the content will be truncated to a maximum length of 5,000 characters.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Include Technical Key*
        
        </td>
        <td valign="top">
        
        When the property *Include Technical Key* is selected, it ensures that the \_\_message\_id column is included as part of the selected table and treated as the primary key. If you deselect it, you hide the current primary key and a new one must be selected.
        
        </td>
        </tr>
        </table>
        
    -   The *Schema* section, where you will update the schema itself. It can be displayed in two different modes: *Flat* or *Nested*:


        <table>
        <tr>
        <th valign="top">

        Properties
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        **Source columns \(Technical Name\)**
        
        </td>
        <td valign="top">
        
        Displays the technical name of the source column.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Source Data Type*
        
        </td>
        <td valign="top">
        
        Displays the column data type.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Opcode*
        
        </td>
        <td valign="top">
        
        You can define a source column to be interpreted as an operation code column. Only one column of data type *String* can be selected. Once *Opcode* is selected, you must define the opcode mapping.

        > ### Note:  
        > When you add an opcode, it's recommended that you select a different primary key for the item level to avoid inconsistency problems when applying change delta capture operations. We therefore recommend that:
        > 
        > 1.  '\_\_array\_index' is not defined as the primary key, because the '\_\_array\_index' can be changed by the source.
        > 2.  You check the order of messages pushing all relevant messages into one partition.
        > 
        > The reason is that if array\_index is used as part of the primary key, when a message comes with a differently ordered array and for example, an updated opcode, it could update the wrong row, generating unexpected results.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        **Opcode Mapping**
        
        </td>
        <td valign="top">
        
        Define how the SAP opcodes column must be mapped with the values contained in your dataset for Insert, Update or Delete.

        > ### Note:  
        > You can define multiple values for one opcode if needed \(use a coma as separator\).

        > ### Example:  
        > You have inserted data from another system \(we will call it SystemA\) into Confluent. This dataset contains several columns, one of which indicates the type of operation performed, acting as the operation code column. This column stores values for different operations such as insert, update, or delete. For example, SystemA might use values like INS or INSR for insert operations, and UPD or UP for update operations.
        > 
        > While replicating this data from Confluent to another system, you can mark that column as the operation code column, and provide a mapping by providing values in insert, update and delete input fields. So as Opcode Mapping I will set:
        > 
        > -   INSERT = INS, INSR
        > -   UPDATE = UPD, UP
        > 
        > When you specify values like INS and INSRT in the Insert field, SAP Datasphere will use those values while replicating the data using their equivalent operation code whenever it encounters INS or INSRT during replication.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Key Column*
        
        </td>
        <td valign="top">
        
        One primary key must be defined. By default the message\_id column is selected. However, you can choose a different primary key.
        
        </td>
        </tr>
        </table>
        

4.  Click *Apply Changes*.
5.  Save and redeploy



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

For more information, see the blog [Confluent as Replication Source](https://community.sap.com/t5/technology-blogs-by-sap/replication-flows-blog-series-part-8-confluent-as-a-replication-source/ba-p/13938148)

