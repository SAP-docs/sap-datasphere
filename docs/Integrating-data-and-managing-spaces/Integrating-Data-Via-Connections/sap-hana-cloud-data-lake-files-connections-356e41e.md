<!-- loio356e41e880e54255891b702d2afefeb3 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP HANA Cloud, Data Lake Files Connections

Use an *SAP HANA Cloud, Data Lake Files* connection to access data from the Files component of a standalone SAP HANA Cloud, data lake.



This topic contains the following sections:

-   [Context](sap-hana-cloud-data-lake-files-connections-356e41e.md#loio356e41e880e54255891b702d2afefeb3__context)
-   [Supported Features](sap-hana-cloud-data-lake-files-connections-356e41e.md#loio356e41e880e54255891b702d2afefeb3__HDLDB_usage)
-   [Configuring Connection Properties](sap-hana-cloud-data-lake-files-connections-356e41e.md#loio356e41e880e54255891b702d2afefeb3__connection_properties)



<a name="loio356e41e880e54255891b702d2afefeb3__context"/>

## Context

Standalone SAP HANA Cloud, data lake is a standalone component in the SAP Business Technology Platform Cockpit. It is composed of the default data lake Files component and the data lake Relational Engine component, and it is not integrated with SAP HANA database. For more information, see [What is SAP HANA Cloud, Data Lake](https://help.sap.com/docs/SAP_HANA_DATA_LAKE/a896c6a184f21015b5bcf4c7a967df07/228c19ac890046ecbe8e38a540c0cb6b.html) in the *SAP HANA Cloud, Data Lake* documentation.

> ### Note:  
> -   With connection type *SAP HANA Cloud, Data Lake Files* you cannot connect to the SAP HANA Cloud, data lake instance that is available with SAP Datasphere. To connect to this instance, use your Open SQL schema in the space which you have selected to access the data lake.
> 
>     For more information, see [Integrating Data to and From SAP HANA Cloud Data Lake](../Integrating-Data-to-and-From-HANA-Cloud/integrating-data-to-and-from-sap-hana-cloud-data-lake-e84545b.md).
> 
> -   SAP HANA Cloud, data lake Files connections are secure by default. They are encrypted without the need of configuring any TLS settings. Also, uploading server certificates isn't required.
> 
> -   To allow SAP Datasphere to access SAP HANA Cloud, data lake Files storage, it might be required to add the SAP Datasphere outbound IP address and HANA IP addresses to the allowed IP addresses for the data lake instance in SAP HANA Cloud Central.
> 
>     For more information, see:
> 
>     -   [Data Lake Connections](https://help.sap.com/docs/HANA_CLOUD/9ae9104a46f74a6583ce5182e7fb20cb/7e8ca90a9b4940d2930c36e92fbf6ba7.html) in the *SAP HANA Cloud* documentation
> 
>     -   [Finding SAP Datasphere IP addresses](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/0934f7ed9a534e638299f53ab60866ae.html "Find externally facing IP addresses and IDs that must be added to allowlists in particular remote applications before you can use connections to these remote applications.") :arrow_upper_right:



<a name="loio356e41e880e54255891b702d2afefeb3__HDLDB_usage"/>

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
<tr>
<td valign="top">

Replication Flows

</td>
<td valign="top">

You can use the connection to add source and target objects to a replication flow.

For more information, see:

-   [Using a Cloud Storage Provider As the Source](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/4d481a2c620f4b52ba65b360299d7719.html "If you use a cloud storage provider as the source for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:

-   [Using a Cloud Storage Provider As the Target](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/43d93a27150a4a218e3df14e3abdf456.html "If you use a cloud storage provider as the target for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:




</td>
</tr>
</table>



<a name="loio356e41e880e54255891b702d2afefeb3__connection_properties"/>

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

*Host* 

</td>
<td valign="top">

Enter the host name for SAP HANA Cloud, data lake Files. 

</td>
</tr>
<tr>
<td valign="top">

*Root Path* 

</td>
<td valign="top">

\[optional\] Enter a root path for browsing files. The value starts with the character slash. For example, `/My Folder/MySubfolder`. 

If you have specified the root path, then any path used with this connection is prefixed with the root path.

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

*Keystore File* 

</td>
<td valign="top">

Enter the Base64-encoded value of the client keystore file. The supported format is PCKS\#12 \(P12 and PFX files\). 

You can also choose <span class="SAP-icons-V5"></span> Browse and select the file from your download location.

</td>
</tr>
<tr>
<td valign="top">

*Keystore Password* 

</td>
<td valign="top">

Enter the client keystore password. 

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
<tr>
<td valign="top">

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
</table>

