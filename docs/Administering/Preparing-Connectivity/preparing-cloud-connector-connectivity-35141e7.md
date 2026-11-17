<!-- loio35141e7668774958b5e59495f7a7828e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Preparing Cloud Connector Connectivity

Connections to on-premise sources used for data flows, replication flows, and other use cases require Cloud Connector to act as link between SAP Datasphere and the source. Before creating the connection, the Cloud Connector requires an appropriate setup.



<a name="loio35141e7668774958b5e59495f7a7828e__section_iyq_hvz_4tb"/>

## Context

Cloud Connector serves as a link between SAP Datasphere and your on-premise sources and is required for connections that you want to use for:

-   Data flows

-   Replication flows

-   Model import from:

    -   SAP BW∕4HANA Model Transfer connections \(Cloud Connector is required for the live data connection of type tunnel that you need to create the model import connection\)

    -   SAP S/4HANA On-Premise connections \(Cloud Connector is required for the live data connection of type tunnel that you need to search for the entities in the SAP S/4HANA system\)


-   Remote tables \(only for SAP HANA on-premise via SAP HANA Smart Data Access\)

-   API tasks \(when using a Generic HTTP connection to a system in your local network\)

For an overview of on-premise connection types that require a Cloud Connector setup to be able to use any of these features, see [Preparing Connectivity for Connections](preparing-connectivity-for-connections-bffbd58.md).

You can also use a dedicated Cloud Connector instance in your customer virtual private network \(VPN\) as a TLS tunnel between the VPN and SAP Datasphere to privately route the data. This is supported for the following connection types:

-   [Amazon Simple Storage Service Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a7b660a0a4ef4a4fbee57b44f5b2147d.html "Use an Amazon Simple Storage Service connection to connect to and access data from objects in Amazon S3 buckets.") :arrow_upper_right:
-   [Confluent Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/d83c08ad4eaf49dba9602b1d51c07a52.html#loiod83c08ad4eaf49dba9602b1d51c07a52 "Use the connection to connect to Apache Kafka hosted on either the Confluent Platform or Confluent Cloud. The connection type has two endpoints: the Kafka brokers and the Schema Registry.") :arrow_upper_right:
-   [Google BigQuery Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/30ed77de13864368bdc596099b37ed70.html "Use the connection to connect to and access data from Google BigQuery.") :arrow_upper_right:
-   [Google Cloud Storage Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/aec242c29188408c9ebe1a3ab63ce28b.html "Use the connection to connect to and access objects from Google Cloud Storage.") :arrow_upper_right:
-   [Microsoft Azure Data Lake Storage Gen2 Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/cd06b3c5ab5147c0905e3fa8abd13eb1.html "Use the connection to connect to and access objects in Microsoft Azure Data Lake Gen2 (ADL Gen2).") :arrow_upper_right:
-   [Microsoft Azure SQL Database Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/46343fc1c4544fa9a075d97f84d39826.html "Use a Microsoft Azure SQL Database connection to access table data from a Microsoft Azure SQL database.") :arrow_upper_right:
-   [Microsoft OneLake Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/057fa4b51c734e679dd70eec9514839d.html "Use the connection to connect to and access objects in Microsoft OneLake.") :arrow_upper_right:
-   [Snowflake Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/d9ead8bb44ac456d99a141b4e3f5e973.html "Use the connection to connect to and access data from a Snowflake database.") :arrow_upper_right:



<a name="loio35141e7668774958b5e59495f7a7828e__section_j3m_4vz_4tb"/>

## Procedure

To prepare connectivity via Cloud Connector, perform the following steps:

1.  Install the Cloud Connector in your on-premise network.

    For more information, see [Cloud Connector Installation](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/57ae3d62f63440f7952e57bfcef948d3.html) in the *SAP BTP Connectivity* documentation.

2.  Make sure to hold the SAP Datasphere subaccount information ready. You can find the information in <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *Data Source Configuration*.

    For more information, see [Set Up Cloud Connector in SAP Datasphere](set-up-cloud-connector-in-sap-datasphere-6de74f7.md).

3.  In the Cloud Connector administration, set up and configure Cloud Connector according to your requirements.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

4.  If you have connected multiple Cloud Connector instances to your subaccount and you want to use these locations for your connections, add the location IDs in <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *Data Source Configuration*.

    For more information, see [Set Up Cloud Connector in SAP Datasphere](set-up-cloud-connector-in-sap-datasphere-6de74f7.md).

5.  If you you want to create SAP BW∕4HANA Model Transfer connections or SAP S/4HANA On-Premise connections for model import, make sure you have switched on *Allow live data to securely leave my network* in <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *Data Source Configuration*.

    For more information, see [Set Up Cloud Connector in SAP Datasphere](set-up-cloud-connector-in-sap-datasphere-6de74f7.md).




<a name="loio35141e7668774958b5e59495f7a7828e__section_stc_svz_4tb"/>

## Result

The Cloud Connector respectively Cloud Connector instances are available for creating connections and enabling these for the supported features.



<a name="loio35141e7668774958b5e59495f7a7828e__section_vpb_spb_s5b"/>

## Related Links

[Frequently Asked Questions \(about the Cloud Connector\)](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/f8d6f9ab43c14e52a9e8036515a472e9.html) in the *SAP BTP Connectivity* documentation

