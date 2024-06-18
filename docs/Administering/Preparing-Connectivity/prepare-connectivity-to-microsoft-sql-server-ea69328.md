<!-- loioea69328fb328449ab7b04d2b142592f8 -->

# Prepare Connectivity to Microsoft SQL Server

To be able to successfully validate and use a connection to a Microsoft SQL Server for remote tables or data flows, certain preparations have to be made.



<a name="loioea69328fb328449ab7b04d2b142592f8__prereq_rt_MSSQL"/>

## Remote Tables

Before you can use the connection for creating views and accessing data via remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the MssqlLogReaderAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   An administrator has downloadad and installed the required JDBC library in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/lib</code> folder before registering the adapter with SAP Datasphere.

-   [Required Permissions for SQL Server Trigger-Based Replication](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/2815e1a621f84bada5fa3447d5029eb6.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*




<a name="loioea69328fb328449ab7b04d2b142592f8__prereq_df_MSSQL"/>

## Data Flows

Before you can use the connection for data flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

    > ### Note:  
    > Cloud Connector is not required if your Microsoft SQL Server database is available on the public internet.

-   The required driver is pre-bundled and doesn't need to be uploaded by an administrator.


**Related Information**  


[Microsoft SQL Server Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a13c8abb328f45be891599c9cc76fb91.html "Use a Microsoft SQL Server connection to access data from a Microsoft SQL Server database (on-premise).") :arrow_upper_right:

