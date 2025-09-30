<!-- loiob645de78a8374c24871ab6169be40d35 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Generic SFTP Connections

Use a *Generic SFTP* connection to connect to and access files on a Secure File Transfer Protocol \(SFTP\) server. 



This topic contains the following sections:

-   [Supported Features](generic-sftp-connections-b645de7.md#loiob645de78a8374c24871ab6169be40d35__SFTP_usage)
-   [Configuring Connection Properties](generic-sftp-connections-b645de7.md#loiob645de78a8374c24871ab6169be40d35__connection_properties)

For information about the required prerequisites, see [Prepare Connectivity for Generic SFTP](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/5454a8cfdb9845a9b6c772d63b8e92ec.html "To connect to the SFTP server, a public host key is required to verify the server's identity. Additionally, to successfully validate and use a Generic SFTP connection to an on-premise SFTP server, Cloud Connector is required.") :arrow_upper_right:.



<a name="loiob645de78a8374c24871ab6169be40d35__SFTP_usage"/>

## Supported Features

> ### Note:  
> In file spaces, only replication flows are supported. Data flows are not supported.


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

Data Flows

</td>
<td valign="top">

You can use the connection to add source objects to a data flow. Supported file formats are JSON, JSONL, CSV, XLS, XLSX, ORC, and PARQUET.

For more information, see [Add a Source to a Data Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/7b50e8e304244ced9ff1e62e2f2fe919.html "Add a source to read data from. You can add multiple sources and combine them together using join or union operators.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

Replication Flows

</td>
<td valign="top">

You can use the connection to add source and target objects to a replication flow. Supported file formats for target objects are are CSV, JSON, JSONL, and PARQUET. The supported file format for source objects is CSV.

For more information, see:

-   [Secure File Transfer Protocol (SFTP) as Targets for Your Replication Flows](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/5a14eb1709a24a35821d1618285d021d.html "You want to replicate data using a secure file transfer protocol (SFTP) for secure and reliable file transfers.") :arrow_upper_right:
-   [Secure File Transfer Protocol (SFTP) Sources for Replication Flows](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/a832ef4cee9d4d3aa1210869743b6173.html "You want to replicate data from a file storage using a secure file transfer protocol (SFTP) connection for secure and reliable file transfers to a supported target.") :arrow_upper_right:

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Premium Outbound Integration](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/4e9c6acb5d6a43fa9a6471837399e71c.html "To use a non-SAP target in a replication flow, you need premium outbound integration.") :arrow_upper_right: and [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).



</td>
</tr>
</table>



<a name="loiob645de78a8374c24871ab6169be40d35__connection_properties"/>

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

*Category* 

</td>
<td valign="top">

Select *Cloud* if you want to connect to an SFTP server in the public cloud, or select *On-Premise* if you want to connect to an SFTP server in your local network. 

</td>
</tr>
<tr>
<td valign="top">

*Host* 

</td>
<td valign="top">

Enter the host name of the SFTP server. 

</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Enter the port number of the SFTP server. 

</td>
</tr>
<tr>
<td valign="top">

*Host Key* 

</td>
<td valign="top">

Enter the public SSH host key \(public key of the SFTP server, not the key fingerprint\). 

Choose <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location.

If you don’t know your host key, ask your administrator or use command line tools like ssh-keyscan to obtain the host key \(only through a trustable channel\). For more information, see [Prepare Connectivity for Generic SFTP](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/5454a8cfdb9845a9b6c772d63b8e92ec.html "To connect to the SFTP server, a public host key is required to verify the server's identity. Additionally, to successfully validate and use a Generic SFTP connection to an on-premise SFTP server, Cloud Connector is required.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

*Root Path*

</td>
<td valign="top">

\[optional\] Enter the root path name for browsing objects. The value starts with the character slash. For example, **`/My Folder/MySubfolder`**. 

If you have entered root path, then any path used with this connection is prefixed with the root path.

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

\[optional\] Set to *true* if your source is an on-premise source and you want to use the connection for data flows and replication flows. The default is *false*. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

\[optional\] Select a location ID. 

> ### Note:  
> To select another location ID than the default location, *Connection.Read* privilege is required. The privilege is neither included in the *DW Integrator* nor in the *DW Space Administrator* role. If you need to select a location ID, ask your tenant administrator to either assign your user to a global role that is based on the *DW Administrator* role or to assign your user to a custom global role \(with license type SAP Datasphere\) that includes the required *Connection.Read* privilege.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Virtual Destination* 

</td>
<td valign="top">

\[optional\] Select how you want to specify the virtual destination. 

You can select:

-   *Derive Virtual Host and Port from Connection Details* \(default\)

    If host and port entered in the connection details match the virtual host and port from the Cloud Connector configuration, you don't need to enter the values manually.

-   *Enter Virtual Host and Port in Separate Fields*




</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Host* 

</td>
<td valign="top">

Enter the virtual host that you defined during Cloud Connector configuration. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Port* 

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

Select the authentication type to be used. 

You can select:

-   *SSH* for using the Secure Shell \(SSH\) protocol \(default value\)
-   *User Name And Password* for basic authentication



</td>
</tr>
</table>



### Credentials \(SSH\)

If *Authentication Type* = *SSH*:


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

Enter the user who is accessing the SFTP server. 

</td>
</tr>
<tr>
<td valign="top">

*Private Key*  

</td>
<td valign="top">

Enter the user SSH private key used for SSH key authentication. The server must know the user SSH public key. 

Choose <span class="SAP-icons-V5"></span> \(Browse\) and select the file.

</td>
</tr>
<tr>
<td valign="top">

*Passphrase*  

</td>
<td valign="top">

Enter the passphrase needed to decrypt the private key in SSH key authentication. 

</td>
</tr>
</table>



### Credentials \(User Name and Password\)

If *Authentication Type* = *User Name and Password*:


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

Enter the user accessing the SFTP server. 

</td>
</tr>
<tr>
<td valign="top">

*Password*  

</td>
<td valign="top">

Enter the user's password used for authentication. 

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

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties. If your source is an on-premise source, make sure you have maintained the properties in the *Cloud Connector* section.

> ### Note:  
> In file spaces, only replication flows are supported. Data flows are not supported.



</td>
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

