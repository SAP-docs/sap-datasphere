<!-- loioe589041e80264f43b6c209c407336376 -->

# SAP BW Connections

Use an *SAP BW* connection to access data from virtual tables through RFC for ODP sources \(extractors\) and ABAP Dictionary tables from SAP Business Warehouse \(SAP BW\) or SAP BW∕4HANA systems. For SAP BW systems that don't have the ABAP Pipeline Engine extension installed, ODP extractors can be used as sources in data flows.



<a name="loioe589041e80264f43b6c209c407336376__section_j1b_byq_spb"/>

## Prerequisites

See: [Prepare Connectivity to SAP BW](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/b0b371e1c06546c2b5fd0c22e1b0cdaf.html "To be able to successfully validate and use a connection to SAP BW for remote tables or data flows, certain preparations have to be made.") :arrow_upper_right:



<a name="loioe589041e80264f43b6c209c407336376__section_n34_dcc_x4b"/>

## Using the Connection

The connection type supports the remote table as well as the data flow feature.

> ### Note:  
> If you want to provide SAP BW∕4HANA business semantics to SAP Datasphere, you can use connection type *SAP BW/4HANA Model Import* and import SAP BW∕4HANA models based on analytic queries. During the import, the semantics of the underlying SAP BW∕4HANA models are translated into native SAP Datasphere entities that you can use to access the data stored in SAP BW∕4HANA, to enhance the data in SAP Datasphere, or to consume them by analytic clients. For more information, see [SAP BW∕4HANA Model Transfer Connections](sap-bw-4hana-model-transfer-connections-1caba95.md).

> ### Note:  
> This connection type doesn't support replication flows. Instead, we recommend using the *SAP ABAP* connection type for replication flows.



### Remote Tables

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


Supported data access methods for remote tables:

-   Remote
-   Replication \(snapshot\)
-   For ODP sources: Replication \(real-time\)

    For more information about the prerequisites, see [Replicate Data Changes in Real-Time](../Data-Integration-Monitor/replicate-data-changes-in-real-time-441d327.md).


For more information, see [Replicating Data and Monitoring Remote Tables](../Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md). 

> ### Note:  
> Certain SAPI DataSources \(from FI-AA Business Content, for example\) may send duplicate records during snapshot replication or real-time initialization. Remote table replication runs with optimized INSERT processing on DataSource key level which leads to unique constraint violation errors. In such cases we recommend to use a data flow which uses the remote table as source and for which the target table has selected the *Append* mode with the *Update Records By Primary Key \(UPSERT\)* option.



### Data Flows

For legacy SAP BW systems that do not have the ABAP Pipeline Engine extension or DMIS Addon installed, you can leverage Operational Data Provisioning \(ODP\) connectivity und use ODP extractors as sources in data flows. Note that ABAP Dictionary tables are not supported as sources in data flows.

> ### Note:  
> The data preview in the data flow editor of the Data Builder is **not** available for SAP BW sources.





### Best Practices for Integrating Data

See [SAP Data Warehouse Cloud - First Guidance: Data Integration for ABAP Source Systems](https://www.sap.com/documents/2021/06/e8238e12-e47d-0010-bca6-c68f7e60039b.html) \(published February 2022\) for general best practices for integrating data from ABAP source systems with SAP Datasphere.



<a name="loioe589041e80264f43b6c209c407336376__section_xk3_jrv_r4b"/>

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

Enter the message server port.



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

Set to *true* if your source is an on-premise source and you want to use the connection for data flows. The default is *false*. 



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 



</td>
<td valign="top">

Select a location. 

> ### Note:  
> To select another location ID than the default location, *Connection.Read* privilege is required. The privilege is not included in the *DW Integrator* or *DW Space Administrator* role. If you need to select a location ID, ask your tenant administrator to either assign the *DW Administrator* role to your user or to create a custom role containing the required privileges.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Virtual Destination* 



</td>
<td valign="top">

Select *Derive Virtual Host and Port from Connection Details* or *Enter Virtual Host and Port in Separate Fields*. 

If host and port entered in the connection details match the virtual host and port from the Cloud Connector configuration, you can select *Derive Virtual Host and Port from Connection Details* and don't need to enter the values manually.

> ### Note:  
> When you select *Derive Virtual Host and Port from Connection Details* for ABAP-based connections, virtual port is set to ***sapgw*<system number\>**** to make sure that it matches the virtual port defined in the Cloud Connector configuration.



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

To enable *Remote Tables*: 


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

Enter the name of the RFC destination that you have created in the source. For more information, see [Prerequisites for ABAP RFC Streaming](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/62adb440e4214c53a3028a4fdb5e1156.html "If you want to stream ABAP tables for loading large amounts of data without running into memory issues it is required to meet the following requirements.") :arrow_upper_right:. 



</td>
</tr>
</table>

*Data Flows* are enabled without the need to set any additional connection properties. Make sure you have maintained the properties in the *Cloud Connector* section.



<a name="loioe589041e80264f43b6c209c407336376__section_j21_tdg_knb"/>

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

-   \[if *Streaming Read* = *On*\] *Batch Size, MB*

-   \[if *Streaming Read* = *On*\] *Batch Receive Timeout*

-   \[if *Streaming Read* = *On*\] *RFC Trace*


For more information, see [SAP ABAP Adapter Remote Source Configuration](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/8575941eb7a344abadc21721418e28cb.html) in the*SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*.

