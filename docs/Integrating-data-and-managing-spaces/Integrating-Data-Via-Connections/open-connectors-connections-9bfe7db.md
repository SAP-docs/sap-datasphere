<!-- loio9bfe7db51216449d985a0b59f5e181c4 -->

# Open Connectors Connections

Use an *Open Connectors* connection to access data from sources that are connected to the SAP Open Connectors account that is integrated with your space. 

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).



<a name="loio9bfe7db51216449d985a0b59f5e181c4__section_nts_j2p_spb"/>

## Leveraging SAP Open Connectors for SAP Datasphere Connectivity

You can use the broad SAP Open Connectors connectivity available from SAP Business Technology Platform directly within your SAP Datasphere space.

> ### Note:  
> Using SAP Open Connectors may incur additional charges. You can review your usage in your SAP BTP cockpit.

With SAP Open Connectors, \(API\) hubs provide uniform APIs to access a collection of resources enabling one-to-many API access to multiple API providers. With integrating SAP Open Connectors SAP Datasphere gets access to third-party cloud applications that are available with SAP Open Connectors hub categories. Each hub category contains connectors each representing a pre-built API integration that enables a connection into a specific API Provider endpoint, for example Salesforce, Snowflake, or Microsoft SharePoint. For any connector, connector instances represent a single authenticated connection between SAP and an account at the API provider.

SAP Datasphere supports the following SAP Open Connectors hub categories:

-   CRM

-   DB

-   General

-   Marketing

-   Social

-   Documents


> ### Note:  
> -   For information about SAP Open Connectors availability in data centers, see SAP Note [2903776](https://me.sap.com/notes/2903776).
> 
> -   Some SAP Open Connectors types might not work in case the API hasn't been fully implemented. We recommend to check the connector on SAP Open Connectors side first before using it in SAP Datasphere. For more information, see [Working with Connectors](https://help.openconnectors.ext.hana.ondemand.com/home/working-with-elements) in the SAP Open Connectors documentation.
> 
> -   For sources which SAP Datasphere natively supports with dedicated connection types, such as Amazon S3 or Microsoft SQL Server, use the corresponding SAP Datasphere connection type. We do not recommend using SAP Open Connectors connectivity in this case.
> 
> -   Input parameters are not supported for data flows. For resources with mandatory parameters the parameters have to be replaced in SAP Open Connectors, or the respective connector has to be cloned and adjusted to work without any mandatory parameter. For more information, see Setup Configuration and Parameters \(for custom connectors\) in the SAP Open Connectors documentation.



<a name="loio9bfe7db51216449d985a0b59f5e181c4__section_j1b_byq_spb"/>

## Prerequisites

See: [Prepare Connectivity to SAP Open Connectors](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/fb1aa1107f40429888a633bf940f4ad4.html "Integrate SAP Open Connectors with SAP Datasphere to be able to connect to third party data sources powered by SAP Open Connectors. ") :arrow_upper_right:



<a name="loio9bfe7db51216449d985a0b59f5e181c4__OpenConnectors_usage"/>

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
</table>



<a name="loio9bfe7db51216449d985a0b59f5e181c4__section_nrb_hcc_x4b"/>

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

*Open Connectors Instance* 

</td>
<td valign="top">

Select the instance to which you want to connect. 

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
</table>

