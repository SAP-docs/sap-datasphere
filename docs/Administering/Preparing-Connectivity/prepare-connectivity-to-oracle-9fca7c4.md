<!-- loio9fca7c484e974429afc6570196303c35 -->

# Prepare Connectivity to Oracle

To be able to successfully validate and use a connection to an Oracle database for remote tables or data flows, certain preparations have to be made.



<a name="loio9fca7c484e974429afc6570196303c35__prereq_rt_Oracle"/>

## Remote Tables

Before you can use the connection for remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the OracleLogReaderAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   An administrator has downloaded and installed the required JDBC library in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/lib</code> folder before registering the adapter with SAP Datasphere.

    For more information about the supported JDBC libraries, see the [SAP HANA smart data integration and all its patches Product Availability Matrix \(PAM\) for SAP HANA SDI 2.0](https://support.sap.com/content/dam/launchpad/en_us/pam/pam-essentials/TIP/PAM_HANA_SDI_2_0.pdf). Search for the required library in the internet and download it from an appropriate web page.

-   [Required Permissions for Oracle Trigger-Based Replication](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/bd79ed316a1447ffb1fbd3757aff9c71.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*

-   If encrypted communication is used \(connection is configured to use SSL\), the server certificate must be uploaded to the Data Provisioning Agent.

    To retrieve the certificate, you can use for example the following command: `openssl s_client -showcerts -servername <host name of the Oracle database server>:<port number of the Oracle database server> -connect <host name of the Oracle database server>:<port number of the Oracle database server>`

    For more information about uploading the certificate to the Data Provisioning Agent, see:

    -   [Configure the Adapter Truststore and Keystore](https://help.sap.com/docs/HANA_SMART_DATA_INTEGRATION/7952ef28a6914997abc01745fef1b607/1d0259de04e247d994258429b34b8546.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation
    -   [Configure SSL for the Oracle Log Reader Adapter](https://help.sap.com/docs/HANA_SMART_DATA_INTEGRATION/7952ef28a6914997abc01745fef1b607/03c4f2f0629d40f28d333723a820a0d4.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation




<a name="loio9fca7c484e974429afc6570196303c35__prereq_df_Oracle"/>

## Data Flows

Before you can use the connection for data flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

    > ### Note:  
    > Cloud Connector is not required if your Oracle database is available on the public internet.

-   A DW administrator has uploaded the required ODBC driver file to SAP Datasphere.

    To use encrypted communication \(connection is configured to use SSL\), additional files are required to be uploaded.

    For more information, see [Upload Third-Party ODBC Drivers \(Required for Data Flows\)](upload-third-party-odbc-drivers-required-for-data-flows-b9b5579.md).

-   A DW administrator has uploaded the server certificate to SAP Datasphere.

    To retrieve the certificate, you can use for example the following command: `openssl s_client -showcerts -servername <host name of the Oracle database server>:<port number of the Oracle database server> -connect <host name of the Oracle database server>:<port number of the Oracle database server>`

    For more information, see [Manage Certificates for Connections](manage-certificates-for-connections-46f5467.md).


**Related Information**  


[Oracle Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/c73ae0601d364f47830d339b6e86b7e8.html "Use the connection to connect to and access data from an Oracle database (on-premise).") :arrow_upper_right:

