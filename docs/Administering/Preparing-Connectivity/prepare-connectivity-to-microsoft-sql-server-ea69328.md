<!-- loioea69328fb328449ab7b04d2b142592f8 -->

# Prepare Connectivity to Microsoft SQL Server

To be able to successfully validate and use a connection to a Microsoft SQL Server, certain preparations have to be made.



<a name="loioea69328fb328449ab7b04d2b142592f8__prereq_rt_MSSQL"/>

## Remote Tables

Before you can use the connection for remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the MssqlLogReaderAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   An administrator has downloaded and installed the required JDBC library in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/lib</code> folder before registering the adapter with SAP Datasphere.

-   [Required Permissions for SQL Server Trigger-Based Replication](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/2815e1a621f84bada5fa3447d5029eb6.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*




<a name="loioea69328fb328449ab7b04d2b142592f8__prereq_df_MSSQL"/>

## Replication Flows

Before you can use the connection for replication flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

    > ### Note:  
    > Cloud Connector is not required if your Microsoft SQL Server database is available on the public internet.

-   The required driver is pre-bundled and doesn't need to be uploaded by an administrator.

-   To replicate from a Microsoft SQL Server \(MSSQL\) or Azure SQL source system, the database user must have the following privileges:


    <table>
    <tr>
    <th valign="top">

    Privilege
    
    </th>
    <th valign="top">

    Object
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Required for initial load
    
    </th>
    <th valign="top">

    Required for delta load
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `public` role
    
    </td>
    <td valign="top">
    
    Database
    
    </td>
    <td valign="top">
    
    Metadata access
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `VIEW DATABASE PERFORMANCE STATE`
    
    </td>
    <td valign="top">
    
    Database
    
    </td>
    <td valign="top">
    
    Metadata access

    > ### Note:  
    > For versions earlier than Microsoft SQL Server 2022, the `VIEW DATABASE STATE` privilege is required instead.


    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `SELECT`
    
    </td>
    <td valign="top">
    
    Source table
    
    </td>
    <td valign="top">
    
    Read data from source tables.
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `ALTER`
    
    </td>
    <td valign="top">
    
    Source table
    
    </td>
    <td valign="top">
    
    Create triggers. Drop triggers for clean up.

    > ### Note:  
    > Triggers can only be created under the source schema. Other replication objects are created under the user schema.


    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `CREATE TABLE`
    
    </td>
    <td valign="top">
    
    Database
    
    </td>
    <td valign="top">
    
    Create shadow tables.
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `CREATE PROCEDURE`
    
    </td>
    <td valign="top">
    
    Database
    
    </td>
    <td valign="top">
    
    Create stored procedures.
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `CREATE SEQUENCE`
    
    </td>
    <td valign="top">
    
    Database
    
    </td>
    <td valign="top">
    
    Create sequences.
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `ALTER`
    
    </td>
    <td valign="top">
    
    User schema
    
    </td>
    <td valign="top">
    
    Create replication objects in user schema. Drop replication objects for clean up.
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > This table lists the minimum per-table privileges required for initial and delta loads. Equivalent schema-level privileges \(for example, `SELECT`, `ALTER` on the source schema\) also work because they cover all tables in the schema. Database roles like `db_datareader`, which grant `SELECT` on all tables in the database can also work, depending on your security requirements.

    To enable delta loading, a database schema with the same name as the database user must exist, replication objects \(shadow tables, procedures, sequences\) are created under this user schema. If it does not exist, create it. The database user needs the required privileges on this schema to create and manage replication objects. You can create the necessary user and schema with the following commands:

    ```
    -- Create login / user
    CREATE USER <ds_rep_user> WITH PASSWORD =<Strong!Password>;
    
    -- Create dedicated schema owned by the replication user
    CREATE SCHEMA <ds_rep_user> AUTHORIZATION <ds_rep_user>;
    ```




<a name="loioea69328fb328449ab7b04d2b142592f8__section_wl5_xzv_3hc"/>

## Data Flows

Before you can use the connection for data flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

    > ### Note:  
    > Cloud Connector is not required if your Microsoft SQL Server database is available on the public internet.

-   The required driver is pre-bundled and doesn't need to be uploaded by an administrator.


**Related Information**  


[Microsoft SQL Server Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a13c8abb328f45be891599c9cc76fb91.html "Use a Microsoft SQL Server connection to access data from a Microsoft SQL Server database (on-premise).") :arrow_upper_right:

