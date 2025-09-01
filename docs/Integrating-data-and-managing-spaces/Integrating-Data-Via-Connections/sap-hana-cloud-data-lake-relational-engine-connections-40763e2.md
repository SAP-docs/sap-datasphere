<!-- loio40763e2e3e33440db0c37f6bcbe650f0 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP HANA Cloud, Data Lake Relational Engine Connections

Use an *SAP HANA Cloud, Data Lake Relational Engine* connection to access table data from the Relational Engine component of a standalone SAP HANA Cloud, data lake.

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

Standalone SAP HANA Cloud, data lake is a standalone component in the SAP Business Technology Platform Cockpit. It is composed of the default data lake Files component and the data lake Relational Engine component, and it is not integrated with SAP HANA database. For more information, see [What is SAP HANA Cloud, Data Lake](https://help.sap.com/docs/SAP_HANA_DATA_LAKE/a896c6a184f21015b5bcf4c7a967df07/228c19ac890046ecbe8e38a540c0cb6b.html) in the *SAP HANA Cloud, Data Lake* documentation.



<a name="loio40763e2e3e33440db0c37f6bcbe650f0__HDLDB_usage"/>

## Using the Connection

The connection type supports the remote table as well as the data flow feature.

Supported data access methods for remote tables:

-   Remote
-   Replication \(snapshot\)

> ### Note:  
> -   With connection type *SAP HANA Cloud, Data Lake Relational Engine* you cannot connect to the SAP HANA Cloud, data lake instance that is available with SAP Datasphere. To connect to this instance, use your Open SQL schema in the space which you have selected to access the data lake.
> 
>     For more information, see [Integrating Data to and From SAP HANA Cloud Data Lake](../Integrating-Data-to-and-From-HANA-Cloud/integrating-data-to-and-from-sap-hana-cloud-data-lake-e84545b.md).
> 
> -   SAP HANA Cloud, data lake Relational Engine connections are secure by default. They are encrypted without the need of configuring any TLS settings. Also, uploading server certificates isn't required.
> 
> -   To allow SAP Datasphere to access SAP HANA Cloud, data lake Relational Engine, it might be required to add the SAP Datasphere outbound IP address and HANA IP addresses to the allowed IP addresses for the data lake instance in SAP HANA Cloud Central.
> 
>     For more information, see:
> 
>     -   [Data Lake Connections](https://help.sap.com/docs/HANA_CLOUD/9ae9104a46f74a6583ce5182e7fb20cb/7e8ca90a9b4940d2930c36e92fbf6ba7.html) in the *SAP HANA Cloud* documentation
> 
>     -   [Finding SAP Datasphere IP addresses](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/0934f7ed9a534e638299f53ab60866ae.html "Find externally facing IP addresses and IDs that must be added to allowlists in particular remote applications before you can use connections to these remote applications.") :arrow_upper_right:



<a name="loio40763e2e3e33440db0c37f6bcbe650f0__section_nrb_hcc_x4b"/>

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

Enter the host of the SAP HANA Cloud, data lake Relational Engine server. 

</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Enter the port number. The default port is `443`. 

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

Select the authentication type to use to connect to the SAP HANA Cloud, data lake Relational Engine. 

You can select:

-   *X.509 Client Certificate* \(default value\)
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

Enter the name of the SAP HANA Cloud, data lake Relational Engine user.

> ### Note:  
> This user needs to have corresponding privileges to access the tables or views in SAP HANA Cloud, data lake Relational Engine that you want to use in SAP Datasphere. For more information, see [SAP HANA Cloud, Data Lake User Management for Data Lake IQ](https://help.sap.com/viewer/745778e524f74bb4af87460cca5e62c4/latest/en-US) in the *SAP HANA Cloud, Data Lake* documentation.



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

*Remote Tables* are enabled without the need to set any additional connection properties.

*Data Flows* are enabled without the need to set any additional connection properties.

