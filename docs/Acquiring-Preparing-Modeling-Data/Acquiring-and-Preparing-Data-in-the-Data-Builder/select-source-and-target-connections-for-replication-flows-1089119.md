<!-- loio10891192186c4920b08939a7b46adc79 -->

# Select Source and Target Connections for Replication Flows

Select the source connection you want to read data from and the target connection you want to replicate data to.

Replication flows support up to three load types:

-   `I`: *Initial Only* - Replicate the data present in the source object at the start of the run and then finish.
-   `ID`: *Initial and Delta* - Replicate the data from the object at the start of the run and then continue to replicate any changes \(inserted, updated, deleted records\) at specified intervals \(or scheduled times\).
-   `D`: *Delta Only* - Ignore data present in the source object at the start of the run, and replicate only subsequent changes \(inserted, updated, deleted records\) at specified intervals \(or scheduled times\).

The following table displays connection types, their availability as sources and/or targets and the load types they support. Your selected source connection and target connection must both support the load type that you want to use:


<table>
<tr>
<th valign="top">

Connection Type

</th>
<th valign="top">

Source Load Types

</th>
<th valign="top">

Target Load Types

</th>
<th valign="top">

Links

</th>
</tr>
<tr>
<td valign="top">

SAP Datasphere \(standard space\)

</td>
<td valign="top">

`I-ID-D` \*

</td>
<td valign="top">

`I-ID--` \*

</td>
<td valign="top">

Use as: [Target](sap-datasphere-targets-for-replication-flows-12c45eb.md)

</td>
</tr>
<tr>
<td valign="top">

SAP Datasphere \(file space\)

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

`I-ID--` \*

</td>
<td valign="top">

Use as: [Target](sap-datasphere-targets-for-replication-flows-12c45eb.md)

</td>
</tr>
<tr>
<td valign="top">

Amazon Simple Storage Service

</td>
<td valign="top">

`I-----`

</td>
<td valign="top">

`I-ID-D`

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a7b660a0a4ef4a4fbee57b44f5b2147d.html "Use an Amazon Simple Storage Service connection to connect to and access data from objects in Amazon S3 buckets.") :arrow_upper_right: | Use as: [Source](cloud-storage-provider-sources-for-replication-flows-4d481a2.md) | [Target](cloud-storage-provider-targets-for-replication-flows-43d93a2.md)

</td>
</tr>
<tr>
<td valign="top">

Apache Kafka

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

`I-ID-D`

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/1992c6b7154c4bc080d83c8977382ff4.html "Use the connection to connect to an Apache Kafka cluster.") :arrow_upper_right: | Use as: [Target](apache-kafka-targets-for-replication-flows-6df55db.md)

</td>
</tr>
<tr>
<td valign="top">

Confluent

</td>
<td valign="top">

`--ID--`

</td>
<td valign="top">

`I-ID-D`

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/d83c08ad4eaf49dba9602b1d51c07a52.html#loiod83c08ad4eaf49dba9602b1d51c07a52 "Use the connection to connect to Apache Kafka hosted on either the Confluent Platform or Confluent Cloud. The connection type has two endpoints: the Kafka brokers and the Schema Registry.") :arrow_upper_right: | Use as: [Source](confluent-kafka-sources-for-replication-flows-4f2d0a8.md) | [Target](confluent-kafka-targets-for-replication-flows-74b3c95.md)

</td>
</tr>
<tr>
<td valign="top">

Generic SFTP

</td>
<td valign="top">

`I-----`

</td>
<td valign="top">

`I-ID--`

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/b645de78a8374c24871ab6169be40d35.html "Use a Generic SFTP connection to connect to and access files on a Secure File Transfer Protocol (SFTP) server.") :arrow_upper_right: | Use as [Source](secure-file-transfer-protocol-sftp-sources-for-replication-flows-a832ef4.md) | [Target](secure-file-transfer-protocol-sftp-for-replication-flows-5a14eb1.md)

</td>
</tr>
<tr>
<td valign="top">

Google BigQuery

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

`I-ID-D`

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/30ed77de13864368bdc596099b37ed70.html "Use the connection to connect to and access data from Google BigQuery.") :arrow_upper_right: | Use as: [Target](google-bigquery-targets-for-replication-flows-56d4472.md)

</td>
</tr>
<tr>
<td valign="top">

Google Cloud Storage

</td>
<td valign="top">

`I-----`

</td>
<td valign="top">

`I-ID-D`

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/aec242c29188408c9ebe1a3ab63ce28b.html "Use the connection to connect to and access objects from Google Cloud Storage.") :arrow_upper_right: | Use as: [Source](cloud-storage-provider-sources-for-replication-flows-4d481a2.md) | [Target](cloud-storage-provider-targets-for-replication-flows-43d93a2.md)

</td>
</tr>
<tr>
<td valign="top">

Microsoft Azure Data Lake Gen2

</td>
<td valign="top">

`I-----`

</td>
<td valign="top">

`I-ID-D`

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/cd06b3c5ab5147c0905e3fa8abd13eb1.html "Use the connection to connect to and access objects in Microsoft Azure Data Lake Gen2 (ADL Gen2).") :arrow_upper_right: | Use as: [Source](cloud-storage-provider-sources-for-replication-flows-4d481a2.md) | [Target](cloud-storage-provider-targets-for-replication-flows-43d93a2.md)

</td>
</tr>
<tr>
<td valign="top">

Microsoft Azure SQL Database

</td>
<td valign="top">

`I-ID-D`

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/46343fc1c4544fa9a075d97f84d39826.html "Use a Microsoft Azure SQL Database connection to access table data from a Microsoft Azure SQL database.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Microsoft OneLake

</td>
<td valign="top">

`I-----`

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/057fa4b51c734e679dd70eec9514839d.html "Use the connection to connect to and access objects in Microsoft OneLake.") :arrow_upper_right: | Use as: [Source](cloud-storage-provider-sources-for-replication-flows-4d481a2.md) |

</td>
</tr>
<tr>
<td valign="top">

Microsoft SQL Server

</td>
<td valign="top">

`I-ID-D`

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a13c8abb328f45be891599c9cc76fb91.html "Use a Microsoft SQL Server connection to access data from a Microsoft SQL Server database (on-premise).") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

SAP ABAP

</td>
<td valign="top">

`I-ID-D` \*\*

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a75c1aacf951449ba3b740c7e46da3a9.html "Use an SAP ABAP connection to access data from ABAP-based on-premise or cloud systems.") :arrow_upper_right: | Use as: [Source](sap-s-4hana-and-other-abap-sources-for-replication-flows-3f70579.md)

</td>
</tr>
<tr>
<td valign="top">

SAP BW

</td>
<td valign="top">

`I-----`

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e589041e80264f43b6c209c407336376.html "Use an SAP BW connection to access data from SAP Business Warehouse (SAP BW) or SAP BW∕4HANA systems.") :arrow_upper_right: | Use as: [Source](sap-ecc-and-sap-bw-sources-for-replication-flows-c7accb3.md)

</td>
</tr>
<tr>
<td valign="top">

SAP ECC

</td>
<td valign="top">

`I-----`

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e546ccd61af54bf49a0f531a43fe0961.html "Use an SAP ECC connection to access data from SAP ERP Central Component (SAP ECC) systems (on-premise).") :arrow_upper_right: | Use as: [Source](sap-ecc-and-sap-bw-sources-for-replication-flows-c7accb3.md)

</td>
</tr>
<tr>
<td valign="top">

SAP HANA

</td>
<td valign="top">

`I-ID-D`

</td>
<td valign="top">

`I-ID--`

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e6b63f176d3640609adcf06297fb37e9.html#loioe6b63f176d3640609adcf06297fb37e9 "Use an SAP HANA connection to access data from a remote SAP HANA database (on-premise or cloud).") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

SAP HANA Cloud, Data Lake Files

</td>
<td valign="top">

`I-ID-D`

</td>
<td valign="top">

`I-ID-D`

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/356e41e880e54255891b702d2afefeb3.html "Use an SAP HANA Cloud, Data Lake Files connection to access data from the Files component of a standalone SAP HANA Cloud, data lake.") :arrow_upper_right: | Use as:  <?sap-ot O2O class="- topic/xref " href="84405b0d00d543dc846fe19262c60682.xml" text="Source" desc="" xtrc="xref:38" xtrf="file:/home/builder/src/dita-all/ypt1776854185315/loioc25299a38b6448f889a43b42c9e5897d_en-US/src/content/localization/en-us/10891192186c4920b08939a7b46adc79.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

</td>
</tr>
<tr>
<td valign="top">

SAP Signavio

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

`I-ID--`

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4c367de075a44ad7b7a6db576a4a9c82.html "Use the connection to securely integrate SAP systems such as SAP S/4HANA on-premise with SAP Signavio using replication flows for efficient and scalable data replication to SAP Signavio Process Intelligence.") :arrow_upper_right: | Use as: [Target](sap-signavio-targets-for-replication-flows-b8f5e28.md)

</td>
</tr>
<tr>
<td valign="top">

SAP S/4HANA Cloud

</td>
<td valign="top">

`I-ID-D` \*\*

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a98e5ffdf47c44d9a845dca01a18bd82.html "Use an SAP S/4HANA Cloud connection to access or import extraction-enabled ABAP Core Data Services views (ABAP CDS views) from SAP S/4HANA Cloud.") :arrow_upper_right: | Use as: [Source](sap-s-4hana-and-other-abap-sources-for-replication-flows-3f70579.md)

</td>
</tr>
<tr>
<td valign="top">

SAP S/4HANA On-Premise

</td>
<td valign="top">

`I-ID-D` \*\*

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

[Create](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a49a1e3cc50f4af89711d8306bdd8f26.html "Use an SAP S/4HANA On-Premise connection to access data from SAP S/4HANA on-premise systems.") :arrow_upper_right: | Use as: [Source](sap-s-4hana-and-other-abap-sources-for-replication-flows-3f70579.md)

</td>
</tr>
</table>

\*SAP Datasphere support for run types depends on the space type and the Delta Capture setting:


<table>
<tr>
<th valign="top">

Space Type

</th>
<th valign="top">

Source Run Types

</th>
<th valign="top">

Target Run Types

</th>
</tr>
<tr>
<td valign="top">

Standard Space / Local Tables

</td>
<td valign="top">

-   Delta Capture Off: `I-----`
-   Delta Capture On: `I-ID-D`



</td>
<td valign="top">

-   Delta Capture Off: `I-ID--`
-   Delta Capture On: `--ID--`



</td>
</tr>
<tr>
<td valign="top">

File Space / Local Tables \(File\)

</td>
<td valign="top">

-   Delta Capture Off: `------`
-   Delta Capture On: `------`



</td>
<td valign="top">

-   Delta Capture Off: `------`
-   Delta Capture On: `I-ID-D`



</td>
</tr>
</table>

\*\* To support delta-enabled runs for SAP ABAP source connections:

-   you must add the appropriate `@Analytics` annotations to the ABAP source view:

    ```
    @Analytics:{
        dataExtraction: {
            enabled: true,
            delta.changeDataCapture.automatic: true
        }
    }
    ```

    For detailed information, see [Deep Dive 1.2 - Extraction and Delta enablement for simple ABAP CDS Views](https://github.com/SAP-samples/teched2023-DA260/tree/main/exercises/dd1#deep-dive-12---extraction-and-delta-enablement-for-simple-abap-cds-views).

-   CDS and ODP source objects without a primary key only support *Initial Only* runs.

