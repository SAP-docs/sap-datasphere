<!-- loioa98e5ffdf47c44d9a845dca01a18bd82 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP S/4HANA Cloud Connections

Use an *SAP S/4HANA Cloud* connection to access or import extraction-enabled ABAP Core Data Services views \(ABAP CDS views\) from SAP S/4HANA Cloud.



This topic contains the following sections:

-   [Supported Features](sap-s-4hana-cloud-connections-a98e5ff.md#loioa98e5ffdf47c44d9a845dca01a18bd82__S4_Cloud_usage)
-   [Configuring Connection Properties](sap-s-4hana-cloud-connections-a98e5ff.md#loioa98e5ffdf47c44d9a845dca01a18bd82__connection_properties)

For information about the required prerequisites, see [Prepare Connectivity to SAP S/4HANA Cloud](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/abb159e027184c98a54fc1b2a88dd3f5.html "To be able to successfully validate and use a connection to SAP S/4HANA Cloud, certain preparations have to be made.") :arrow_upper_right:.



<a name="loioa98e5ffdf47c44d9a845dca01a18bd82__S4_Cloud_usage"/>

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

Remote Tables

</td>
<td valign="top">

You can use remote tables imported from the connection either to access data directly live in the connected source \(federation\) or to copy the data into SAP Datasphere \(replication\).

For remote tables, real-time replication is supported. For information about any constraints, see [Replicate Data Changes in Real-Time](../Data-Integration-Monitor/replicate-data-changes-in-real-time-441d327.md).

</td>
</tr>
<tr>
<td valign="top">

Model Import

</td>
<td valign="top">

You can use the connection to import semantically-rich entities from SAP S/4HANA Cloud and all their sources and dependencies. For more information, see [Importing Entities with Semantics from SAP S/4HANA](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/845fedbd28574aa8b84239df848936f6.html "You can use the Import Entities wizard to load metadata from your SAP S/4HANA Cloud and SAP S/4HANA on-premise connections via semantically-rich objects. The wizard creates Business Builder and Data Builder entities (along with all the objects on which they depend) in SAP Datasphere.") :arrow_upper_right:. 

</td>
</tr>
<tr>
<td valign="top">

Data Flows

</td>
<td valign="top">

You can use the connection to add source objects to a data flow.

> ### Note:  
> The data preview in the data flow editor of the Data Builder is **not** available for SAP S/4HANA Cloud sources.



</td>
</tr>
<tr>
<td valign="top">

Replication Flows

</td>
<td valign="top">

You can use the connection to add source objects to a replication flow. 

</td>
</tr>
</table>

For more information about extracting ABAP CDS Views from SAP S/4HANA Cloud, see:

-   [Data Integration](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/c3a5da91691d4ebd89748d9f40af7a4c.html) in the *SAP S/4HANA Cloud* documentation

-   [CDS Views Enabled for Data Extraction](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/870d66c6bfc44d6c9f128c888f0c7957.html) in the *SAP S/4HANA Cloud* documentation


> ### Note:  
> The connection type supports replication with both remote tables via Data Provisioning Agent \(SAP HANA Smart Data Integration\) and replication flows.
> 
> Regardless of whether you use the same connection or two separate connections, for replicating data from a dedicated source object in the source we strongly recommend to only use remote tables or replication flows and not both.



<a name="loioa98e5ffdf47c44d9a845dca01a18bd82__connection_properties"/>

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

*Application Server*

</td>
<td valign="top">

Enter the name of the application server to which you want to connect.

</td>
</tr>
<tr>
<td valign="top">

*Client*

</td>
<td valign="top">

Enter the system client number.

</td>
</tr>
<tr>
<td valign="top">

*System ID*

</td>
<td valign="top">

Enter the system ID of the system to which you want to connect.

</td>
</tr>
<tr>
<td valign="top">

*Language*

</td>
<td valign="top">

Enter a two-digit ISO language code, EN for English or DE for German, for example. Object and field descriptions in the data flow editor of the Data Builder are then shown in the specified language. If you don't enter any language code, the application uses the default logon language of the SAP S/4HANA system.

</td>
</tr>
<tr>
<td valign="top">

*Port*

</td>
<td valign="top">

Enter the port number of the WebSocket RFC connection endpoint. The default port number is 443.

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

Select the authentication type to use to connect to SAP S/4HANA Cloud. 

You can select:

-   *X.509 Client Certificate* 
-   *User Name And Password* for basic authentication

The default is *X.509 Client Certificate*.

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

*X.509 Client Certificate*

</td>
<td valign="top">

To upload the certificate or certificate chain that is used to authenticate to the remote system, click <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location.

</td>
</tr>
<tr>
<td valign="top">

*X.509 Client Private Key*

</td>
<td valign="top">

To upload the private key, click <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location.

</td>
</tr>
<tr>
<td valign="top">

*X.509 Client Private Key Password*

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

Enter the user name that is used to connect to the SAP S/4HANA system.

</td>
</tr>
<tr>
<td valign="top">

*Password*

</td>
<td valign="top">

Enter the user password.

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

*Remote Tables*

</td>
<td valign="top">

To enable *Remote Tables*, select a Data Provisioning Agent. 

</td>
</tr>
<tr>
<td valign="top">

*Model Import*

</td>
<td valign="top">

To enable *Model Import*, select a Data Provisioning Agent. 

</td>
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

