<!-- loioaa04f9a3dd454b1b8761a963079887a3 -->

# Microsoft Azure Data Lake Store Gen1 Connections \(Deprecated\)

Use the connection to access objects in Microsoft Azure Data Lake Gen1 \(ADL Gen1\).



> ### Caution:  
> Microsoft Azure Data Lake Storage Gen1 will be retired on February 29, 2024 \(see [https://azure.microsoft.com/en-us/updates/action-required-switch-to-azure-data-lake-storage-gen2-by-29-february-2024/](https://azure.microsoft.com/en-us/updates/action-required-switch-to-azure-data-lake-storage-gen2-by-29-february-2024/)\). After this date, it might not be possible to access data with Gen1 connections. Therefore, the connection type *Microsoft Azure Data Lake Storage Gen1* is deprecated and may be removed in future releases.
> 
> After your Microsoft Azure Data Lake Storage Gen1 has been migrated to Microsoft Azure Data Lake Storage Gen2, recreate existing Gen1 connections with the Gen2 connection type and adapt your models and processes to the new connections.



<a name="loioaa04f9a3dd454b1b8761a963079887a3__ADL1_usage"/>

## Using the Connection

The connection type supports the data flow feature.



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

Enter the name of the Azure Data Lake Storage Gen1 account. 

</td>
</tr>
<tr>
<td valign="top">

*Tenant ID*  

</td>
<td valign="top">

Enter the ID of the Azure Data Lake Storage Gen1 tenant. 

</td>
</tr>
<tr>
<td valign="top">

*Root Path*  

</td>
<td valign="top">

\[optional\] Enter the root path name for browsing. It starts with a slash and the file system name. For example `/MyFileSystem/MyFolder`. The file system must be provided. 

</td>
</tr>
</table>



### Credentials


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

*Client ID*  

</td>
<td valign="top">

Enter the client ID. 

</td>
</tr>
<tr>
<td valign="top">

*Client Key*  

</td>
<td valign="top">

Enter the client key \(also referred to as client secret or authentication key\). 

</td>
</tr>
</table>



### Features

*Data Flows* are enabled without the need to set any additional connection properties.

