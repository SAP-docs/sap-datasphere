<!-- loioeb85e157ab654152bd68a8714036e463 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Integrating Data via Connections

Connections provide access to data from a wide range of remote systems, cloud as well as on-premise, SAP as well as Non-SAP, and partner tools. They allow users assigned to a space to use objects from the connected remote system as source to acquire, prepare and access data from those sources in SAP Datasphere. In addition, you can use certain connections to define targets for replication flows.



This topic contains the following sections:

-   [Supported Connection Type Features](integrating-data-via-connections-eb85e15.md#loioeb85e157ab654152bd68a8714036e463__section_connection_features)
-   [Connection Types Overview](integrating-data-via-connections-eb85e15.md#loioeb85e157ab654152bd68a8714036e463__section_connection_overview)
-   [Managing Connections](integrating-data-via-connections-eb85e15.md#loioeb85e157ab654152bd68a8714036e463__section_connection_management)



<a name="loioeb85e157ab654152bd68a8714036e463__section_connection_features"/>

## Supported Connection Type Features

Each connection type supports a defined set of features. Depending on the connection type and the connection configuration, a connection can be used for one or more of the following features:


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Remote Tables 

</td>
<td valign="top">

Allows modelers to import tables from a source when creating graphical and SQL views or entity-relationship models. During the import, the tables are deployed as remote tables. Depending on the connection type, you can use remote tables to:

-   directly access data in the source \(remote access\)

-   copy the full set of data \(snapshot or scheduled replication\)

-   copy data changes in real-time \(real-time replication\)


For more information, see:

-   [Importing Tables and Views from Sources](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/7c4acd33e39a451e99c87f0661772443.html "Import tables and views from a connection, Open SQL schema, HDI container or other source available in your space.") :arrow_upper_right:
-   [Replicating Data and Monitoring Remote Tables](../Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md)



</td>
</tr>
<tr>
<td valign="top">

Data Flows 

</td>
<td valign="top">

Allows modelers to use objects from a connected source when creating data flows to extract, transform and load data.

For more information, see [Creating a Data Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/e30fd1417e954577baae3246ea470c3f.html "Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

Model Import 

</td>
<td valign="top">

Allows modelers to import objects from any supporting SAP system with rich metadata and, if supported, with their dependencies. This way, you can leverage your existing investment in your customer system landscape without having to rebuild the objects manually.

For more information, see [Importing SAP BW∕4HANA Models](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/a3d4a2f91bea4810ba8839ff73577dac.html "You can import existing analytic queries from SAP BW∕4HANA into SAP Datasphere in order to build new models on top of them or enhance them.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

Replication Flows 

</td>
<td valign="top">

Allows modelers to replicate data from multiple source objects from a connected source to a target including simple projection and mapping capabilities.

You can enable a single initial load or request initial and delta loads to load changes at regular intervals. It depends on the connection type if you can use the connection as source or target connection.

For more information, see [Creating a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/25e2bd7a70d44ac5b05e844f9e913471.html "Create a replication flow if you want to copy multiple data assets from the same source to the same target in a fast and easy way and do not require complex projections.") :arrow_upper_right:.

</td>
</tr>
</table>

> ### Note:  
> Some connection types, such as SAP S/4HANA Cloud and on-premise or SAP ABAP, support replication with both remote tables via Data Provisioning Agent \(SAP HANA Smart Data Integration\) and replication flows.
> 
> Regardless of whether you use the same connection or two separate connections, for replicating data from a dedicated source object we strongly recommend to only use remote tables **or** replication flows and not both.

To allow space users using a feature, the feature must be enabled in the connection configuration. You can find more information about which features are supported by which connection type and what prerequisites and connection properties are required to enable \(or disable\) a feature from the links in the overview below.



<a name="loioeb85e157ab654152bd68a8714036e463__section_connection_overview"/>

## Connection Types Overview

To connect to remote systems, applications, databases, or storages, SAP Datasphere provides different connection types. The following connection types are available with SAP Datasphere:



****


<table>
<tr>
<th valign="top">

Connection Type

</th>
<th valign="top">

Remote Tables

\(Remote Access and Snapshot or Scheduled Replication\)

</th>
<th valign="top">

Replication Flows

</th>
<th valign="top">

Data Flows

</th>
<th valign="top">

Model Import

</th>
<th valign="top">

Category

</th>
<th valign="top">

Sources

</th>
</tr>
<tr>
<td valign="top">

[Adverity Connections](adverity-connections-63e9ff5.md)

</td>
<td valign="top">

\*

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Partner Tools

</td>
</tr>
<tr>
<td valign="top">

[Amazon Athena Connections](amazon-athena-connections-1b21cd0.md)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Amazon Redshift Connections](amazon-redshift-connections-8b13206.md)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Amazon Simple Storage Service Connections](amazon-simple-storage-service-connections-a7b660a.md)

</td>
<td valign="top">

no

</td>
<td valign="top">

yes \(target\)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Apache Kafka Connections](apache-kafka-connections-1992c6b.md)

</td>
<td valign="top">

no

</td>
<td valign="top">

yes \(target\)

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Cloud Data Integration Connections](cloud-data-integration-connections-cd33107.md)

</td>
<td valign="top">

yes \(including real-time replication\*\*\)

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[Generic JDBC Connections](generic-jdbc-connections-eeae3ac.md)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

On-Premise, Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Generic OData Connections](generic-odata-connections-5d36f1a.md)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

On-Premise, Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Generic SFTP Connections](generic-sftp-connections-b645de7.md)

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

On-Premise, Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Google BigQuery Connections](google-bigquery-connections-30ed77d.md)

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes \(target\)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Google Cloud Storage Connections](google-cloud-storage-connections-aec242c.md)

</td>
<td valign="top">

no

</td>
<td valign="top">

yes \(target\)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Hadoop Distributed File System Connections](hadoop-distributed-file-system-connections-f9c3356.md)

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Microsoft Azure Blob Storage Connections](microsoft-azure-blob-storage-connections-df5a7c5.md)

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Microsoft Azure Data Lake Store Gen1 Connections \(Deprecated\)](microsoft-azure-data-lake-store-gen1-connections-deprecated-aa04f9a.md)

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Microsoft Azure Data Lake Store Gen2 Connections](microsoft-azure-data-lake-store-gen2-connections-cd06b3c.md)

</td>
<td valign="top">

no

</td>
<td valign="top">

yes \(target\)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Microsoft Azure SQL Database Connections](microsoft-azure-sql-database-connections-46343fc.md)

</td>
<td valign="top">

yes \(including real-time replication\*\*\)

</td>
<td valign="top">

yes \(source\)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Microsoft SQL Server Connections](microsoft-sql-server-connections-a13c8ab.md)

</td>
<td valign="top">

yes \(including real-time replication\*\*\)

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

On-Premise

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Open Connectors Connections](open-connectors-connections-9bfe7db.md)

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[Oracle Connections](oracle-connections-c73ae06.md)

</td>
<td valign="top">

yes \(including real-time replication\*\*\)

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

On-Premise

</td>
<td valign="top">

Non SAP

</td>
</tr>
<tr>
<td valign="top">

[Precog Connections](precog-connections-6e5f225.md)

</td>
<td valign="top">

\*

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

Partner Tools

</td>
</tr>
<tr>
<td valign="top">

[SAP ABAP Connections](sap-abap-connections-a75c1aa.md)

</td>
<td valign="top">

yes \(including real-time replication\*\*\)

</td>
<td valign="top">

yes \(source\)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

On-Premise, Cloud

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[SAP BW Connections](sap-bw-connections-e589041.md)

</td>
<td valign="top">

yes \(including real-time replication\*\*\)

</td>
<td valign="top">

via connection type [SAP ABAP Connections](sap-abap-connections-a75c1aa.md) \(source\)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

On-Premise

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

\[generated and only available within a SAP BW bridge space if SAP BW bridge has been provisioned\] [Importing SAP BW Bridge Objects into SAP Datasphere](https://help.sap.com/viewer/e2d2b48377c14490b55466b5f1872640/DEV_CURRENT/en-US/34d1700f70444ea6a48a9d380d4cb0d5.html "You can use SAP BW bridge to model objects and import them into SAP Datasphere.") :arrow_upper_right:SAP Datasphere SAP BW bridge

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[SAP BW∕4HANA Model Transfer Connections](sap-bw-4hana-model-transfer-connections-1caba95.md)

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

On-Premise

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[SAP ECC Connections](sap-ecc-connections-e546ccd.md)

</td>
<td valign="top">

yes \(including real-time replication\*\*\)

</td>
<td valign="top">

via connection type [SAP ABAP Connections](sap-abap-connections-a75c1aa.md) \(source\)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

On-Premise

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[SAP Fieldglass Connections](sap-fieldglass-connections-bda94ee.md)

</td>
<td valign="top">

yes \(including real-time replication\*\*\)

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[SAP HANA Connections](sap-hana-connections-e6b63f1.md#loioe6b63f176d3640609adcf06297fb37e9)

</td>
<td valign="top">

yes \(including real-time replication\*\*\)

</td>
<td valign="top">

yes \(source and target\)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

On-Premise, Cloud

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[SAP HANA Cloud, Data Lake Files Connections](sap-hana-cloud-data-lake-files-connections-356e41e.md)

</td>
<td valign="top">

no

</td>
<td valign="top">

yes \(target\)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[SAP HANA Cloud, Data Lake Relational Engine Connections](sap-hana-cloud-data-lake-relational-engine-connections-40763e2.md)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[SAP Marketing Cloud Connections](sap-marketing-cloud-connections-4de4959.md)

</td>
<td valign="top">

yes \(including real-time replication\*\*\)

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[SAP SuccessFactors Connections](sap-successfactors-connections-39df020.md)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[SAP S/4HANA Cloud Connections](sap-s-4hana-cloud-connections-a98e5ff.md)

</td>
<td valign="top">

yes \(including real-time replication\*\*\)

</td>
<td valign="top">

yes \(source\)

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
<td valign="top">

Cloud

</td>
<td valign="top">

SAP

</td>
</tr>
<tr>
<td valign="top">

[SAP S/4HANA On-Premise Connections](sap-s-4hana-on-premise-connections-a49a1e3.md)

</td>
<td valign="top">

yes \(including real-time replication\*\*\)

</td>
<td valign="top">

yes \(source\)

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
<td valign="top">

On-Premise

</td>
<td valign="top">

SAP

</td>
</tr>
</table>

\*Data is pushed into the SAP Datasphere space by using the database user \(Open SQL schema\) SQL Interface. Typically, the push action is triggered from the partner tool. When data is pushed by the source, you can import a table from the *Sources* tab of the *Source Browser* panel in the Data Builder which is then deployed as local table \(see [Connections to Partner Tools](connections-to-partner-tools-55da0fa.md)\).

\*\* For more information about any constraints for using real-time replication, see [Replicate Data Changes in Real-Time](../Data-Integration-Monitor/replicate-data-changes-in-real-time-441d327.md).

\*\*\*Connections marked as "On-Premise" can be used to connect to sources located in the cloud, too. Note that in order to connect to a cloud-based SAP ABAP or Microsoft SQL Server, for example, you have to connect through the on-premise installed SAP HANA smart data integration Data Provisioning Agent.



<a name="loioeb85e157ab654152bd68a8714036e463__section_connection_management"/>

## Managing Connections

In the <span class="FPA-icons"></span> \(*Connections*\) app, you get an overview of all connections created in your space.

Use the following tools to create and manage connections:


<table>
<tr>
<th valign="top">

Tool

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Create

</td>
<td valign="top">

Create a connection to allow users assigned to the space to use the connected remote system for data modeling and data access in SAP Datasphere.

For more information, see [Create a Connection](create-a-connection-c216584.md).

</td>
</tr>
<tr>
<td valign="top">

Edit

</td>
<td valign="top">

Select and edit a connection to change its properties. Warnings might indicate that you need to edit a connection.

For more information, see [Edit a Connection](edit-a-connection-ba20892.md).

</td>
</tr>
<tr>
<td valign="top">

Delete

</td>
<td valign="top">

Select and delete one or more connections if they are not used anymore.

For more information, see [Delete a Connection](delete-a-connection-e90c290.md).

</td>
</tr>
<tr>
<td valign="top">

Validate

</td>
<td valign="top">

Select and validate a connection to get detailed status information and make sure that it can be used for data modeling and data access. Always validate a connection after you have created or edited it.

For more information, see [Validate a Connection](validate-a-connection-99bd229.md).

</td>
</tr>
<tr>
<td valign="top">

Pause/Restart

</td>
<td valign="top">

For connections that connect to a remote system through SAP HANA Smart Data Integration and its Data Provisioning Agent, you can pause and restart real-time replication for selected connections, if required.

For more information, see [Pause Real-Time Replication for a Connection](pause-real-time-replication-for-a-connection-a11f244.md).

</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons"></span> \(Reload Connection List\)

</td>
<td valign="top">

Reload the connections list to include the latest updates into the list.

</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons"></span> \(Sort Connections\)

</td>
<td valign="top">

Open the *Sort* dialog to control the ordering of the connections list.

By default, the list is sorted by *Business Name*. To sort on a specific column, select a *Sort Order* and a *Sort By* column, and then click *OK* to apply them.

</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons"></span> \(Filter Connections\)

</td>
<td valign="top">

Select one or more filter values to restrict the connection list according to your needs.

For more information, see [Filter Connection List](filter-connection-list-31f1075.md).

</td>
</tr>
<tr>
<td valign="top">

:gear:

</td>
<td valign="top">

Open the *Columns* dialog to control the display of columns in the results table.

Modify the column list in any of the following ways, and then click *OK* to apply your changes:

-   To select a column for display, select its checkbox. To hide a column deselect its checkbox.
-   Click on a column token to highlight it and use the arrow buttons to move it in the list.
-   Click *Reset* to go back to the default column display.



</td>
</tr>
<tr>
<td valign="top">

Search

</td>
<td valign="top">

Enter one or more characters in the *Search* field to restrict the list to connections containing the string.

Search considers the *Technical Name*, *Business Name*, *Real-Time Replication Status*, and *Owner* column.

</td>
</tr>
<tr>
<td valign="top">

![](images/2689954ed5874af480166f033f98b1bd.image)

\(Warning Messages\)

</td>
<td valign="top">

When there is one or more messages for your connections, a button is displayed on the top right corner of the *Connections* app specifying the number of warning messages for all connections in the list.

Click the button to open the list of messages. Clicking a message title selects the corresponding connection in the list. Clicking <span class="SAP-icons"></span> \(Navigation\) for a message opens a more detailed message containing guidance on how to solve the issue.

In the connections list, connections with warning messages are highlighted in yellow.

</td>
</tr>
</table>

