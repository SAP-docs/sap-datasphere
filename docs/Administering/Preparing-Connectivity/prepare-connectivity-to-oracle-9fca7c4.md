<!-- loio9fca7c484e974429afc6570196303c35 -->

# Prepare Connectivity to Oracle

To be able to successfully validate and use a connection to an Oracle database for remote tables or data flows, certain preparations have to be made.



<a name="loio9fca7c484e974429afc6570196303c35__prereq_rt_Oracle"/>

## Remote Tables

Before you can use the connection for creating views and accessing data via remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the OracleLogReaderAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   An administrator has downloadad and installed the required JDBC library in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/lib</code> folder before registering the adapter with SAP Datasphere.

-   [Required Permissions for Oracle Trigger-Based Replication](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/bd79ed316a1447ffb1fbd3757aff9c71.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*




<a name="loio9fca7c484e974429afc6570196303c35__prereq_df_Oracle"/>

## Data Flows

Before you can use the connection for data flows, the following is required:

-   To directly consume data in data flows, the Oracle database must be available on the public internet.

-   A DW administrator has uploaded the required ODBC driver file to SAP Datasphere.

    To use encrypted communication \(connection is configured to use SSL\), additional files are required to be uploaded.

    For more information, see [Upload Third-Party ODBC Drivers \(Required for Data Flows\)](upload-third-party-odbc-drivers-required-for-data-flows-b9b5579.md).

-   A DW administrator has uploaded the server certificate to SAP Datasphere.

    For more information, see [Manage Certificates for Connections](manage-certificates-for-connections-46f5467.md).


