<!-- loio782bd8c0d71943a9a6febee5f1557c80 -->

# Prepare Connectivity to Microsoft Azure SQL Database

To be able to successfully validate and use a connection to Microsoft Azure SQL database for remote tables or data flows certain preparations have to be made.



<a name="loio782bd8c0d71943a9a6febee5f1557c80__prereq_rt_MS_Azure_SQL_db"/>

## Remote Tables

Before you can use the connection for creating views and accessing data via remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the MssqlLogReaderAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   An administrator has downloadad and installed the required JDBC library in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/lib</code> folder before registering the adapter with SAP Datasphere.

-   To use Microsoft SQL Server trigger-based replication, the user entered in the connection credentials needs to have the required privileges and permissions. For more information, see [Required Permissions for SQL Server Trigger-Based Replication](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/2815e1a621f84bada5fa3447d5029eb6.html) in the *Installation and Configuration Guide* for *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality*




<a name="loio782bd8c0d71943a9a6febee5f1557c80__prereq_df_MS_Azure_SQL_db"/>

## Data Flows and Replication Flows

Before you can use the connection for data flows and replication flows, the following is required:

-   The outbound IP has been added to the source allowlist.

    For information on where a DW administrator can find the IP address, see [Finding SAP Datasphere IP addresses](finding-sap-datasphere-ip-addresses-0934f7e.md).


**Related Information**  


[Microsoft Azure SQL Database Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/46343fc1c4544fa9a075d97f84d39826.html "Use a Microsoft Azure SQL Database connection to access table data from a Microsoft Azure SQL database.") :arrow_upper_right:

