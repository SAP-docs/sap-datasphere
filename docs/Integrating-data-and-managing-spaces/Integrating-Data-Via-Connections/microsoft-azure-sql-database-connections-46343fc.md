<!-- loio46343fc1c4544fa9a075d97f84d39826 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Microsoft Azure SQL Database Connections

Use a *Microsoft Azure SQL Database* connection to access table data from a Microsoft Azure SQL database.



This topic contains the following sections:

-   -   [Supported Features](microsoft-azure-sql-database-connections-46343fc.md#loio46343fc1c4544fa9a075d97f84d39826__Azure_SQL_usage)
-   [Configuring Connection Properties](microsoft-azure-sql-database-connections-46343fc.md#loio46343fc1c4544fa9a075d97f84d39826__Azure_SQL_connection_properties)

For information about the required prerequisites, see [Prepare Connectivity to Microsoft Azure SQL Database](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/782bd8c0d71943a9a6febee5f1557c80.html "To be able to successfully validate and use a connection to Microsoft Azure SQL database for remote tables or data flows certain preparations have to be made.") :arrow_upper_right:.



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

