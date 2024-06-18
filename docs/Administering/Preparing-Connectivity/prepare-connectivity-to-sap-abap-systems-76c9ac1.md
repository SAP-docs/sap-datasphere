<!-- loio76c9ac1a318c4de2bea29e72c64be8a0 -->

# Prepare Connectivity to SAP ABAP Systems

To be able to successfully validate and use a connection to an SAP ABAP system for remote tables or data flows, certain preparations have to be made.



## Remote Tables

Before you can use the connection for creating views and accessing data via remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the ABAPAdapter.

    For the *Language* setting in the connection properties to have an effect on the language shown in the Data Builder, Data Provisioning Agent version 2.0 SP 05 Patch 10 \(2.5.1\) or higher is required.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   The ABAP user specified in the credentials of the SAP ABAP connection needs to have a specific set of authorizations in the SAP ABAP system. For more information, see: [Authorizations](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/bcc0ff2acd6a4476b2912ff4cd71cd91.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation.

-   To access and copy data from SAP BW objects such as InfoProviders or characteristics, the appropriate authorization objects like S\_RS\_ADSO or S\_RS\_IOBJA are required for the ABAP user. For more information, see [Overview: Authorization Objects](https://help.sap.com/viewer/2e90b26cf7484203a523bf0f4b1bc137/7.5.latest/en-US/4c658f3245e31ca6e10000000a42189c.html) in the *SAP NetWeaver* documentation.

    If you want to access data from SAP BW Queries, make sure that the ABAP user has the required analysis authorizations to read the data and that characteristic 0TCAIPROV \(InfoProvider\) in the authorization includes `@Q`, which is the prefix for Queries as InfoProviders. For more information, see [Defining Analysis Authorizations](https://help.sap.com/viewer/2e90b26cf7484203a523bf0f4b1bc137/7.5.latest/en-US/4a27a9cf81661d10e10000000a42189b.html) in the *SAP NetWeaver* documentation.

-   If you want to stream ABAP tables for loading large amounts of data without running into memory issues, you need to configure suitable security privileges for successful registration on an SAP Gateway and you need to create an RFC destination of type TCP/IP in the ABAP source system. With the RFC destination you register the Data Provisioning Agent as server program in the source system. For more information, see [Prerequisites for ABAP RFC Streaming](prerequisites-for-abap-rfc-streaming-62adb44.md).

-   To be able to use ABAP Dictionary tables from connections to a SAP BW∕4HANA system for remote tables and creating views, please make sure that SAP note [2872997](https://me.sap.com/notes/2872997) has been applied to the system.






<a name="loio76c9ac1a318c4de2bea29e72c64be8a0__prereq_df_SAP_ABAP"/>

## Data Flows

> ### Note:  
> The availability of the replication flow feature depends on the used version and Support Package level of the ABAP-based SAP system \(SAP S/4HANA or the DMIS addon in the source\). Make sure your source systems meet the required minimum versions. We recommend to use the latest available version of SAP S/4HANA and the DMIS add-on where possible and have the latest SAP notes and TCI notes implemented in your systems.
> 
> For more information about required versions, recommended system landscape, considerations for the supported source objects, and more , see SAP Note [2890171](https://me.sap.com/notes/2890171).

Before you can use the connection for data flows, the following is required:

-   If the connected system is an on-premise source, an adminstrator has installed and configured Cloud Connector.

    In the Cloud Connector configuration, an administrator has made sure that access to the required resources is granted.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

    See also: SAP Note [2835207](https://me.sap.com/notes/2835207) \(*ABAP connection type for SAP Data Intelligence*\)

-   If you want to connect to SAP S/4HANA Cloud to replicate extraction-enabled, C1-released CDS views: Consider the information about preparing an SAP S/4HANA Cloud connection for data flows.

    For more information, see [Prepare Connectivity to SAP S/4HANA Cloud](prepare-connectivity-to-sap-s-4hana-cloud-abb159e.md).




<a name="loio76c9ac1a318c4de2bea29e72c64be8a0__section_stp_5kk_qwb"/>

## Replication Flows

> ### Note:  
> The availability of the replication flow feature depends on the used version and Support Package level of the ABAP-based SAP system \(SAP S/4HANA or the DMIS addon in the source\). Make sure your source systems meet the required minimum versions. We recommend to use the latest available version of SAP S/4HANA and the DMIS add-on where possible and have the latest SAP notes and TCI notes implemented in your systems.
> 
> For more information about required versions, recommended system landscape, considerations for the supported source objects, and more , see SAP Note [2890171](https://me.sap.com/notes/2890171).

Before you can use the connection for replication flows, the following is required:

-   If the connected system is an on-premise source, an adminstrator has installed and configured Cloud Connector.

    In the Cloud Connector configuration, an administrator has made sure that access to the required resources is granted.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

    See also: SAP Note [2835207](https://me.sap.com/notes/2835207) \(*ABAP connection type for SAP Data Intelligence*\)

-   If you want to connect to SAP S/4HANA Cloud to replicate extraction-enabled, C1-released CDS views or you want to replicate CDS view entities using the SQL service exposure: Consider the information about preparing an SAP S/4HANA Cloud connection for replication flows.

    For more information, see [Prepare Connectivity to SAP S/4HANA Cloud](prepare-connectivity-to-sap-s-4hana-cloud-abb159e.md).


**Related Information**  


[SAP ABAP Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a75c1aacf951449ba3b740c7e46da3a9.html "Use an SAP ABAP connection to access data from SAP ABAP on-premise systems through RFC or to access data from cloud source systems such as SAP S/4HANA Cloud through Web Socket RFC.") :arrow_upper_right:

