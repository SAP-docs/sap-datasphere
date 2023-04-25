<!-- loio586699519c83489bb77887823625ede8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Transfer Planning Data into SAP Datasphere

With the SAP Analytics Cloud Data Export Service \(DES\), you can simplify the downstream processing of plan data that was generated in SAP Analytics Cloud.



<a name="loio586699519c83489bb77887823625ede8__section_xf4_jfj_2vb"/>

## Transfer Planning Data Using the Cloud Data Integration Connection



### Prerequisites

The Cloud Connector has been installed and configured. For more information, see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f289920243a34127b0c8b13012a1a4b5.html "Set up and configure Cloud Connector before connecting to on-premise sources for data flows, replication flows, model import from SAP BW∕4HANA, and remote table access from SAP HANA on-premise (via SAP HANA smart data access). In the Cloud Connector administation, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:.

You have created a Cloud Data Integration connection to access SAP Analytics Cloud. For more information, see [Cloud Data Integration Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/cd33107246f446628f9baff56faf5a1b.html "Use a Cloud Data Integration connection to access data from SAP cloud applications which provide OData-based APIs for data integration and have a Cloud Data Integration (CDI) provider service implemented.") :arrow_upper_right:.



### Procedure

1.  Create a data flow: Select your SAC system as a source. For more information, see [Creating a Data Flow](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-data-flow-e30fd14.md).
2.  Select your data.
3.  Select the table in which you want to load your data as target.
4.  Connect source and target, deploy the data flow, and run the data flow.



<a name="loio586699519c83489bb77887823625ede8__section_ixv_jfj_2vb"/>

## Transfer Planning Data Using Remote Tables



### Prerequisites

An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the CloudDataIntegrationAdapter. For more information, see [Preparing Data Provisioning Agent Connectivity](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f1a39d1a763e48c8872f45c110a5a4e2.html "Most connection types that support creating views and accessing or replicating data via remote tables, for this purpose leverage SAP HANA Smart Data Integration (SDI) and its Data Provisioning Agent. Before using the connection, the agent requires an appropriate setup.") :arrow_upper_right:.



### Procedure

1.  1.  In the Data Builder, choose <span class="FPA-icons"></span> Import Remote Tables. All the available connections are listed.

2.  Select the connection to SAP Analytics Cloud.
3.  Select the objects with your planning data.
4.  Create a view. For more information, see [Creating a Graphical View](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-graphical-view-27efb47.md).

