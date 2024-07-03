<!-- loiob645de78a8374c24871ab6169be40d35 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Generic SFTP Connections

Use a *Generic SFTP* connection to access files on a Secure File Transfer Protocol \(SFTP\) server. 



<a name="loiob645de78a8374c24871ab6169be40d35__SFTP_usage"/>

## Using the Connection

The connection type supports the data flow feature.

Supported file types:

-   JSON, JSONL

-   Parquet

-   ORC

-   CSV

-   XLS, XLSX




<a name="loiob645de78a8374c24871ab6169be40d35__section_nrb_hcc_x4b"/>

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

Select the category. Select *Cloud* if you want to connect to an SFTP server in the public cloud, or select *On-Premise* if you want to connect to an SFTP server in your local network. 

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

If you don’t know your host key, ask your administrator or use command line tools like ssh-keyscan to obtain the host key \(only through a trustable channel\). For more information, see [Prepare Connectivity for Generic SFTP](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/5454a8cfdb9845a9b6c772d63b8e92ec.html "To create a Generic SFTP connection, the host's public key is required. Additionally, to successfully validate and use a Generic SFTP connection to an on-premise SFTP server, Cloud Connector is required.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

*Root Path*

</td>
<td valign="top">

\[optional\] Enter the root path name for browsing objects. The value starts with the character slash. For example, `/My Folder/MySubfolder`. 

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

\[optional\] Set to *true* if your source is an on-premise source and you want to use the connection for data flows. The default is *false*. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

\[optional\] Select a location ID. 

> ### Note:  
> To select another location ID than the default location, *Connection.Read* privilege is required. The privilege is neither included in the *DW Integrator* nor in the *DW Space Administrator* role. If you need to select a location ID, ask your tenant administrator to either assign your user to a global role that is based on the *DW Administrator* role or to assign your user to a custom global role that includes the required *Connection.Read* privilege.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Virtual Destination* 

</td>
<td valign="top">

\[optional\] Select *Derive Virtual Host and Port from Connection Details* or *Enter Virtual Host and Port in Separate Fields*. 

If host and port entered in the connection details match the virtual host and port from the Cloud Connector configuration, you can select *Derive Virtual Host and Port from Connection Details* and don't need to enter the values manually.

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

Choose <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location.

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

*Data Flows* are enabled without the need to set any additional connection properties. If your source is an on-premise source, make sure you have maintained the properties in the *Cloud Connector* section.

