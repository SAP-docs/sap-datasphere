<!-- loiof9c33566c4eb412d9d36a2f044bb5126 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Hadoop Distributed File System Connections

Use the connection to access objects from an Hadoop Distributed File System \(HDFS\) server. 

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

This topic contains the following sections:

-   [Supported Features](hadoop-distributed-file-system-connections-f9c3356.md#loiof9c33566c4eb412d9d36a2f044bb5126__HDFS_usage)
-   [Configuring Connection Properties](hadoop-distributed-file-system-connections-f9c3356.md#loiof9c33566c4eb412d9d36a2f044bb5126__HDFS_connection_properties)



<a name="loiof9c33566c4eb412d9d36a2f044bb5126__HDFS_usage"/>

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

Data Flows

</td>
<td valign="top">

You can use the connection to add source objects to a data flow.

</td>
</tr>
</table>



<a name="loiof9c33566c4eb412d9d36a2f044bb5126__HDFS_connection_properties"/>

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

*Endpoint*  

</td>
<td valign="top">

Select *RPC* or *WEBHDFS* 

> ### Note:  
> Along with Remote Procedure Call \(RPC\), HDFS can also extend connections with WebHDFS.
> 
> If you select *RPC*, make sure that both the NameNode and the DataNodes are exposed and can be connected from SAP Datasphere. For more information, see [Obtain SAP Datasphere IP addresses For Allowlisting in Remote Systems](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/0934f7ed9a534e638299f53ab60866ae.html "Remote systems may restrict access to their instances. The remote system often decides whether an external client, such as SAP Datasphere, can access it based on allowlisted IPs. You must add SAP Datasphere's IP address to the remote system's allowlist before SAP Datasphere attempts access, via connections, for example.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

*Host*  

</td>
<td valign="top">

Enter the hostname or the IP address of the HDFS namenode. 

</td>
</tr>
<tr>
<td valign="top">

*Port*  

</td>
<td valign="top">

Enter the port of the HDFS namenode. If you do not provide any value, the default value for the selected protocol is used. 

</td>
</tr>
<tr>
<td valign="top">

*Root Path* 

</td>
<td valign="top">

\[optional\] Enter the root path name for browsing objects. The value starts with the character slash. For example, `/My Folder/MySubfolder`. 

If you have specified the root path, then any path used with this connection is prefixed with the root path.

</td>
</tr>
</table>



### Custom Parameters


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

*Use Custom Parameters*

</td>
<td valign="top">

Select *true* to use an HDFS custom parameter.

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Custom Parameters* = *true*\] *HDFS Configuration*  

</td>
<td valign="top">

Enter the HDFS custom parameter. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Custom Parameters* = *true*\] *Value*  

</td>
<td valign="top">

Enter a value. 

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

Select the authentication type that the application must use. 

To connect to HDFS the application supports *User Name And Password*, *Simple*, or *Kerberos* authentication mechanisms.

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

Enter the user name of the HDFS user. 

</td>
</tr>
<tr>
<td valign="top">

*Password*  

</td>
<td valign="top">

Enter the password of the HDFS user. 

</td>
</tr>
</table>



### Credentials \(Simple\)

If *Authentication Type* = *Simple*:


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

Enter the user name of the HDFS user. 

</td>
</tr>
</table>



### Credentials \(Kerberos\)

If *Authentication Type* = *Kerberos*:


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

Enter the user principal. 

</td>
</tr>
<tr>
<td valign="top">

*keytab*  

</td>
<td valign="top">

Enter the content of the keytab file of the user from the local system. 

Choose <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location.

</td>
</tr>
</table>



### Configuration

If *Authentication Type* = *Kerberos*:


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

*krb5.config*  

</td>
<td valign="top">

Enter the content of the krb5.conf configuration file from your local system. 

Choose <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location.

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

*Data Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
</table>

