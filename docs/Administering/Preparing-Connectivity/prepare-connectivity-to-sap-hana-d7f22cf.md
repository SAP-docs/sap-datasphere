<!-- loiod7f22cffa3d443669fec3003971e7638 -->

# Prepare Connectivity to SAP HANA

To be able to successfully validate and use a connection to SAP HANA Cloud or SAP HANA \(on-premise\) for remote tables or data flows certain preparations have to be made.



<a name="loiod7f22cffa3d443669fec3003971e7638__section_zt1_2l1_z4b"/>

## SAP HANA Cloud

A DW administrator has uploaded the server certificate to SAP Datasphere.

For more information, see [Manage Certificates for Connections](manage-certificates-for-connections-46f5467.md).



<a name="loiod7f22cffa3d443669fec3003971e7638__section_iz1_bm1_z4b"/>

## SAP HANA on-premise





### Remote Tables

Before you can use the connection for creating views and accessing data via remote tables, the following is required:

-   If you want to use SAP HANA Smart Data Integration:

    -   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the HanaAdapter.

        For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

    -   If you use encrypted communication \(see the *Security* properties in the connection creation wizard\):

        An administrator has already correctly configured Data Provisioning Agent for SSL support.

        For more information, see [Configure SSL for SAP HANA On-Premise \[Manual Steps\]](https://help.sap.com/docs/HANA_SMART_DATA_INTEGRATION/7952ef28a6914997abc01745fef1b607/caeef0265b14482eb355b101c9cb92df.html?version=latest) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation.


-   If you want to use SAP HANA Smart Data Access:

    -   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

        For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

    -   An administrator has added the Cloud Connector IP address to the IP allowlist.

        For more information, see [Add IP address to IP Allowlist](add-ip-address-to-ip-allowlist-a3c2145.md).

    -   If you use encrypted communication and the server certificate should be validated \(see the *Security* properties in the connection creation wizard\):

        A DW administrator has uploaded the server certificate to SAP Datasphere.

        For more information, see [Manage Certificates for Connections](manage-certificates-for-connections-46f5467.md).





### Data Flows and Replication Flows

For SAP HANA \(on-premise\), before you can use the connection for data flows and replication flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).


