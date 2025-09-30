<!-- loio94562426f30c475286f50a1e2b45e743 -->

# Connection Types

To connect to remote systems, applications, databases, or storages, SAP Datasphere provides different connection types.

The following connection types are available with SAP Datasphere.

> ### Note:  
> Spaces with storage type *SAP HANA Database \(Disk and In-Memory\)* offer all connection types.
> 
> Spaces with storage type *SAP HANA Data Lake Files* \(file spaces\) provide a subset of connection types \(see column *Available in File Spaces* below\). In file spaces, the connection types only support replication flows. Remote tables, data flows, and model import are not supported in file spaces.

****


<table>
<tr>
<th valign="top">

Connection Type

</th>
<th valign="top">

Supported in File Spaces

</th>
<th valign="top">

Remote Tables

\(remote access and snapshot or scheduled replication\)

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

no

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

no

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

no

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

yes \(source and target\)

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

yes

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

[Business Data Product Connections](business-data-product-connections-5661d88.md)

\[created when installing an SAP Business Data Cloud data product from the connected system for the first time and only available within an SAP-managed ingestion space\]

</td>
<td valign="top">

no

</td>
<td valign="top">

not applicable

</td>
<td valign="top">

not applicable

\(replication flows are created and deployed via the data product installation\)

</td>
<td valign="top">

not applicable

</td>
<td valign="top">

not applicable

</td>
<td valign="top">

not applicable

</td>
<td valign="top">

not applicable

</td>
</tr>
<tr>
<td valign="top">

[Cloud Data Integration Connections](cloud-data-integration-connections-cd33107.md)

</td>
<td valign="top">

no

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

[Confluent Connections](confluent-connections-d83c08a.md#loiod83c08ad4eaf49dba9602b1d51c07a52)

</td>
<td valign="top">

yes

</td>
<td valign="top">

no

</td>
<td valign="top">

yes \(source and target\)

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

[Generic HTTP Connections](generic-http-connections-b79b865.md)

\[enables API tasks in task chains\]

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

no

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

[Generic JDBC Connections](generic-jdbc-connections-eeae3ac.md)

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

no

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

yes

</td>
<td valign="top">

no

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

no

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

yes \(source and target\)

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

yes

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

[Microsoft OneLake Connections](microsoft-onelake-connections-057fa4b.md)

</td>
<td valign="top">

no

</td>
<td valign="top">

no

</td>
<td valign="top">

yes \(source\)

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

[Microsoft SQL Server Connections](microsoft-sql-server-connections-a13c8ab.md)

</td>
<td valign="top">

yes

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

no

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

no

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

yes

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

no

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

[SAP Datasphere, SAP BW bridge Connection](https://help.sap.com/viewer/e2d2b48377c14490b55466b5f1872640/DEV_CURRENT/en-US/34d1700f70444ea6a48a9d380d4cb0d5.html "You can use SAP BW bridge to model objects and import them into SAP Datasphere.") :arrow_upper_right:

\[generated and only available within an SAP BW bridge space if SAP BW bridge has been provisioned\]

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

no

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

no

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

no

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

yes

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

yes

</td>
<td valign="top">

no

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

no

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

no

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

[SAP Signavio Connections](sap-signavio-connections-4c367de.md)

</td>
<td valign="top">

yes

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

SAP

</td>
</tr>
<tr>
<td valign="top">

[SAP SuccessFactors Connections](sap-successfactors-connections-39df020.md)

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

yes

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

yes

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

