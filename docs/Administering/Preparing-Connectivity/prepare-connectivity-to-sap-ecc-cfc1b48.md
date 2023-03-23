<!-- loiocfc1b487fc014c8aa14af81bfa15a82d -->

# Prepare Connectivity to SAP ECC

To be able to successfully validate and use a connection to SAP ECC for remote tables or data flows, certain preparations have to be made.



<a name="loiocfc1b487fc014c8aa14af81bfa15a82d__prereq_rt_SAPECC"/>

## Remote Tables

Before you can use the connection for creating views and accessing data via remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the ABAPAdapter.

    For the *Language* setting in the connection properties to have an effect on the language shown in the Data Builder, Data Provisioning Agent version 2.0 SP 05 Patch 10 \(2.5.1\) or higher is required.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   The ABAP user specified in the credentials of the SAP ABAP connection needs to have a specific set of authorizations in the SAP ABAP system. For more information, see: [Authorizations](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/bcc0ff2acd6a4476b2912ff4cd71cd91.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation.

-   If you want to stream ABAP tables for loading large amounts of data without running into memory issues, you need to configure suitable security privileges for successful registration on an SAP Gateway and you need to create an RFC destination of type TCP/IP in the ABAP source system. With the RFC destination you register the Data Provisioning Agent as server program in the source system. For more information, see [Prerequisites for ABAP RFC Streaming](prerequisites-for-abap-rfc-streaming-62adb44.md).




<a name="loiocfc1b487fc014c8aa14af81bfa15a82d__prereq_df_SAPECC"/>

## Data Flows

Before you can use the connection for data flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    In the Cloud Connector configuration, an administrator has made sure that access to the required resources is granted.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).


