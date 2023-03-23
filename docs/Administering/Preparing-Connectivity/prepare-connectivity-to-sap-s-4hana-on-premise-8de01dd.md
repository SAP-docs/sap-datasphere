<!-- loio8de01dd25c1e443e8e2de7d2fbe1364d -->

# Prepare Connectivity to SAP S/4HANA On-Premise

To be able to successfully validate and use a connection to SAP for remote tables or data flows, certain preparations have to be made.



<a name="loio8de01dd25c1e443e8e2de7d2fbe1364d__prereq_rt_S4_OP"/>

## Remote Tables

Before you can use the connection for creating views and accessing data via remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the ABAPAdapter.

    For the *Language* setting in the connection properties to have an effect on the language shown in the Data Builder, Data Provisioning Agent version 2.0 SP 05 Patch 10 \(2.5.1\) or higher is required.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   The ABAP user specified in the credentials of the SAP ABAP connection needs to have a specific set of authorizations in the SAP ABAP system. For more information, see: [Authorizations](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/bcc0ff2acd6a4476b2912ff4cd71cd91.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation.

-   If you want to stream ABAP tables for loading large amounts of data without running into memory issues, you need to configure suitable security privileges for successful registration on an SAP Gateway and you need to create an RFC destination of type TCP/IP in the ABAP source system. With the RFC destination you register the Data Provisioning Agent as server program in the source system. For more information, see [Prerequisites for ABAP RFC Streaming](prerequisites-for-abap-rfc-streaming-62adb44.md).




<a name="loio8de01dd25c1e443e8e2de7d2fbe1364d__prereq_df_S4_OP"/>

## Data Flows

Before you can use the connection for data flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

-   Supported source versions: SAP S/4HANA version 1909 FPS01 plus SAP Note [2873666](https://launchpad.support.sap.com/#/notes/2873666) \(*SAP Data Hub / Data Intelligence ABAP Integration - TCI note for SAP\_ABA 1909 SP0/SP1*\) or a higher SAP S/4HANA version




<a name="loio8de01dd25c1e443e8e2de7d2fbe1364d__section_stp_5kk_qwb"/>

## Replication Flows

Before you can use the connection for replication flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

-   For CDS views, replication is supported for version 1909 and later. TCI note implementation is required for:

    -   SAP S/4HANA 1909 with TCI Note [3105890](https://launchpad.support.sap.com/#/notes/3105890) and central note [2830276](https://launchpad.support.sap.com/#/notes/2830276).
    -   SAP S/4HANA 2020 with TCI Note [3105880](https://launchpad.support.sap.com/#/notes/3105880) and central note [2943599](https://launchpad.support.sap.com/#/notes/2943599).
    -   SAP S/4HANA 2021 with TCI Note [3115128](https://launchpad.support.sap.com/#/notes/3115128) and central note [3085579](https://launchpad.support.sap.com/#/notes/3085579).

    For information about which ABAP CDS Views are available for extraction, see [CDS Views Enabled for Data Extraction](https://help.sap.com/viewer/8308e6d301d54584a33cd04a9861bc52/latest/en-US/b7a5b8b72d3643b7a8ecf4cd695e0791.html) in the *SAP S/4HANA* documentation.

-   For table-based replication via SAP LT Replication Server, replication is supported for SAP S/4HANA 2022 and higher.

-   ODP-based replication is supported for ODP context ODP\_SAPI and ODP\_BW, and requires ODP API version 2.


For more information about integrating ABAP-based SAP systems, see [2890171](https://launchpad.support.sap.com/#/notes/2890171).

