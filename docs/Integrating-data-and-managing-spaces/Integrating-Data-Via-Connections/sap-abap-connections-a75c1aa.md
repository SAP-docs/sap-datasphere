<!-- loioa75c1aacf951449ba3b740c7e46da3a9 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# SAP ABAP Connections

Use an *SAP ABAP* connection to access data from SAP ABAP on-premise systems through RFC or to access data from cloud source systems such as SAP S/4HANA Cloud through Web Socket RFC.



This topic contains the following sections:

-   [Supported Features](sap-abap-connections-a75c1aa.md#loioa75c1aacf951449ba3b740c7e46da3a9__ABAP_usage)
-   [Configuring Connection Properties](sap-abap-connections-a75c1aa.md#loioa75c1aacf951449ba3b740c7e46da3a9__connection_properties)

For information about the required prerequisites, see [Prepare Connectivity to SAP ABAP Systems](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/76c9ac1a318c4de2bea29e72c64be8a0.html "To be able to successfully validate and use a connection to an SAP ABAP system for remote tables or data flows, certain preparations have to be made.") :arrow_upper_right:.



<a name="loioa75c1aacf951449ba3b740c7e46da3a9__ABAP_usage"/>

## Supported Features

> ### Note:  
> In file spaces, only replication flows are supported. Remote tables and data flows are not supported.


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

-   for federation: standard and custom CDS view entities that are exposed using the ABAP SQL service from SAP S/4HANA Cloud or SAP S/4HANA \(**recommended for federation scenarios**\)

    For more information, see:

    -   [Using ABAP SQL Services for Accessing Data from SAP S/4HANA Cloud](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/ef2b2238154f4cd78a08df360447c1d5.html "The ABAP SQL service provides SQL-level access to published CDS view entities for SAP Datasphere. You can use the service to replicate data with replication flows or to federate data with remote tables.") :arrow_upper_right:
    -   [Using ABAP SQL Services for Accessing Data from SAP S/4HANA](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/4d7474595a5b41bb986616262ff44a3a.html "The ABAP SQL service provides SQL-level access to published CDS view entities for SAP Datasphere. You can use the service to federate data with remote tables. Using the service requires Cloud Connector.") :arrow_upper_right:

    > ### Note:  
    > On the *Sources* tab of the remote-table-related Data Builder editors in SAP Datasphere, the service binding name from the *SQL\_SCHEMA* authorization field is visible as \(virtual\) schema.

-   for federation and replication from ABAP-based on-premise systems \(**legacy**\):

    -   Data from virtual tables through RFC for ODP sources \(extractors\):

        -   Extraction context *ABAP\_CDS* provides access to ABAP Core Data Services \(CDS\) Views that include the annotation `@Analytics.dataextraction.enabled: true` \(in SAP ABAP on-premise systems\) and do not contain the annotation `@Analytics.Query: true`.

            For information about which ABAP CDS Views are available for extraction, see [CDS Views Enabled for Data Extraction](https://help.sap.com/viewer/8308e6d301d54584a33cd04a9861bc52/latest/en-US/b7a5b8b72d3643b7a8ecf4cd695e0791.html) in the *SAP S/4HANA* documentation.

            > ### Note:  
            > For SAP S/4HANA on-premise, ABAP CDS Views are the preferred method over SAPI extractors when integrating data with SAP Datasphere.

        -   Extraction context *BW* provides access to InfoProviders in SAP BW or SAP BW∕4HANA systems:

            -   DataStore objects \(advanced or classic\)

            -   CompositeProviders

            -   Queries as InfoProviders \(with a subset of OLAP capabilities\) - can be enabled in the runtime properties of queries in the BW Modeling tools

            -   InfoObjects \(characteristics\) - can be enabled in the general settings of the InfoObject editor in the BW Modeling tools


            > ### Note:  
            > For accessing CompositeProviders and Queries in SAP BW∕4HANA we strongly recommended to use the model import with the specific connection type*SAP BW/4HANA Model Transfer*. For more information, see [SAP BW∕4HANA Model Transfer Connections](sap-bw-4hana-model-transfer-connections-1caba95.md).

            > ### Note:  
            > To import BW Hierarchies and deploy them as remote tables in SAP Datasphere, use the /BI\*/H*<InfoObject name\>* tables with data access via SAP ABAP Dictionary tables instead of using ODP extraction context *BW*. In the Data Builder, you can find the tables in the *ABAPTABLES* folder of the connection.

        -   Extraction context *SAPI* provides access to Service API \(SAPI\) DataSources

            > ### Note:  
            > Importing SAPI DataSources into SAP Datasphere is not supported if the DataSource contains mandatory selection fields. You will receive an error message when trying to import tables for such DataSources.

            > ### Note:  
            > Certain SAPI DataSources \(from FI-AA Business Content, for example\) may send duplicate records during snapshot replication or real-time initialization. Remote table replication runs with optimized INSERT processing on DataSource key level which leads to unique constraint violation errors. In such cases, we recommend to use a data flow which uses the remote table as source and for which the target table has selected the *Append* mode with the *Update Records By Primary Key \(UPSERT\)* option.


    -   Data from SAP ABAP Dictionary tables in SAP ABAP on-premise systems


    Real-time replication is supported for ODP sources. For information about any constraints, see [Replicate Data Changes in Real-Time](../Data-Integration-Monitor/replicate-data-changes-in-real-time-441d327.md).

    > ### Note:  
    > This legacy option is still supported, however we recommend using the ABAP SQL service for federation \(if available\) and replication flows for replication.




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

    For more information, see:

    -   in the *SAP S/4HANA Cloud* documentation: [Data Integration](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/c3a5da91691d4ebd89748d9f40af7a4c.html) and [CDS Views Enabled for Data Extraction](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/870d66c6bfc44d6c9f128c888f0c7957.html)

    -   in the *SAP S/4HANA* documentation: [CDS Views Enabled for Data Extraction](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/ee6ff9b281d8448f96b4fe6c89f2bdc8/b7a5b8b72d3643b7a8ecf4cd695e0791.html)


-   Tables from SAP Landscape Transformation Replication Server \(SAP LT Replication Server\) sources, for which an appropriate configuration has been created in SAP LT Replication Server. In the *Sources* of the data flow editor, you then can find the source objects in an *SLT - SAP LT Replication Server* folder of the connection.


> ### Note:  
> -   The availability of the data flow feature depends on the used version and Support Package level of SAP S/4HANA or the DMIS addon in the source. Make sure your source systems meet the required minimum versions. We recommend to use the latest available version of SAP S/4HANA and the DMIS add-on where possible and have the latest SAP notes and TCI notes implemented in your systems.
> 
>     For more information about required versions, recommended system landscape, considerations for the supported source objects, and more, see SAP Note [2890171](https://me.sap.com/notes/2890171).
> 
> -   Data flows currently support one-time loading of data \(also known as initial load\) only.
> 
> -   The data preview in the data flow editor of the *Data Builder* is **not** available, except for:
> 
>     -   CDS views if the version of the connected system is SAP S/4HANA on-premise 1909 or SAP S/4HANA 1909 or a higher version respectively.
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

You can access the following data:

-   extraction-enabled ABAP CDS views that are C1-released, that is views with annotation `@Analytics.dataextraction.enabled: true` and that are available in the connected system \(access via ABAP Pipeline Engine\)

    For more information, see:

    -   in the *SAP S/4HANA Cloud* documentation: [Data Integration](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/c3a5da91691d4ebd89748d9f40af7a4c.html) and [CDS Views Enabled for Data Extraction](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/870d66c6bfc44d6c9f128c888f0c7957.html)

    -   in the *SAP S/4HANA* documentation: [CDS Views Enabled for Data Extraction](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/ee6ff9b281d8448f96b4fe6c89f2bdc8/b7a5b8b72d3643b7a8ecf4cd695e0791.html)


    > ### Note:  
    > When adding source objects in replication flows, you can find the CDS views in the CDS\_EXTRACTION container.

-   standard and custom CDS view entities that are exposed using the SQL service from SAP BTP, ABAP environment, orSAP S/4HANA Cloud, respectively

    For more information, see:

    -   [Using ABAP SQL Services for Accessing Data from SAP S/4HANA Cloud](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/ef2b2238154f4cd78a08df360447c1d5.html "The ABAP SQL service provides SQL-level access to published CDS view entities for SAP Datasphere. You can use the service to replicate data with replication flows or to federate data with remote tables.") :arrow_upper_right:
    -   [Using ABAP SQL Services for Accessing Data from SAP S/4HANA](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/4d7474595a5b41bb986616262ff44a3a.html "The ABAP SQL service provides SQL-level access to published CDS view entities for SAP Datasphere. You can use the service to federate data with remote tables. Using the service requires Cloud Connector.") :arrow_upper_right:

    > ### Note:  
    > When adding source objects in replication flows, you can find the CDS view entities in the SQL\_SERVICE container.

-   Tables from SAP Landscape Transformation Replication Server \(SAP LT Replication Server\) sources, for which an appropriate configuration has been created in SAP LT Replication Server.

-   Data from ODP sources \(extraction contexts *SAPI* and *BW*\)


> ### Note:  
> -   The availability of the replication flow feature depends on the used version and Support Package level of SAP S/4HANA or the DMIS addon in the source. Make sure your source systems meet the required minimum versions. We recommend to use the latest available version of SAP S/4HANA and the DMIS add-on where possible and have the latest SAP notes and TCI notes implemented in your systems.
> 
>     For more information about required versions, recommended system landscape, considerations for the supported source objects, and more, see SAP Note [2890171](https://me.sap.com/notes/2890171).
> 
> -   The SAP BW and SAP ECC connection types don't support replication flows. Instead, you can use the *SAP ABAP* connection type to use replication flows for replication from SAP BW, SAP BW/4HANA or SAP ECC systems.



</td>
</tr>
</table>

> ### Note:  
> The connection type supports replication with both remote tables via Data Provisioning Agent \(SAP HANA Smart Data Integration\) and replication flows \(for on-premise systems via Cloud Connector\). Generally, for replication scenarios, we recommend to use replication flows.





### Best Practices for Integrating Data

See [SAP Data Warehouse Cloud - First Guidance: Data Integration for ABAP Source Systems](https://www.sap.com/documents/2021/06/e8238e12-e47d-0010-bca6-c68f7e60039b.html) \(published February 2022\) for general best practices for integrating data from ABAP source systems with SAP Datasphere.



<a name="loioa75c1aacf951449ba3b740c7e46da3a9__connection_properties"/>

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

Select the protocol that you want to use to connect to the source system: 

-   *RFC \(Use for on Premise ABAP Systems\)* to connect to an ABAP on-premise system

    You can use the connection to your on-premise system for:

    -   remote tables for data federation via the ABAP SQL service and Cloud Connector
    -   remote tables via Data Provisioning Agent \(legacy; supported for basic authentication with user name and password\)
    -   data flows via Cloud Connector \(supported for all available authentication types\)
    -   replication flows via Cloud Connector \(supported for all available authentication types\)

-   *Web Socket RFC \(Use for S/4HANA Cloud Systems\)* to connect to an ABAP cloud system such as SAP S/4HANA Cloud

    You can use the connection to your SAP S/4HANA Cloud system for:

    -   remote tables for data federation via the ABAP SQL service \(supported for X.509 Client Certificate authentication\)
    -   data flows \(supported for all available authentication types\)
    -   replication flows \(supported for all available authentication types\)


The default is *RFC \(Use for on Premise ABAP Systems\)*.

</td>
</tr>
<tr>
<td valign="top">

\[if *Protocol* = *RFC \(Use for on Premise ABAP Systems\)*\] *SAP Logon Connection Type*

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
> In the Cloud Connector system mapping, make sure the message server port is specified in the *System ID* field \(see [Configure Cloud Connector](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:\).



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

\[if *Protocol* = *Web Socket RFC \(Use for S/4HANA Cloud Systems\)*\] *Application Server*

</td>
<td valign="top">

Enter the name of the application server to which you want to connect to.

</td>
</tr>
<tr>
<td valign="top">

\[if *Protocol* = *Web Socket RFC \(Use for S/4HANA Cloud Systems\)*\] *Port*

</td>
<td valign="top">

Enter the port number of the WebSocket RFC connection endpoint.

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

\[optional\] Set to *true* if you want to use the connection for one or more of the following features: 

-   remote tables for data federation via the ABAP SQL service
-   data flows
-   replication flows

The default is *false*.

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

\[optional\] Select how you want to specify the virtual destination. 

You can select:

-   *Derive Virtual Host and Port from Connection Details* \(default\)

    If host and port entered in the connection details match the virtual host and port from the Cloud Connector configuration, you don't need to enter the values manually.

-   *Enter Virtual Host and Port in Separate Fields*


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

Select the authentication type to use to connect to the SAP ABAP system. 

You can select:

-   *User Name And Password* for basic authentication \(default value\) - This option is read-only if you set Cloud Connector to *false*.
-   *OAuth 2.0* - You can select this option only if you have selected the *RFC* protocol and if you have set Cloud Connector to *true* to enable replication flows and data flows. Remote tables currently are not supported with OAuth authentication.

    For information about setting up OAuth 2.0 authentication including creating an OAuth client in SAP Datasphere, see [Prepare OAuth 2.0 Authentication for SAP ABAP and SAP S/4HANA Connections](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/03dde8504a4645b08d6e4bb0d246ca19.html "You can use OAuth 2.0 authentication with client credentials for SAP ABAP (on-premise) and SAP S/4HANA connections, supporting replication flows and data flows. Using OAuth 2.0 authentication requires the set up for technical user propagation with activities in the Cloud Connector, in the ABAP on-premise system, and in SAP Datasphere.") :arrow_upper_right:.

-   *X.509 Client Certificate* - You can select this option if you have selected the *Web Socket RFC* protocol.

    For information about setting up certificate-based authentication, see *X.509 Client Certificates* in [Prepare Connectivity to SAP S/4HANA Cloud](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/abb159e027184c98a54fc1b2a88dd3f5.html "To be able to successfully validate and use a connection to SAP S/4HANA Cloud, certain preparations have to be made.") :arrow_upper_right:.




</td>
</tr>
</table>



### OAuth 2.0

If *Authentication Type* = *OAuth 2.0*:


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

Enter the SAP Datasphere *Token URL* which is available under <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *App Integration*** \> ***OAuth Clients*\( see [Create an OAuth2.0 Client with a Technical User Purpose](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/88b13468fc3c4ebd972bcb8faa6cafbf.html "Users with an administrator role can create OAuth2.0 clients with a technical user purpose and provide the client parameters to users, giving them limited privileges and permissions when connecting clients, tools, or apps to SAP Datasphere.") :arrow_upper_right:\).

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



### Credentials \(OAuth 2.0\)

If *Authentication Type* = *OAuth 2.0*:


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

Enter the client ID you received when creating the OAuth client in SAP Datasphere. 

</td>
</tr>
<tr>
<td valign="top">

*Client Secret*

</td>
<td valign="top">

Enter the client secret you received when creating the OAuth client in SAP Datasphere.

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

Select the middleware to use when connecting to and accessing the ABAP-based system: 

-   *None* \(default\): if you don't want to use remote tables.

-   \[RFC protocol\] *Data Provisioning Agent*: if you want to use federation and replication via SAP HANA smart data integration ABAPAdapter \(**legacy**\).

    > ### Note:  
    > This legacy option is still supported, however we recommend using the ABAP SQL service for federation \(if available\) and replication flows for replication.

-   \[RFC protocol\] *Cloud Connector* / \[Web Socket RFC protocol\] *Direct*: if you want to federate data from the source objects of the connection and access them remotely in the source system using the ABAP SQL service \(**recommended for federation scenarios**\).


> ### Note:  
> -   Remote tables are not supported for authentication type *OAuth 2.0*.
> -   Remote tables are not supported for authentication type *X.509 Client Certificate* if you're using the *RFC* protocol and data provisioning option *Cloud Connector* \(RFC protocol\)



</td>
</tr>
<tr>
<td valign="top">

\[if *Data Provisioning Option* = *Data Provisioning Agent*, *Cloud Connector*, or *Direct*\] *Data Access* 

</td>
<td valign="top">

\[read-only\] Displays how data from source objects can be accessed: 

-   *Remote and Replication*: if you selected data provisioning option *Data Provisioning Agent* \(using the SAP HANA smart data integration ABAPAdapter\).

-   *Remote Only*: if you selected data provisioning option *Cloud Connector* or *Direct* \(using the ABAP SQL service\).




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

\[if *Data Provisioning Option* = *Cloud Connector* or *Direct*\] *Type Map* 

</td>
<td valign="top">

Specify how ABAP data types are mapped to SAP HANA data types: 

-   ﻿*native*﻿: no conversion of ABAP data types

-   ﻿*semantic*﻿: conversion of the ABAP data types to an ABAP-independent data format

-   *semanticDatsTimsAsWchar*: like *semantic*, except that the ABAP types DATS and TIMS are mapped to the ODBC type SQL\_WCHAR to allow for lossless conversion of date literals and time literals




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

To enable*Remote Tables*, complete the connection properties in the *Remote Tables* section. If your source is an on-premise source and you want to use remote tables for data federation via the ABAP SQL service, make sure you have maintained the properties in the *Cloud Connector* section.

> ### Note:  
> In file spaces, only replication flows are supported. Remote tables are not supported.



</td>
</tr>
<tr>
<td valign="top">

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties. If your source is an on-premise source, make sure you have maintained the properties in the *Cloud Connector* section.

> ### Note:  
> In file spaces, only replication flows are supported. Data flows are not supported.



</td>
</tr>
<tr>
<td valign="top">

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties. If your source is an on-premise source, make sure you have maintained the properties in the *Cloud Connector* section. 

</td>
</tr>
</table>



<a name="loioa75c1aacf951449ba3b740c7e46da3a9__section_j21_tdg_knb"/>

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

