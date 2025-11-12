<!-- loio8b132061d4e149d9a16b3576dda1f613 -->

# Amazon Redshift Connections

Use an *Amazon Redshift* connection to access data from Amazon Redshift 8.x databases. 

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

This topic contains the following sections:

-   -   [Supported Features](amazon-redshift-connections-8b13206.md#loio8b132061d4e149d9a16b3576dda1f613__Redshift_usage)
-   [Configuring Connection Properties](amazon-redshift-connections-8b13206.md#loio8b132061d4e149d9a16b3576dda1f613__Redshift_connection_properties)



<a name="loio8b132061d4e149d9a16b3576dda1f613__section_j1b_byq_spb"/>

## Prerequisites

See: [Prepare Connectivity to Amazon Redshift](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/519b2dbc588940fb9698745e430c9859.html "To be able to successfully validate and use a connection to an Amazon Redshift database for remote tables or data flows certain preparations have to be made.") :arrow_upper_right:



<a name="loio8b132061d4e149d9a16b3576dda1f613__Redshift_usage"/>

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

For more information, see [Monitoring Remote Tables](../Data-Integration-Monitor/monitoring-remote-tables-4dd95d7.md). 

> ### Note:  
> -   In the view editor of the Data Builder, you can see technical artifacts from the source that you cannot use for modeling. Affected artifacts are tables containing "pkey" or tables from technical schemas pg\_catalog, pg\_internal, and information\_schema, for example. Please ignore these artifacts.



</td>
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



<a name="loio8b132061d4e149d9a16b3576dda1f613__Redshift_connection_properties"/>

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

Enter the host name of the Redshift server. 

</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Displays the default port 5439. You can overwrite the port, if required. 

</td>
</tr>
<tr>
<td valign="top">

*Database Name* 

</td>
<td valign="top">

Enter the name of the database to which you want to connect. 

</td>
</tr>
</table>



### Security


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

*Use SSL* 

</td>
<td valign="top">

Select the SSL certificate verification mode to use when connecting. The default is *false*. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use SSL* = *true*\] *Validate Server Certificate*

</td>
<td valign="top">

Select if the server certficate should be validated \(*true*\) or not \(*false*\). The default is *false*. 

If you select *true*, then the host name in the certificate must match the host name specified in the *Host* field.

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

Enter the name of the Redshift user that has privileges to connect to the database. 

</td>
</tr>
<tr>
<td valign="top">

*Password* 

</td>
<td valign="top">

Enter the password of the Redshift user. 

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

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
</table>

