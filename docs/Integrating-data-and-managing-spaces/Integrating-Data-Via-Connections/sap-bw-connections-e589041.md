<!-- loioe589041e80264f43b6c209c407336376 -->

# SAP BW Connections

Use an *SAP BW* connection to access data from virtual tables through RFC for ODP sources \(extractors\) and ABAP Dictionary tables from SAP Business Warehouse \(SAP BW\) or SAP BW∕4HANA systems. For SAP BW systems that don't have the ABAP Pipeline Engine extension installed, ODP extractors can be used as sources in data flows.

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

This topic contains the following sections:

-   [Supported Features](sap-bw-connections-e589041.md#loioe589041e80264f43b6c209c407336376__BW_usage)
-   [Prerequisites](sap-bw-connections-e589041.md#loioe589041e80264f43b6c209c407336376__BW_prerequisites)
-   [Configuring Connection Properties](sap-bw-connections-e589041.md#loioe589041e80264f43b6c209c407336376__BW_connection_properties)



<a name="loioe589041e80264f43b6c209c407336376__BW_prerequisites"/>

## Prerequisites



### Remote Tables

Before you can use the connection for remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the ABAPAdapter.

    For the *Language* setting in the connection properties to have an effect on the language shown in the Data Builder, Data Provisioning Agent version 2.0 SP 05 Patch 10 \(2.5.1\) or higher is required.

    For more information, see [Preparing Data Provisioning Agent Connectivity](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f1a39d1a763e48c8872f45c110a5a4e2.html "Most connection types supporting remote tables use SAP HANA Smart Data Integration (SDI) and its Data Provisioning Agent. Before using the connection, the agent requires an appropriate setup.") :arrow_upper_right:.

-   The ABAP user specified in the credentials of the SAP ABAP connection needs to have a specific set of authorizations in the SAP ABAP system. For more information, see: [Authorizations](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/bcc0ff2acd6a4476b2912ff4cd71cd91.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation.

-   To access and copy data from SAP BW objects such as InfoProviders or characteristics, the appropriate authorization objects like S\_RS\_ADSO or S\_RS\_IOBJA are required for the ABAP user. For more information, see [Overview: Authorization Objects](https://help.sap.com/viewer/2e90b26cf7484203a523bf0f4b1bc137/7.5.latest/en-US/4c658f3245e31ca6e10000000a42189c.html) in the *SAP NetWeaver* documentation.

    If you want to access data from SAP BW Queries, make sure that the ABAP user has the required analysis authorizations to read the data and that characteristic 0TCAIPROV \(InfoProvider\) in the authorization includes `@Q`, which is the prefix for Queries as InfoProviders. For more information, see [Defining Analysis Authorizations](https://help.sap.com/viewer/2e90b26cf7484203a523bf0f4b1bc137/7.5.latest/en-US/4a27a9cf81661d10e10000000a42189b.html) in the *SAP NetWeaver* documentation.

-   If you want to stream ABAP tables for loading large amounts of data without running into memory issues, you need to configure suitable security privileges for successful registration on an SAP Gateway and you need to create an RFC destination of type TCP/IP in the ABAP source system. With the RFC destination you register the Data Provisioning Agent as server program in the source system. For more information, see [Prerequisites for ABAP RFC Streaming](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/62adb440e4214c53a3028a4fdb5e1156.html "If you want to stream ABAP tables for loading large amounts of data without running into memory issues it is required to meet the following requirements.") :arrow_upper_right:.

-   To be able to use ABAP Dictionary tables from connections to a SAP BW∕4HANA system for remote tables and creating views, please make sure that SAP note [2872997](https://me.sap.com/notes/2872997) has been applied to the system.




### Data Flows

Before you can use the connection for data flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    In the Cloud Connector configuration, an administrator has made sure that access to the required resources is granted.

    For more information, see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:.

-   If you want to enable secure network communication \(SNC\) to an ABAP-based on-premise system, which you want to connect to for using data flows, configure SNC in the Cloud Connector and consider the SNC-specific settings when adding the system mapping information:

    -   In the *Back-end Type* field, select *ABAP System*.
    -   In the *Protocol* field, select *RFC SNC*.
    -   In the *Principal Type* field, select *X.509 Certificate*.
    -   In the *SNC Partner Name* field, enter the ABAP system's SNC identity name \(for example, `p:CN=SID, O=Trust Community, C=DE`\). The SNC partner name needs to contain the correct SNC identification of the ABAP system. The value can typically be found in the ABAP system instance profile parameter `snc/identity/as` \(and hence is provided per application server\).

    For more information about configuring SNC, see [Initial Configuration \(RFC\)](https://help.sap.com/viewer/DRAFT/cca91383641e40ffbe03bdc78f00f681/Validation/en-US/f09eefe71d1e4d4484e1dd4b121585fb.html) in the *SAP BTP Connectivity* documentation.




<a name="loioe589041e80264f43b6c209c407336376__BW_usage"/>

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

You can use the connection type to access:

-   data from virtual tables through RFC for ODP sources \(extractors\):

    -   Extraction context *ABAP\_CDS* provides access to ABAP Core Data Services \(CDS\) Views that include the annotation `@Analytics.dataextraction.enabled: true`

        For information about which ABAP CDS Views are available for extraction, see [CDS Views Enabled for Data Extraction](https://help.sap.com/viewer/8308e6d301d54584a33cd04a9861bc52/latest/en-US/b7a5b8b72d3643b7a8ecf4cd695e0791.html) in the *SAP S/4HANA* documentation.

    -   Extraction context *BW* provides access to InfoProviders in SAP BW or SAP BW∕4HANA systems:

        -   DataStore objects \(advanced or classic\)

        -   CompositeProviders

        -   Queries as InfoProviders \(with a subset of OLAP capabilities\) - can be enabled in the runtime properties of queries in the BW Modeling tools

        -   InfoObjects \(characteristics\) - can be enabled in the general settings of the InfoObject editor in the BW Modeling tools


    -   Extraction context *SAPI* provides access to Service API \(SAPI\) DataSources

        > ### Note:  
        > Importing SAPI DataSources into SAP Datasphere is not supported if the DataSource contains mandatory selection fields. You will receive an error message when trying to import tables for such DataSources.


-   data from SAP ABAP Dictionary tables in SAP S/4HANA systems


Real-time replication is supported for ODP sources. For information about any constraints, see [Replicate Data Changes in Real-Time](../Data-Integration-Monitor/replicate-data-changes-in-real-time-441d327.md).

For more information, see [Monitoring Remote Tables](../Data-Integration-Monitor/monitoring-remote-tables-4dd95d7.md). 

> ### Note:  
> Certain SAPI DataSources \(from FI-AA Business Content, for example\) may send duplicate records during snapshot replication or real-time initialization. Remote table replication runs with optimized INSERT processing on DataSource key level which leads to unique constraint violation errors. In such cases we recommend to use a data flow which uses the remote table as source and for which the target table has selected the *Append* mode with the *Update Records By Primary Key \(UPSERT\)* option.



</td>
</tr>
<tr>
<td valign="top">

Data Flows

</td>
<td valign="top">

You can use the connection to add source objects to a data flow.

For legacy SAP BW systems that do not have the ABAP Pipeline Engine extension or DMIS Addon installed, you can leverage Operational Data Provisioning \(ODP\) connectivity und use ODP extractors as sources in data flows. Note that ABAP Dictionary tables are not supported as sources in data flows.

> ### Note:  
> The data preview in the data flow editor of the Data Builder is **not** available for SAP BW sources.



</td>
</tr>
</table>

> ### Note:  
> If you want to provide SAP BW∕4HANA business semantics to SAP Datasphere, you can use connection type SAP BW∕4HANA*Model Import* and import SAP BW∕4HANA models based on analytic queries. During the import, the semantics of the underlying SAP BW∕4HANA models are translated into native SAP Datasphere entities that you can use to access the data stored in SAP BW∕4HANA, to enhance the data in SAP Datasphere, or to consume them by analytic clients. For more information, see [SAP BW∕4HANA Model Transfer Connections](sap-bw-4hana-model-transfer-connections-1caba95.md).

> ### Note:  
> This connection type doesn't support replication flows. Instead, we recommend using the *SAP ABAP* connection type for replication flows.





### Best Practices for Integrating Data

See [SAP Data Warehouse Cloud - First Guidance: Data Integration for ABAP Source Systems](https://www.sap.com/documents/2021/06/e8238e12-e47d-0010-bca6-c68f7e60039b.html) \(published February 2022\) for general best practices for integrating data from ABAP source systems with SAP Datasphere.



<a name="loioe589041e80264f43b6c209c407336376__BW_connection_properties"/>

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
> In the Cloud Connector system mapping, make sure the message server port is specified in the *System ID* field \(see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:\).



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

\[optional\] Set to *true* if your source is an on-premise source and you want to use the connection for data flows. The default is *false*. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

\[optional\] Select a location. 

> ### Note:  
> To select another location ID than the default location, *Connection* privilege with *Read* permission is required. The privilege is neither included in the *DW Integrator* nor in the *DW Space Administrator* role. If you need to select a location ID, ask your tenant administrator to either assign your user to a global role that is based on the *DW Administrator* role or to assign your user to a custom global role \(with license type SAP Datasphere\) that includes the required *Connection* privilege with *Read* permission. 



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



</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Host* 

</td>
<td valign="top">

Enter the virtual host that you defined during Cloud Connector configuration. 

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

To enable *Remote Tables*, complete the following properties: 


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

*Data Provisioning Agent* 

</td>
<td valign="top">

Select an agent if you want to use the connection to access data via imported remote tables and to build views. 

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

Enter the name of the RFC destination that you have created in the source. For more information, see [Prerequisites for ABAP RFC Streaming](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/62adb440e4214c53a3028a4fdb5e1156.html "If you want to stream ABAP tables for loading large amounts of data without running into memory issues it is required to meet the following requirements.") :arrow_upper_right:. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Streaming* = *On*\] *Execution Targets*

</td>
<td valign="top">

Enter a comma-separated list of execution targets for streaming batch jobs.

Each time a streaming query on an ABAP table is executed, the system assigns the corresponding streaming batch job to a target server chosen randomly from this list.

If you don't specify a list of execution targets, the source system assigns the target servers.

> ### Note:  
> This property requires Data Provisioning Agent version 2.7.0.0 or higher.



</td>
</tr>
</table>



</td>
</tr>
<tr>
<td valign="top">

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties.Make sure you have maintained the properties in the *Cloud Connector* section. 

</td>
</tr>
</table>



<a name="loioe589041e80264f43b6c209c407336376__section_j21_tdg_knb"/>

## Advanced Connection Properties

When you've selected a Data Provisioning Agent, you can configure advanced connection properties to enable specific customer scenarios. In the connection creation wizard, you configure advanced properties in an additional wizard step. When editing the connection to configure the properties, scroll down and click the *Show Advanced Properties* button. Advanced properties have default values that you can override according to your customer scenario’s needs.

Available properties:

-   *Connection Pool Size*

-   *Connection Limit*

-   *Extractor’s ODP Version*

-   *CDC Batch Size, MB*: You can adjust the maximum package size that is used when replicating extractor data via ODP \(ODP contexts BW, ABAP\_CDS, SAPI\). The default value is 50 MB. The package size can impact performance and memory workload. For example, if the ODP source is very large and the CDC batch size is defined too small, this will result in too many small units being transferred, which impacts performance.

-   *RFC Unicode*

-   \[if *RFC Unicode* = *No*\] *RFC Character Encoding*

-   *RFC Serialization* \(requires Data Provisioning Agent version 2.3.7.2 or higher\)

-   *RFC Trace*

-   *SNC Mode*

-   \[if *SNC Mode* = *On*\] *SNC Library*

-   \[if *SNC Mode* = *On*\] *SNC Name of Client*

-   \[if *SNC Mode* = *On*\] *SNC Name of SAP Server*

-   \[if *SNC Mode* = *On*\] *SNC SSO*

-   \[if *SNC Mode* = *On*\] *SNC Quality of Protection*

-   Properties that are only considered if *Streaming Read* is set to *On*in the *Remote Tables* section of the connection:
    -   *Batch Size, MB*

    -   *Batch Receive Timeout*



For more information, see [SAP ABAP Adapter Remote Source Configuration](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/8575941eb7a344abadc21721418e28cb.html) in the*SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*.

