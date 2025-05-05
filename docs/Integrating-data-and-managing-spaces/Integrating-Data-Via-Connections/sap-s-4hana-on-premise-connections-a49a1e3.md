<!-- loioa49a1e3cc50f4af89711d8306bdd8f26 -->

# SAP S/4HANA On-Premise Connections

Use an SAP S/4HANA On-Premise connection to access data from SAP S/4HANA on-premise systems.



This topic contains the following sections:

-   [Supported Features](sap-s-4hana-on-premise-connections-a49a1e3.md#loioa49a1e3cc50f4af89711d8306bdd8f26__S4_OP_usage)
-   [Configuring Connection Properties](sap-s-4hana-on-premise-connections-a49a1e3.md#loioa49a1e3cc50f4af89711d8306bdd8f26__connection_properties)

For information about the required prerequisites in the connected systems and SAP Datasphere, and about supported source system versions, see [Prepare Connectivity to SAP S/4HANA On-Premise](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/8de01dd25c1e443e8e2de7d2fbe1364d.html "To be able to successfully validate and use a connection to SAP S/4HANA, certain preparations have to be made.") :arrow_upper_right:.



<a name="loioa49a1e3cc50f4af89711d8306bdd8f26__S4_OP_usage"/>

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

You can access the following data:

-   for federation: standard and custom CDS view entities that are exposed using the ABAP SQL service from SAP S/4HANA \(**recommended for federation scenarios**\)

    For more information, see [Using ABAP SQL Services for Accessing Data from SAP S/4HANA](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/4d7474595a5b41bb986616262ff44a3a.html "The ABAP SQL service provides SQL-level access to published CDS view entities for SAP Datasphere. You can use the service to federate data with remote tables. Using the service requires Cloud Connector.") :arrow_upper_right:.

    > ### Note:  
    > On the *Sources* tab of the remote-table-related Data Builder editors in SAP Datasphere, the service binding name from the *SQL\_SCHEMA* authorization field is visible as \(virtual\) schema.

-   for federation and replication: \(**legacy**\)

    -   Data from virtual tables through RFC for ODP sources \(extractors\):

        -   Extraction context *ABAP\_CDS* provides access to ABAP Core Data Services \(CDS\) Views that include the annotation `@Analytics.dataextraction.enabled: true`

            For information about which ABAP CDS Views are available for extraction, see [CDS Views Enabled for Data Extraction](https://help.sap.com/viewer/8308e6d301d54584a33cd04a9861bc52/latest/en-US/b7a5b8b72d3643b7a8ecf4cd695e0791.html) in the *SAP S/4HANA* documentation.

            > ### Note:  
            > ABAP CDS Views are the preferred method over SAPI extractors when integrating SAP S/4HANA data with SAP Datasphere.

        -   Extraction context *BW* provides access to InfoProviders in SAP BW or SAP BW∕4HANA systems:

            -   DataStore objects \(advanced or classic\)

            -   CompositeProviders

            -   Queries as InfoProviders \(with a subset of OLAP capabilities\) - can be enabled in the runtime properties of queries in the BW Modeling tools

            -   InfoObjects \(characteristics\) - can be enabled in the general settings of the InfoObject editor in the BW Modeling tools


        -   Extraction context *SAPI* provides access to Service API \(SAPI\) DataSources

            > ### Note:  
            > Importing SAPI DataSources into SAP Datasphere is not supported if the DataSource contains mandatory selection fields. You will receive an error message when trying to import tables for such DataSources.

            > ### Note:  
            > Certain SAPI DataSources \(from FI-AA Business Content, for example\) may send duplicate records during snapshot replication or real-time initialization. Remote table replication runs with optimized INSERT processing on DataSource key level which leads to unique constraint violation errors. In such cases, we recommend to use a data flow which uses the remote table as source and for which the target table has selected the *Append* mode with the *Update Records By Primary Key \(UPSERT\)* option.


    -   Data from SAP ABAP Dictionary tables in SAP S/4HANA systems


    Real-time replication is supported for ODP sources. For information about any constraints, see [Replicate Data Changes in Real-Time](../Data-Integration-Monitor/replicate-data-changes-in-real-time-441d327.md).

    > ### Note:  
    > This legacy option is still supported, however we recommend using the ABAP SQL service for federation \(if available\) and replication flows for replication.




</td>
</tr>
<tr>
<td valign="top">

Model Import

</td>
<td valign="top">

You can use the connection to import semantically-rich entities from an SAP S/4HANA system which you have selected in the *Import Entities* wizard. For more information, see [Importing Entities with Semantics from SAP S/4HANA](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/845fedbd28574aa8b84239df848936f6.html "You can use the Import Entities wizard to load metadata from your SAP S/4HANA Cloud and SAP S/4HANA on-premise connections via semantically-rich objects. The wizard creates Business Builder and Data Builder entities (along with all the objects on which they depend) in SAP Datasphere.") :arrow_upper_right:. 

You can import extraction-enabled ABAP CDS views that are C1-released, that is views with annotation `@Analytics.dataextraction.enabled: true` and that are available in the connected system. For more information, see [CDS Views Enabled for Data Extraction](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/ee6ff9b281d8448f96b4fe6c89f2bdc8/b7a5b8b72d3643b7a8ecf4cd695e0791.html) in the *SAP S/4HANA* documentation.

The options to access the data depend on the version of the SAP S/4HANA system. You can see the data access option when you have selected a connection in the *Import Entities* wizard:

-   *Replication Flow to Local Tables* - available if the connected system is SAP S/4HANA 2021 or higher \(SAP\_BASIS 756 and higher\). It's the default and recommended option for these system versions.

-   *Remote Tables* - available if the connected system is SAP S/4HANA 1809 or higher \(SAP\_BASIS 753 and higher\)

    In the *Import Entities* wizard, you can change from the default *Replication Flow to Local Tables* to *Remote Tables* if your system is SAP S/4HANA 2021 or higher \(SAP\_BASIS 756 and higher\).


> ### Note:  
> Note that associated entities can only be included in the import when data access is *Replication Flow to Local Tables*. For more information, see [Importing Entities with Semantics from SAP S/4HANA](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/845fedbd28574aa8b84239df848936f6.html "You can use the Import Entities wizard to load metadata from your SAP S/4HANA Cloud and SAP S/4HANA on-premise connections via semantically-rich objects. The wizard creates Business Builder and Data Builder entities (along with all the objects on which they depend) in SAP Datasphere.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

Data Flows

</td>
<td valign="top">

You can use the connection to add source objects to a data flow.

You can replicate the following data:

-   extraction-enabled ABAP CDS views that are C1-released, that is views with annotation `@Analytics.dataextraction.enabled: true` and that are available in the connected system \(access via ABAP Pipeline Engine\)

    For more information, see [CDS Views Enabled for Data Extraction](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/ee6ff9b281d8448f96b4fe6c89f2bdc8/b7a5b8b72d3643b7a8ecf4cd695e0791.html) in the *SAP S/4HANA* documentation.

-   Tables from SAP Landscape Transformation Replication Server \(SAP LT Replication Server\) sources, for which an appropriate configuration has been created in SAP LT Replication Server.


> ### Note:  
> -   The availability of the data flow feature depends on the used version and Support Package level of SAP S/4HANA or the DMIS addon in the source. Make sure your source systems meet the required minimum versions. We recommend to use the latest available version of SAP S/4HANA and the DMIS add-on where possible and have the latest SAP notes and TCI notes implemented in your systems.
> 
>     For more information about required versions, recommended system landscape, considerations for the supported source objects, and more, see SAP Note [2890171](https://me.sap.com/notes/2890171).
> 
> -   Data flows currently support one-time loading of data \(also known as initial load\) only.
> 
> -   The data preview in the data flow editor of the *Data Builder* is **not** available, except for:
> 
>     -   CDS views if the version of the connected system is SAP S/4HANA 1909 or higher.
> 
>     -   SAP Landscape Transformation Replication Server objects if ABAP Add-on DMIS 2018 SP08 or DMIS 2020 SP04 is installed or a higher DMIS version.



</td>
</tr>
<tr>
<td valign="top">

Replication Flows

</td>
<td valign="top">

You can use the connection to add source objects to a replication flow.

You can replicate the following data:

-   extraction-enabled ABAP CDS views that are C1-released, that is views with annotation `@Analytics.dataextraction.enabled: true` and that are available in the connected system \(access via ABAP Pipeline Engine\)

    For more information, see [CDS Views Enabled for Data Extraction](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/ee6ff9b281d8448f96b4fe6c89f2bdc8/b7a5b8b72d3643b7a8ecf4cd695e0791.html) in the *SAP S/4HANA* documentation.

-   Data from ODP sources \(extraction contexts *SAPI* and *BW*\)

> ### Note:  
> The availability of the replication flow feature depends on the used version and Support Package level of SAP S/4HANA or the DMIS addon in the source. Make sure your source systems meet the required minimum versions. We recommend to use the latest available version of SAP S/4HANA and the DMIS add-on where possible and have the latest SAP notes and TCI notes implemented in your systems.
> 
> For more information about required versions, recommended system landscape, considerations for the supported source objects, and more, see SAP Note [2890171](https://me.sap.com/notes/2890171).



</td>
</tr>
</table>

> ### Note:  
> The connection type supports replication with both remote tables via Data Provisioning Agent \(SAP HANA Smart Data Integration\) and replication flows \(for on-premise systems via Cloud Connector\).
> 
> Regardless of whether you use the same connection or two separate connections, for replicating data from a dedicated source object in the source we strongly recommend to only use remote tables or replication flows and not both.





### Best Practices for Integrating Data

See [SAP Data Warehouse Cloud - First Guidance: Data Integration for ABAP Source Systems](https://www.sap.com/documents/2021/06/e8238e12-e47d-0010-bca6-c68f7e60039b.html) \(published February 2022\) for general best practices for integrating data from ABAP source systems with SAP Datasphere.



<a name="loioa49a1e3cc50f4af89711d8306bdd8f26__connection_properties"/>

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

*SAP Logon Connection Type*

</td>
<td valign="top">

Select *Application Server* to connect to a single application server, or select *Message Server* to use load balancing and connect to a message server that distributes the load to different application servers.

> ### Note:  
> The SAP Logon connection type you select here must match the connection type in the system mapping in the Cloud Connector configuration \(load balancing logon or connecting to a specific application server\).



</td>
</tr>
<tr>
<td valign="top">

\[if *SAP Logon Connection Type* = *Application Server*\] *Application Server* 

</td>
<td valign="top">

Enter the name of the application server to which you want to connect to. 

</td>
</tr>
<tr>
<td valign="top">

\[if *SAP Logon Connection Type* = *Application Server*\] *System Number* 

</td>
<td valign="top">

Enter the SAP ABAP system instance number. 

</td>
</tr>
<tr>
<td valign="top">

\[if *SAP Logon Connection Type* = *Message Server*\] *Message Server*

</td>
<td valign="top">

Enter the name of the message server to which you want to connect to.

</td>
</tr>
<tr>
<td valign="top">

\[if *SAP Logon Connection Type* = *Message Server*\] *Message Server Port*

</td>
<td valign="top">

Enter the message server port \(numerical\).

> ### Note:  
> In the Cloud Connector system mapping, make sure the message server port is specified in the *System ID* field \(see [Configure Cloud Connector](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administation, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:\).



</td>
</tr>
<tr>
<td valign="top">

\[if *SAP Logon Connection Type* = *Message Server*\] *Message Server Group*

</td>
<td valign="top">

Enter the message server group.

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

Enter the system ID.

</td>
</tr>
<tr>
<td valign="top">

*Language* 

</td>
<td valign="top">

Enter the two-digit ISO language code, EN for English or DE for German, for example. In the Data Builder, object and field descriptions are then shown in the specified language. If not set, the application uses the default logon language of the ABAP system for data flows, and EN is used for remote tables and views. 

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

Set to *true* if you want to use the connection for one or more of the following features: 

-   remote tables for data federation via the ABAP SQL service
-   data flows
-   replication flows
-   model import

The default is *false*.

> ### Note:  
> When the connection is configured for using the ABAP SQL service for data federation with remote tables, you can't use the same connection for model import.



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

\[optional\] Select *Derive Virtual Host and Port from Connection Details* or *Enter Virtual Host and Port in Separate Fields*. 

If host and port entered in the connection details match the virtual host and port from the Cloud Connector configuration, you can select *Derive Virtual Host and Port from Connection Details* and don't need to enter the values manually.

> ### Note:  
> When you select *Derive Virtual Host and Port from Connection Details* for ABAP-based connections:
> 
> -   The virtual application or message server defined in the Cloud Connector configuration must be the same application or message server that you have entered in the connection details.
> 
> -   If the *SAP Logon Connection Type* for your connection is *Application Server*: virtual port is set to ***sapgw*<system number\>**** \(with the system number that you have entered in the connection details\) to make sure that it matches the virtual port defined in the Cloud Connector configuration.
> 
> -   If the *SAP Logon Connection Type* for your connection is *Message Server*: virtual port is set to the numerical message server port that you have entered in the connection details.

> ### Note:  
> When the connection is configured for using the ABAP SQL service for data federation with remote tables and you also want to use the connection for data flows and replication flows, consider the following:
> 
> -   You must enter virtual host and port manually. Deriving virtual host and port from the connection details is not supported because the Cloud Connector configuration requires two system mappings with different virtual ports. One is for the RFC protocol used for data flows and replication flows. The other is for HTTPS protocol used for remote tables via the ABAP SQL service.
> -   The virtual host defined in the Cloud Connector system mappings must be the same for both the HTTPS and RFC protocols.
> 
> For more information, see [Using ABAP SQL Services for Accessing Data from SAP S/4HANA](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/4d7474595a5b41bb986616262ff44a3a.html "The ABAP SQL service provides SQL-level access to published CDS view entities for SAP Datasphere. You can use the service to federate data with remote tables. Using the service requires Cloud Connector.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Host* 

</td>
<td valign="top">

Enter the virtual host that you defined during Cloud Connector configuration. 

> ### Note:  
> If you're using the ABAP SQL service for data federation with this connection and also want to use it for data and replication flows, ensure the virtual host defined in the Cloud Connector system mappings is the same for both the HTTPS and RFC protocols \(see [Using ABAP SQL Services for Accessing Data from SAP S/4HANA](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/4d7474595a5b41bb986616262ff44a3a.html "The ABAP SQL service provides SQL-level access to published CDS view entities for SAP Datasphere. You can use the service to federate data with remote tables. Using the service requires Cloud Connector.") :arrow_upper_right:\).



</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Port* 

</td>
<td valign="top">

Enter the virtual port that you defined during Cloud Connector configuration. 

> ### Note:  
> -   If the *SAP Logon Connection Type* for your connection is *Application Server*: Enter ***sapgw*<system number\>**** to make sure that it matches the virtual port defined in the Cloud Connector configuration.
> -   If the *SAP Logon Connection Type* for your connection is *Message Server*: Enter a numerical port and make sure it is the port defined in the Cloud Connector configuration.
> -   If you're using the **ABAP SQL service** for data federation with this connection and also want to use it for data and replication flows: **Enter the virtual port defined in the Cloud Connector system mapping for the HTTPS protocol** which has been created for remote tables \(see [Using ABAP SQL Services for Accessing Data from SAP S/4HANA](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/4d7474595a5b41bb986616262ff44a3a.html "The ABAP SQL service provides SQL-level access to published CDS view entities for SAP Datasphere. You can use the service to federate data with remote tables. Using the service requires Cloud Connector.") :arrow_upper_right:\).



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

Select the authentication type to use to connect to SAP S/4HANA. 

You can select:

-   *User Name And Password* for basic authentication \(default value\) - This option is read-only if you set Cloud Connector to *false*.
-   *OAuth 2.0* - You can select this option only if you have set Cloud Connector to *true* to enable replication flows and data flows. Remote tables and model import currently are not supported with OAuth authentication.



</td>
</tr>
</table>



### OAuth 2.0


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

*OAuth Grant Type*

</td>
<td valign="top">

Displays *Client Credentials* as grant type used to retrieve an access token. 

</td>
</tr>
<tr>
<td valign="top">

*OAuth Token Endpoint*

</td>
<td valign="top">

Enter the API endpoint to use to request an access token.

</td>
</tr>
<tr>
<td valign="top">

*OAuth Scope*

</td>
<td valign="top">

\[optional\] Enter the OAuth scope, if applicable.

</td>
</tr>
<tr>
<td valign="top">

*OAuth Token Request Content Type*

</td>
<td valign="top">

\[optional\] Enter the content type of the OAuth2 token request. 

You can select:

-   *URL Encoded* \(default value\)

    OAuth2 token request parameters will be url-encoded and included in the HTTP request body.

-   *JSON*

    OAuth2 token request parameters will be in JSON format and included in the HTTP request body.




</td>
</tr>
</table>



### Credentials \(User Name And Password\)


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

Enter the user name that is used to connect to the SAP ABAP system. 

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



### Credentials \(OAuth 2.0\)


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

Enter the client ID to authenticate SAP Datasphere to the SAP S/4HANA system. 

</td>
</tr>
<tr>
<td valign="top">

*Client Secret*

</td>
<td valign="top">

Enter the client secret to authenticate SAP Datasphere to the SAP S/4HANA system.

</td>
</tr>
</table>



### Remote Tables


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

Select the middleware to use when connecting to and accessing SAP S/4HANA: 

-   *None* \(default\): if you don't want to use remote tables.

-   *Data Provisioning Agent*: if you want to use federation and replication via SAP HANA smart data integration ABAPAdapter \(**legacy**\).

    > ### Note:  
    > This legacy option is still supported, however we recommend using the ABAP SQL service for federation \(if available\) and replication flows for replication.

-   *Cloud Connector*: if you want to federate data from the source objects of the connection and access them remotely in the source system using the ABAP SQL service \(**recommended for federation scenarios**\).

    > ### Note:  
    > This option is supported for authentication type *User Name And Password*.




</td>
</tr>
<tr>
<td valign="top">

\[if *Data Provisioning Option* = *Data Provisioning Agent* or *Cloud Connector*\] *Data Access* 

</td>
<td valign="top">

\[read-only\] Displays how data from source objects can be accessed: 

-   *Remote and Replication*: if you selected data provisioning option *Data Provisioning Agent* \(using the SAP HANA smart data integration ABAPAdapter\).

-   *Remote Only*: if you selected data provisioning option *Cloud Connector* \(using the ABAP SQL service\).




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

\[if you selected an agent\] *Streaming Read*

</td>
<td valign="top">

Set to *On* if you want to use ABAP RFC streaming for loading tables based on small batches. Set to *Off* to use non-RFC streaming. The default is *Off*.

</td>
</tr>
<tr>
<td valign="top">

\[if *Streaming Read* = *On*\] *Gateway Host*

</td>
<td valign="top">

Enter the gateway host where the ABAP adapter would register an RFC server instance to receive callbacks with the table data batches. Usually, the gateway host is the same as the target ABAP system host.

</td>
</tr>
<tr>
<td valign="top">

\[if *Streaming Read* = *On*\] *Gateway Port*

</td>
<td valign="top">

Enter the port number of the gateway server where the ABAP adapter would register an RFC server instance to receive callbacks with the table data batches. You can find the port number for <code>sapgw<i class="varname">&lt;ABAP_instance_number&gt;</i></code> in file `/etc/services` on the ABAP host. The default port number is <code>33<i class="varname">&lt;ABAP_instance_number&gt;</i></code>. If you have a file `/etc/services` with this mapping on the Data Provisioning Agent’s host, you can also enter <code>sapgw<i class="varname">&lt;ABAP_instance_number&gt;</i></code> instead of the port number.

</td>
</tr>
<tr>
<td valign="top">

\[if *Streaming* = *On*\] *RFC Destination*

</td>
<td valign="top">

Enter the name of the RFC destination that you have created in the source. For more information, see [Prerequisites for ABAP RFC Streaming](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/62adb440e4214c53a3028a4fdb5e1156.html "If you want to stream ABAP tables for loading large amounts of data without running into memory issues it is required to meet the following requirements.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

\[if *Data Provisioning Option* = *Cloud Connector*\] *Type Map* 

</td>
<td valign="top">

Specify how ABAP data types are mapped to SAP HANA data types: 

-   ﻿*native*﻿: no conversion of ABAP data types

-   ﻿*semantic*﻿: conversion of the ABAP data types to an ABAP-independent data format

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
> -   *Fast Serialization* for replication flows is not related to *RFC Serialization* in the advanced properties of connections using a Data Provisioning Agent for remote tables.
> 
> -   For information about the prerequisites for using fast serialization in SAP Datasphere, see [Prepare Connectivity to SAP S/4HANA On-Premise](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/8de01dd25c1e443e8e2de7d2fbe1364d.html "To be able to successfully validate and use a connection to SAP S/4HANA, certain preparations have to be made.") :arrow_upper_right:.
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

</td>
</tr>
<tr>
<td valign="top">

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties. Make sure you have maintained the properties in the *Cloud Connector* section.

</td>
</tr>
<tr>
<td valign="top">

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties. Make sure you have maintained the properties in the *Cloud Connector* section. 

</td>
</tr>
<tr>
<td valign="top">

*Model Import*

</td>
<td valign="top">

To enable *Model Import*, select the live data connection that connects to your SAP S/4HANA system and select a Data Provisioning Agent.

> ### Note:  
> When the connection is configured for using the ABAP SQL service for data federation with remote tables, you can't use the same connection for model import.



</td>
</tr>
</table>



<a name="loioa49a1e3cc50f4af89711d8306bdd8f26__section_j21_tdg_knb"/>

## Advanced Connection Properties

When you've selected a Data Provisioning Agent, you can configure advanced connection properties to enable specific customer scenarios. In the connection creation wizard, you configure advanced properties in an additional wizard step. When editing the connection to configure the properties, scroll down and click the *Show Advanced Properties button*. Advanced properties have default values that you can override according to your customer scenario’s needs.

Available properties:

-   *Connection Pool Size*

-   *Connection Limit*

-   *Extractor’s ODP Version*

-   *CDC Batch Size, MB*

-   *RFC Unicode*

-   \[if *RFC Unicode* = *No*\] *RFC Character Encoding*

-   *SNC Mode*

-   \[if *SNC Mode* = *On*\] *SNC Library*

-   \[if *SNC Mode* = *On*\] *SNC Name of Client*

-   \[if *SNC Mode* = *On*\] *SNC Name of SAP Server*

-   \[if *SNC Mode* = *On*\] *SNC SSO*

-   \[if *SNC Mode* = *On*\] *SNC Quality of Protection*

-   *RFC Serialization* \(requires Data Provisioning Agent version 2.3.7.2 or higher\)

-   \[if *Streaming Read* = *On*\] *Batch Size, MB*

-   \[if *Streaming Read* = *On*\] *Batch Receive Timeout*

-   \[if *Streaming Read* = *On*\] *RFC Trace*


For more information, see [SAP ABAP Adapter Remote Source Configuration](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/8575941eb7a344abadc21721418e28cb.html) in the*SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*.

