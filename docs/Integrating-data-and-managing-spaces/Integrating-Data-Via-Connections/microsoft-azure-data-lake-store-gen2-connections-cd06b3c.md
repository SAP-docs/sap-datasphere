<!-- loiocd06b3c5ab5147c0905e3fa8abd13eb1 -->

# Microsoft Azure Data Lake Store Gen2 Connections

Use the connection to access objects in Microsoft Azure Data Lake Gen2 \(ADL Gen2\). 



<a name="loiocd06b3c5ab5147c0905e3fa8abd13eb1__ADL2_usage"/>

## Using the Connection

The connection type supports the data flow feature.



<a name="loiocd06b3c5ab5147c0905e3fa8abd13eb1__section_nrb_hcc_x4b"/>

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

 *Storage Account Name*  



</td>
<td valign="top">

 Enter the name of the Azure Data Lake Storage Gen2 used for authentication. 



</td>
</tr>
<tr>
<td valign="top">

 *Root Path*  



</td>
<td valign="top">

 \[optional\] Enter the root path name for browsing. It starts with a slash and the file system name. For example `/MyFileSystem/MyFolder`. The file system must be provided. Any path used with this connection will be prefixed with this root path. 



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

 Select the authentication type to be used: *Shared Key* \(default\) or *Shared Access Signature*. 

Shared key provides full access to your storage account while with shared access signature you can provide secure delegate access to the storage account resources.



</td>
</tr>
</table>



### Credentials \(Shared Access Signature\)

If *Authentication Type* = *Shared Access Signature*:


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

 *SAS Token*  



</td>
<td valign="top">

 Enter the shared access signature token \(SAS token\) used in shared access signature authentication. 



</td>
</tr>
</table>



### Credentials \(Shared Key\)

If *Authentication Type* = *Shared Key*:


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

 *Account Key*  



</td>
<td valign="top">

 Enter the account key used in the shared key authorization. 



</td>
</tr>
</table>



### Features

*Data Flows* are enabled without the need to set any additional connection properties.

