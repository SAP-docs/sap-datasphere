<!-- loiodf5a7c56ac21472c973f6fab341f3991 -->

# Microsoft Azure Blob Storage Connections

Use the connection to access objects in Microsoft Azure Blob Storage. 

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).



<a name="loiodf5a7c56ac21472c973f6fab341f3991__WASB_usage"/>

## Using the Connection

The connection type supports the data flow feature.



<a name="loiodf5a7c56ac21472c973f6fab341f3991__section_nrb_hcc_x4b"/>

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

*Protocol* 

</td>
<td valign="top">

Select the protocol \(wasb for unencrypted access or wasbs for TLS-encrypted access\). The default is wasbs. 

</td>
</tr>
<tr>
<td valign="top">

*Account Name* 

</td>
<td valign="top">

Enter the name of the Microsoft Azure storage account through which Microsoft Azure Blob Storage is provisioned. 

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
<tr>
<td valign="top">

*Endpoint Suffix* 

</td>
<td valign="top">

Displays the default value for the endpoint suffix which is "core.windows.net". You can override the default value according to the domain assigned to the endpoint of your blob service. 

</td>
</tr>
</table>



### Credentials \(Shared Key\)


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

Enter the storage account access key \(shared key authorization\). 

</td>
</tr>
</table>



### Features

*Data Flows* are enabled without the need to set any additional connection properties.

