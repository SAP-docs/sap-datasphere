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

-   To be able to use ABAP Dictionary tables from connections to a SAP BW∕4HANA system for remote tables and creating views, please make sure that SAP note [2872997](https://launchpad.support.sap.com/#/notes/2872997) has been applied to the system.






<a name="loio76c9ac1a318c4de2bea29e72c64be8a0__prereq_df_SAP_ABAP"/>

## Data Flows

Before you can use the connection for data flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    In the Cloud Connector configuration, an administrator has made sure that access to the required resources is granted.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

    See also: SAP Note [2835207](https://launchpad.support.sap.com/#/notes/2835207) \(*ABAP connection type for SAP Data Intelligence*\)

-   For SAP S/4HANA, source version 1909 FPS01 plus SAP Note [2873666](https://launchpad.support.sap.com/#/notes/2873666) or higher versions are supported.

-   When connecting to SAP LT Replication Server:

    Connectivity to SAP LT Replication Server is supported for:

    -   Systems with Addon DMIS 2011 Support Package 19 or higher \(supporting SAP ECC 6.00 or higher\)

    -   Systems with Addon DMIS 2018 Support Package 4 or higher \(supporting SAP S/4HANA 1709 or higher\)

    -   SAP S/4HANA 2020 or higher


    Source systems connected to an SAP LT Replication Server are supported down to:

    -   version 4.6C via Addon DMIS 2010

    -   version 6.20 via Addon DMIS 2011


    In the ABAP-based system in which SAP LT Replication Server is installed, an administrator has created a configuration to specify the source system, the SAP LT Replication Server system and SAP Datasphere as target system.

    For more information, see [Creating a Configuration](https://help.sap.com/viewer/007c373fcacb4003b990c6fac29a26e4/latest/en-US/5a3be474248e4d758ba09a3d292ff1dc.html) in the *SAP Landscape Transformation Replication Server* documentation.

-   When connecting to SAP S/4HANA Cloud, an administrator has created a communication arrangement for the communication scenario `SAP_COM_0532` \(*SAP Data Hub – ABAP CDS Pipeline Integration*\) in the SAP S/4HANA Cloud system.

    For more information, see [Integrating CDS Views Using ABAP CDS Pipeline](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/f509eddda867452db9631dae1ae442a3.html) in the *SAP S/4HANA Cloud *documentation.




<a name="loio76c9ac1a318c4de2bea29e72c64be8a0__section_stp_5kk_qwb"/>

## Replication Flows

Before you can use the connection for replication flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

-   For table-based replication via SAP LT Replication Server, replication is supported for systems using:

    -   DMIS 2018 addon

    -   DMIS 2020 addon


-   ODP-based replication is supported for systems using:

    -   DMIS 2011 addon

    -   DMIS 2018 addon

    -   DMIS 2020 addon



For more information about integrating ABAP-based SAP systems, see [2890171](https://launchpad.support.sap.com/#/notes/2890171).

