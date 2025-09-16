<!-- loiocfc1b487fc014c8aa14af81bfa15a82d -->

# Prepare Connectivity to SAP ECC

To be able to successfully validate and use a connection to SAP ECC for remote tables or data flows, certain preparations have to be made.



<a name="loiocfc1b487fc014c8aa14af81bfa15a82d__prereq_rt_SAPECC"/>

## Remote Tables

Before you can use the connection for remote tables, the following is required:

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

-   If you want to enable secure network communication \(SNC\) to an ABAP-based on-premise system, which you want to connect to for using data flows, configure SNC in the Cloud Connector and consider the SNC-specific settings when adding the system mapping information:

    -   In the *Back-end Type* field, select *ABAP System*.
    -   In the *Protocol* field, select *RFC SNC*.
    -   In the *Principal Type* field, select *X.509 Certificate*.
    -   In the *SNC Partner Name* field, enter the ABAP system's SNC identity name \(for example, `p:CN=SID, O=Trust Community, C=DE`\). The SNC partner name needs to contain the correct SNC identification of the ABAP system. The value can typically be found in the ABAP system instance profile parameter `snc/identity/as` \(and hence is provided per application server\).

    For more information about configuring SNC, see [Initial Configuration \(RFC\)](https://help.sap.com/viewer/DRAFT/cca91383641e40ffbe03bdc78f00f681/Validation/en-US/f09eefe71d1e4d4484e1dd4b121585fb.html) in the *SAP BTP Connectivity* documentation.


**Related Information**  


[SAP ECC Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/e546ccd61af54bf49a0f531a43fe0961.html "Use an SAP ECC connection to access data from virtual tables through RFC for ODP sources (extractors) and ABAP Dictionary tables from SAP ERP Central Component (SAP ECC) systems (on-premise). For source systems that don't have the ABAP Pipeline Engine extension installed, ODP extractors can be used as sources in data flows.") :arrow_upper_right:

