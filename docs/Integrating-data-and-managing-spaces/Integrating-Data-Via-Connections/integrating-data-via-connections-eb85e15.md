<!-- loioeb85e157ab654152bd68a8714036e463 -->

# Integrating Data via Connections

Connections provide access to data from a wide range of sources, cloud as well as on-premise sources, SAP as well as Non-SAP sources, and partner tools. They allow space members to use objects from the connected source to acquire, prepare and access data from those sources in SAP Datasphere. To connect to different sources, SAP Datasphere provides different connection types.



This topic contains the following sections:

-   [Supported Connection Type Features](integrating-data-via-connections-eb85e15.md#loioeb85e157ab654152bd68a8714036e463__section_connection_features)
-   [Connection Types Overview](integrating-data-via-connections-eb85e15.md#loioeb85e157ab654152bd68a8714036e463__section_connection_overview)



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

-   [Importing Tables and Views from Sources](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/7c4acd33e39a451e99c87f0661772443.html "Import tables and views from a connection, Open SQL schema, HDI container or other source available in your space.") :arrow_upper_right:
-   [Replicating Data and Monitoring Remote Tables](../Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md)



</td>
</tr>
<tr>
<td valign="top">

 Data Flows 



</td>
<td valign="top">

Allows modelers to use objects from a connected source when creating data flows to extract, transform and load data.

For more information, see [Creating a Data Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/e30fd1417e954577baae3246ea470c3f.html "Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

 Model Import 



</td>
<td valign="top">

Allows modelers to import objects from any supporting SAP system with rich metadata and, if supported, with their dependencies. This way, you can leverage your existing investment in your customer system landscape without having to rebuild the objects manually.

For more information, see [Importing SAP BW∕4HANA Models](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/a3d4a2f91bea4810ba8839ff73577dac.html "You can import existing analytic queries from SAP BW∕4HANA into SAP Datasphere in order to build new models on top of them or enhance them.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

 Replication Flows 



</td>
<td valign="top">

Allows modelers to replicate data from multiple source objects from a connected source to a target including simple projection and mapping capabilities.

You can enable a single initial load or request initial and delta loads to load changes at regular intervals. It depends on the connection type if you can use the connection as source or target connection.

For more information, see [Creating a Replication Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/25e2bd7a70d44ac5b05e844f9e913471.html "Create a replication flow if you want to copy multiple data assets from the same source to the same target in a fast and easy way and do not require complex projections.") :arrow_upper_right:.



</td>
</tr>
</table>

> ### Note:  
> Some connection types, such as SAP S/4HANA Cloud and on-premise or SAP ABAP, support replication with both remote tables via Data Provisioning Agent \(SAP HANA Smart Data Integration\) and replication flows.
> 
> Regardless of whether you use the same connection or two separate connections, for replicating data from a dedicated source object we strongly recommend to only use remote tables **or** replication flows and not both.

To allow space members using a feature, the feature must be enabled in the connection configuration. You can find more information about which features are supported by which connection type and what prerequisites and connection properties are required to enable \(or disable\) a feature from the links in the overview below.



<a name="loioeb85e157ab654152bd68a8714036e463__section_connection_overview"/>

## Connection Types Overview

The following connection types are available with SAP Datasphere:



** **


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

[Google Cloud Storage Connections](google-cloud-storage-connections-aec242c.md)



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

[Microsoft Azure Data Lake Store Gen1 Connections](microsoft-azure-data-lake-store-gen1-connections-aa04f9a.md)



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

\[generated and only available within a SAP BW bridge space if SAP BW bridge has been provisioned\] [SAP Datasphere SAP BW bridge](https://help.sap.com/viewer/07fda46007d24ff7b8af36b26f9b9634/cloud/en-US/03cc8f27d3a44aabad3debaa79be0216.html "") :arrow_upper_right:



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

no



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

> ### Note:  

