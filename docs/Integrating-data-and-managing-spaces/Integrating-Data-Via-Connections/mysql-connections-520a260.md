<!-- loio520a2601fd7a45f084e5ed1d30c6ebfa -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# MySQL Connections

Use the connection to connect to and access tables from a MySQL database.

This topic contains the following sections:

-   [Supported Features](mysql-connections-520a260.md#loio520a2601fd7a45f084e5ed1d30c6ebfa__MySQL_usage)
-   [Prerequisites](mysql-connections-520a260.md#loio520a2601fd7a45f084e5ed1d30c6ebfa__MySQL_prerequisites)
-   [Configuring Connection Properties](mysql-connections-520a260.md#loio520a2601fd7a45f084e5ed1d30c6ebfa__MySQL_connection_properties)



<a name="loio520a2601fd7a45f084e5ed1d30c6ebfa__MySQL_usage"/>

## Supported Features


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

You can use the connection to add source objects to a replication flow \(see [Select Source and Target Connections for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/10891192186c4920b08939a7b46adc79.html "Select the source connection you want to read data from and the target connection you want to replicate data to.") :arrow_upper_right:\). 

For more information, see [MySQL Sources for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/4fe921866ee44d6e8bb13d92f378d3a2.html "You can use MySQL connections as sources in replication flows to replicate data into supported targets. This feature uses the Connectivity Framework and supports the Initial Only load type.") :arrow_upper_right:.

</td>
</tr>
</table>



<a name="loio520a2601fd7a45f084e5ed1d30c6ebfa__MySQL_prerequisites"/>

## Prerequisites 

Before you can use the connection for replication flows, the following is required:

-   Supported source versions: MySQL 8.4.x
-   If your MySQL server is an on-premise server in your local network, Cloud Connector is required for the connection between MySQL and SAP Datasphere.

    When configuring Cloud Connector, ensure you create the system mapping with the following settings:

    -   *Back-end Type*: Non-SAP System
    -   *Protocol*: TCP
    -   *Internal Host*: host on which the MySQL database is running to which you want to connect
    -   *Port or Port Range*: port for the endpoint
    -   *Virtual Host*: should be the same as the internal host
    -   *Virtual Port*: should be the same as the internal port
    -   *Check Internal Host*: deselected

    For more information, see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:.

-   A user with an administrator role has uploaded the TLS server certificate. This is required regardless of the authentication type selected in the connection.

    For more information, see:

    -   [Manage Certificates](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/46f5467adc5242deb1f6b68083e72994.html "Upload certificates and select their purpose: Choose TLS Server to secure connections or X.509 Client (Open SQL) to enable X.509 client certificate-based authentication for Open SQL database users.") :arrow_upper_right:
    -   [Using Encrypted Connections](https://dev.mysql.com/doc/refman/8.4/en/encrypted-connections.html) in the *MySQL 8.4 Reference Manual*

    For more information, see [Manage Certificates](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/46f5467adc5242deb1f6b68083e72994.html "Upload certificates and select their purpose: Choose TLS Server to secure connections or X.509 Client (Open SQL) to enable X.509 client certificate-based authentication for Open SQL database users.") :arrow_upper_right:.

-   For information about assigning privileges and roles to a MySQL user, see [GRANT Statement](https://dev.mysql.com/doc/refman/8.4/en/grant.html) in the *MySQL 8.4 Reference Manual*.



<a name="loio520a2601fd7a45f084e5ed1d30c6ebfa__MySQL_connection_properties"/>

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

*Hostname*  

</td>
<td valign="top">

Enter the name of the host on which the MySQL database is running. 

</td>
</tr>
<tr>
<td valign="top">

*Port*  

</td>
<td valign="top">

Enter the database server port number. 

</td>
</tr>
<tr>
<td valign="top">

*Database*  

</td>
<td valign="top">

Enter the name of the MySQL database to which you want to connect to. 

</td>
</tr>
<tr>
<td valign="top">

*Validate Hostname in Certificate*  

</td>
<td valign="top">

\[optional\] To secure your connection, TLS is enabled by default. You can choose to verify that the hostname you are connecting to matches the hostname listed in the server's certificate. The default is *false*. 

</td>
</tr>
</table>



### Cloud Connector


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

*Use Cloud Connector* 

</td>
<td valign="top">

\[optional\] Set to *true* if your source is an on-premise source and you want to use the connection for replication flows. The default is *false*. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

\[optional\] Select a location ID. 

> ### Note:  
> To select another location ID than the default location, *Connection* privilege with *Read* permission is required.



</td>
</tr>
<tr>
<td valign="top">

*Virtual Host* 

</td>
<td valign="top">

Enter the virtual host that you defined during Cloud Connector configuration. 

</td>
</tr>
<tr>
<td valign="top">

*Virtual Port* 

</td>
<td valign="top">

Enter the virtual port that you defined during Cloud Connector configuration. 

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

Select the authentication type to use to connect to the MySQL database. 

Choose from the following:

-   *X.509 Client Certificate* \[default\]
-   *User Name And Password* for basic authentication



</td>
</tr>
</table>



### X.509 Client Certificate

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

Enter the user name identifying the MySQL account.

</td>
</tr>
<tr>
<td valign="top">

*Password*

</td>
<td valign="top">

\[optional\] Enter the password for the user name. 

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
> Encrypted keys are supported in PKCS\#8 format.



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



### User Name And Password

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

Enter the user name identifying the MySQL account. 

</td>
</tr>
<tr>
<td valign="top">

*Password*  

</td>
<td valign="top">

Enter the password. 

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

*Replication Flows* are enabled without the need to set any additional connection properties. If your source is an on-premise source, make sure you have maintained the properties in the *Cloud Connector* section. 

</td>
</tr>
</table>

