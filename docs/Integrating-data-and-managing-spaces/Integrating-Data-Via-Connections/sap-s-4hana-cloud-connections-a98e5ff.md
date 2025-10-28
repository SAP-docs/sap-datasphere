<!-- loioa98e5ffdf47c44d9a845dca01a18bd82 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP S/4HANA Cloud Connections

Use an *SAP S/4HANA Cloud* connection to access or import extraction-enabled ABAP Core Data Services views \(ABAP CDS views\) from SAP S/4HANA Cloud.



This topic contains the following sections:

-   [Supported Features](sap-s-4hana-cloud-connections-a98e5ff.md#loioa98e5ffdf47c44d9a845dca01a18bd82__S4_Cloud_usage)
-   [Configuring Connection Properties](sap-s-4hana-cloud-connections-a98e5ff.md#loioa98e5ffdf47c44d9a845dca01a18bd82__connection_properties)

For information about the required prerequisites in the connected systems and SAP Datasphere, see [Prepare Connectivity to SAP S/4HANA Cloud](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/abb159e027184c98a54fc1b2a88dd3f5.html "To be able to successfully validate and use a connection to SAP S/4HANA Cloud, certain preparations have to be made.") :arrow_upper_right:.



<a name="loioa98e5ffdf47c44d9a845dca01a18bd82__S4_Cloud_usage"/>

## Supported Features

> ### Note:  
> In file spaces, only replication flows are supported. Remote tables, data flows, and model import are not supported.


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

You can access the following data:

-   for federation: standard and custom CDS view entities that are exposed using the ABAP SQL service from SAP S/4HANA Cloud \(**recommended for federation scenarios**\)

    For more information, see [Using ABAP SQL Services for Accessing Data from SAP S/4HANA Cloud](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/ef2b2238154f4cd78a08df360447c1d5.html "The ABAP SQL service provides SQL-level access to published CDS view entities for SAP Datasphere. You can use the service to replicate data with replication flows or to federate data with remote tables.") :arrow_upper_right:.

    > ### Note:  
    > On the *Sources* tab of the remote-table-related Data Builder editors in SAP Datasphere, the service binding name from the *SQL\_SCHEMA* authorization field is visible as \(virtual\) schema.

-   for federation and replication: ABAP CDS Views exposed as OData services for data extraction. Data is accessed via Cloud Data Integration \(**legacy**\)

    > ### Note:  
    > This legacy option is still supported, however we recommend using the ABAP SQL service for federation \(if available\) and replication flows for replication.

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

You can access the following data:

-   extraction-enabled ABAP CDS views that are C1-released, that is views with annotation `@Analytics.dataextraction.enabled: true` and that are available in the connected system \(access via ABAP Pipeline Engine\)

    For more information, see:

    -   [Data Integration](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/c3a5da91691d4ebd89748d9f40af7a4c.html) in the *SAP S/4HANA Cloud* documentation

    -   [CDS Views Enabled for Data Extraction](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/870d66c6bfc44d6c9f128c888f0c7957.html) in the *SAP S/4HANA Cloud* documentation



> ### Note:  
> -   Data flows currently support one-time loading of data \(also known as initial load\) only.
> 
> -   The data preview in the data flow editor of the *Data Builder* is **only** available if the version of the connected system is SAP S/4HANA Cloud 2302 or higher.



</td>
</tr>
<tr>
<td valign="top">

Replication Flows

</td>
<td valign="top">

You can use the connection to add source objects to a replication flow. \(**recommended for replication scenarios**\)

For information about minimum system versions and other prerequisites, see [SAP S/4HANA and Other ABAP Sources for Replication Flows](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/3f70579c92434f4f88471bba2bd70893.html "Before replicating data from your SAP S/4HANA or other ABAP source, you must ensure that all the appropriate release and security notes for your source system version are applied.") :arrow_upper_right:.

You can replicate the following data:

-   standard and custom CDS view entities that are exposed using the ABAP SQL service from SAP S/4HANA Cloud

    For more information, see [Data Consumption Using SAP Datasphere](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/ec312dd3e39f401b84681c53adc08ad8.html).

    > ### Note:  
    > When adding source objects in replication flows, you can find the CDS view entities in the SQL\_SERVICE container.

-   extraction-enabled ABAP CDS views that are C1-released, that is views with annotation `@Analytics.dataextraction.enabled: true` and that are available in the connected system \(access via ABAP Pipeline Engine\)

    For more information, see:

    -   [Data Integration](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/c3a5da91691d4ebd89748d9f40af7a4c.html) in the *SAP S/4HANA Cloud* documentation

    -   [CDS Views Enabled for Data Extraction](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/870d66c6bfc44d6c9f128c888f0c7957.html) in the *SAP S/4HANA Cloud* documentation


    > ### Note:  
    > When adding source objects in replication flows, you can find the CDS views in the CDS\_EXTRACTION container.




</td>
</tr>
</table>

> ### Note:  
> The connection type supports replication with both remote tables via Data Provisioning Agent \(SAP HANA Smart Data Integration\) and replication flows.
> 
> Regardless of whether you use the same connection or two separate connections, for replicating data from a dedicated source object in the source we strongly recommend to only use remote tables or replication flows and not both. Generally, for replication scenarios, we recommend to use replication flows.



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

Enter the name of the **API**-URL from the communication arrangements that you set up in SAP S/4HANA Cloud \(without https://\), for example `myXXXXX-api.s4hana.ondemand.com` or `myXXXXX-api.s4hana.cloud.sap`.

For more information about the required communication arrangements, see [Prepare Connectivity to SAP S/4HANA Cloud](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/abb159e027184c98a54fc1b2a88dd3f5.html "To be able to successfully validate and use a connection to SAP S/4HANA Cloud, certain preparations have to be made.") :arrow_upper_right:.

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



### Remote Tables

> ### Note:  
> In file spaces, only replication flows are supported. Remote tables are not supported.


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

*Data Provisioning Option*

</td>
<td valign="top">

Select the middleware to use when connecting to and accessing SAP S/4HANA Cloud: 

-   *None* \(default\): if you don't want to use remote tables.

-   *Data Provisioning Agent*: if you want to use federation and replication via SAP HANA smart data integration CloudDataIntegrationAdapter \(**legacy**\), or if you want to use model import.

    > ### Note:  
    > This legacy option is still supported, however we recommend using the ABAP SQL service for federation \(if available\) and replication flows for replication.

-   *Direct*: if you want to federate data from the source objects of the connection and access them remotely in the source system using the ABAP SQL service \(**recommended for federation scenarios**\).

    > ### Note:  
    > When using the *Direct* option, you can't use the same connection for model import.




</td>
</tr>
<tr>
<td valign="top">

\[if *Data Provisioning Option* = *Data Provisioning Agent* or *Direct*\] *Data Access* 

</td>
<td valign="top">

\[read-only\] Displays how data from source objects can be accessed: 

-   *Remote and Replication*: if you selected data provisioning option *Data Provisioning Agent* \(using the SAP HANA smart data integration CloudDataIntegrationAdapter\).

-   *Remote Only*: if you selected data provisioning option *Direct* \(using the ABAP SQL service\).




</td>
</tr>
<tr>
<td valign="top">

\[if *Data Provisioning Option* = *Data Provisioning Agent*\] *Data Provisioning Agent* 

</td>
<td valign="top">

Select an agent from the list of agents configured for SAP Datasphere.

</td>
</tr>
<tr>
<td valign="top">

\[if *Data Provisioning Option* = *Direct*\] *Type Map* 

</td>
<td valign="top">

Specify how ABAP data types are mapped to SAP HANA data types: 

-   *native*: no conversion of ABAP data types

-   *semantic*: conversion of the ABAP data types to an ABAP-independent data format

-   *semanticDatsTimsAsWchar*: like *semantic*, except that the ABAP types DATS and TIMS are mapped to the ODBC type SQL\_WCHAR to allow for lossless conversion of date literals and time literals




</td>
</tr>
</table>



### Replication Flows


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

*Fast Serialization*

</td>
<td valign="top">

Turn on RFC fast serialization to help improve replication flow performance by avoiding unnecessary, costly conversions in ABAP. This can be useful particularly in cases of large data volumes. The default is *On*.

> ### Note:  
> -   Fast serialization has no impacts on data flows.
> 
> -   For information about the prerequisites for using fast serialization in SAP Datasphere, see [Prepare Connectivity to SAP S/4HANA Cloud](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/abb159e027184c98a54fc1b2a88dd3f5.html "To be able to successfully validate and use a connection to SAP S/4HANA Cloud, certain preparations have to be made.") :arrow_upper_right:.
> 
>     Use the connection validation to check if the prerequisites in the source system for using fast serialization are met.



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

To enable*Remote Tables*, complete the connection properties in the *Remote Tables* section. 

> ### Note:  
> For federation scenarios, we recommend using the ABAP SQL service \(data provisioning option *Direct*\).

> ### Note:  
> In file spaces, only replication flows are supported. Remote tables are not supported.



</td>
</tr>
<tr>
<td valign="top">

*Model Import*

</td>
<td valign="top">

To enable *Model Import*, in the *Remote Tables* section select data provisioning option *Data Provisioning Agent* and then select an agent.

> ### Note:  
> In file spaces, only replication flows are supported. Model import is not supported.



</td>
</tr>
<tr>
<td valign="top">

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties.

> ### Note:  
> In file spaces, only replication flows are supported. Data flows are not supported.



</td>
</tr>
<tr>
<td valign="top">

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties. 

> ### Note:  
> For replication scenarios, we recommend using replication flows.



</td>
</tr>
</table>

