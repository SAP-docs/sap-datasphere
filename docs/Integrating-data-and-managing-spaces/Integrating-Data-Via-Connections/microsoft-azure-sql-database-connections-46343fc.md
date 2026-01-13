<!-- loio46343fc1c4544fa9a075d97f84d39826 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Microsoft Azure SQL Database Connections

Use a *Microsoft Azure SQL Database* connection to access table data from a Microsoft Azure SQL database.



This topic contains the following sections:

-   [Supported Features](microsoft-azure-sql-database-connections-46343fc.md#loio46343fc1c4544fa9a075d97f84d39826__Azure_SQL_usage)
-   [Prerequisites](microsoft-azure-sql-database-connections-46343fc.md#loio46343fc1c4544fa9a075d97f84d39826__Azure_SQL_prerequisites)
-   [Configuring Connection Properties](microsoft-azure-sql-database-connections-46343fc.md#loio46343fc1c4544fa9a075d97f84d39826__Azure_SQL_connection_properties)



<a name="loio46343fc1c4544fa9a075d97f84d39826__Azure_SQL_usage"/>

## Supported Features

> ### Note:  
> In file spaces, only replication flows are supported. Remote tables and data flows are not supported.


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Additional Information

</th>
</tr>
<tr>
<td valign="top">

Replication Flows

</td>
<td valign="top">

You can use the connection to add source objects to a replication flow.

</td>
</tr>
<tr>
<td valign="top">

Remote Tables

</td>
<td valign="top">

You can use remote tables imported from the connection either to access data directly live in the connected source \(federation\) or to copy the data into SAP Datasphere \(replication\).

For remote tables, real-time replication is supported. For information about any constraints, see [Replicate Data Changes in Real-Time](../Data-Integration-Monitor/replicate-data-changes-in-real-time-441d327.md).

</td>
</tr>
<tr>
<td valign="top">

Data Flows

</td>
<td valign="top">

You can use the connection to add source objects to a data flow.

</td>
</tr>
</table>

> ### Note:  
> The connection type supports replication with both remote tables via Data Provisioning Agent \(SAP HANA Smart Data Integration\) and replication flows. Generally, for replication scenarios, we recommend to use replication flows.



<a name="loio46343fc1c4544fa9a075d97f84d39826__Azure_SQL_prerequisites"/>

## Prerequisites



### Remote Tables

Before you can use the connection for remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the MssqlLogReaderAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f1a39d1a763e48c8872f45c110a5a4e2.html "Most connection types supporting remote tables use SAP HANA Smart Data Integration (SDI) and its Data Provisioning Agent. Before using the connection, the agent requires an appropriate setup.") :arrow_upper_right:.

-   An administrator has downloaded and installed the required JDBC library in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/lib</code> folder before registering the adapter with SAP Datasphere.

-   To use Microsoft SQL Server trigger-based replication, the user entered in the connection credentials needs to have the required privileges and permissions. For more information, see [Required Permissions for SQL Server Trigger-Based Replication](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/2815e1a621f84bada5fa3447d5029eb6.html) in the *Installation and Configuration Guide* for *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality*




### Replication Flows

Before you can use the connection for replication flows, the following is required:

-   The outbound IP has been added to the source allowlist.

    For information on where a DW administrator can find the IP address, see [Obtain SAP Datasphere IP addresses For Allowlisting in Remote Systems](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/0934f7ed9a534e638299f53ab60866ae.html "Remote systems may restrict access to their instances. The remote system often decides whether an external client, such as SAP Datasphere, can access it based on allowlisted IPs. You must add SAP Datasphere's IP address to the remote system's allowlist before SAP Datasphere attempts access, via connections, for example.") :arrow_upper_right:.

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
    
    `CREATE SEQUENCE`
    
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
    -- Create login / userCREATE USER <ds_rep_user> WITH PASSWORD =<Strong!Password>;-- Create dedicated schema owned by the replication userCREATE SCHEMA <ds_rep_user> AUTHORIZATION <ds_rep_user>;
    ```




### Data Flows

Before you can use the connection for data flows, the following is required:

-   The outbound IP has been added to the source allowlist.

    For information on where a DW administrator can find the IP address, see [Obtain SAP Datasphere IP addresses For Allowlisting in Remote Systems](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/0934f7ed9a534e638299f53ab60866ae.html "Remote systems may restrict access to their instances. The remote system often decides whether an external client, such as SAP Datasphere, can access it based on allowlisted IPs. You must add SAP Datasphere's IP address to the remote system's allowlist before SAP Datasphere attempts access, via connections, for example.") :arrow_upper_right:.




<a name="loio46343fc1c4544fa9a075d97f84d39826__Azure_SQL_connection_properties"/>

## Configuring Connection Properties



### Connection Details


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Server Name* 

</td>
<td valign="top">

Enter the host name of the Azure server. 

</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Enter the port number of the Azure server. The default is `1433`. 

</td>
</tr>
<tr>
<td valign="top">

*Database Name* 

</td>
<td valign="top">

Enter the name of the database to which you want to connect. 

</td>
</tr>
</table>



### Security


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Host Name in Server Certificate* 

</td>
<td valign="top">

Enter `*.database.windows.net` .

</td>
</tr>
</table>



### Authentication


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the authentication type to use to connect to the Microsoft Azure SQL database. 

You can select:

-   *X.509 Client Certificate* \(default value\)

    > ### Note:  
    > This authentication type uses the ActiveDirectoryServicePrincipalCertificate authentication method. It supports only replication flows.

-   *User Name And Password* for basic authentication



</td>
</tr>
</table>



### Credentials \(X.509 Client Certificate\)

If *Authentication Type* = *X.509 Client Certificate*:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*User Name*

</td>
<td valign="top">

Enter the Azure Active Directory application \(client\) ID.

</td>
</tr>
<tr>
<td valign="top">

*Certificate*

</td>
<td valign="top">

To upload the certificate or certificate chain that is used to authenticate to the remote system, click <span class="SAP-icons-V5"></span> \(Browse\) and select the file.

> ### Note:  
> The file must be in Privacy-enhanced Mail \(PEM\) format. Supported filename extensions are .pem, .crt, or .txt\).



</td>
</tr>
<tr>
<td valign="top">

*Private Key*

</td>
<td valign="top">

To upload the private key, click <span class="SAP-icons-V5"></span> \(Browse\) and select the file.

> ### Note:  
> The file must be in Privacy-enhanced Mail \(PEM\) format. Supported filename extensions are .pem, .crt, .key, or .txt\).

> ### Note:  
> Unencrypted keys are supported in PKCS\#8 and PKCS\#1 formats \(only RSA key type is supported\). Encrypted keys are supported in PKCS\#1 format with RSA key type.



</td>
</tr>
<tr>
<td valign="top">

*Private Key Password*

</td>
<td valign="top">

\[optional\] If the private key is encrypted, enter the password required for decryption.

</td>
</tr>
</table>



### Credentials \(User Name and Password\)

If *Authentication Type* = *User Name And Password*:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*User Name* 

</td>
<td valign="top">

Enter the name of the Azure user that has privileges to connect to the database. 

</td>
</tr>
<tr>
<td valign="top">

*Password* 

</td>
<td valign="top">

Enter the password of the Azure user. 

</td>
</tr>
</table>



### Features


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
<tr>
<td valign="top">

*Remote Tables*

</td>
<td valign="top">

To enable *Remote Tables*, select a Data Provisioning Agent.

> ### Note:  
> In file spaces or when using authentication with X.509 client certificates, only replication flows are supported. Remote tables are not supported.



</td>
</tr>
<tr>
<td valign="top">

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties.

> ### Note:  
> In file spaces or when using authentication with X.509 client certificates, only replication flows are supported. Data flows are not supported.



</td>
</tr>
</table>

