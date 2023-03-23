<!-- loio1caba954bc604e00bf8e82e383a46368 -->

# SAP BW∕4HANA Model Transfer

Use the connection to import analytic queries from SAP BW∕4HANA with their Composite Providers and InfoObjects.



<a name="loio1caba954bc604e00bf8e82e383a46368__section_j1b_byq_spb"/>

## Prerequisites

See: [Preparing SAP BW/4HANA Model Transfer Connectivity](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/962de2f99d234967b8b10541599f00c6.html "Accessing SAP BW/4HANA meta data and importing models into SAP Datasphere with a SAP BW/4HANA Model Transfer connection requires two protocols (or endpoints): Http and SAP HANA Smart Data Integration based on the SAP HANA adapter.") :arrow_upper_right:



## Using the Connection

The connection type supports the model import feature.

For more information, see [Importing SAP BW∕4HANA Models](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/internal/en-US/a3d4a2f91bea4810ba8839ff73577dac.html "You can import existing analytic queries from SAP BW∕4HANA into SAP Datasphere in order to build new models on top of them or enhance them.") :arrow_upper_right:.



<a name="loio1caba954bc604e00bf8e82e383a46368__section_nrb_hcc_x4b"/>

## Configuring Connection Properties



### Live Data Connection \(Tunnel\)


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

*Name*



</td>
<td valign="top">

Select the relevant live data connection of type tunnel. 

A live data connection of type tunnel is required for a secure connection to SAP BW/4HANA with Cloud Connector and for accessing SAP BW/4HANA metadata with http requests. With Cloud Connector, the SAP BW/4HANA system doesn't need to be exposed to the internet in order to make the system accessible.

If the required connection is not available for selection, you or an administrator need to create the tunnel connection before you can create the SAP BW/4HANA Model Transfer connection.

For more information, see [Create Live Data Connection of Type Tunnel](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/5d02f1103dd742aab5c0fc930debe51b.html "To securely connect and make http requests to SAP BW∕4HANA, you need to connect via Cloud Connector. This requires that you create a live data connection of type tunnel to the SAP BW∕4HANA system.") :arrow_upper_right:.



</td>
</tr>
</table>



### SAP HANA SQL Access


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

Displays the SAP HANA host retrieved from SAP BW∕4HANA via the selected tunnel connection.



</td>
</tr>
<tr>
<td valign="top">

*Port*



</td>
<td valign="top">

Displays the SAP HANA port retrieved from SAP BW∕4HANA via the selected tunnel connection.



</td>
</tr>
</table>

> ### Note:  
> If required in exceptional cases, you can change the value in the *Host* and *Port* fields.
> 
> In some use cases, for example when SAP BW∕4HANA is hosted by a third-party cloud provider, host and port can't be retrieved and you must enter it manually.
> 
> In case of an error when retrieving host and port, for example because of missing authorizations, because of any of the services necessary for the tunnel connection not being active, or because of any other issue with the tunnel connection, you can enter host and port manually to be able to proceed with connection creation before validating and fixing the tunnel connection. We recommend, however, to validate and fix the tunnel connection first.
> 
> You can reset the value for the *Host* and *Port* fields to the values retrieved from SAP BW∕4HANA by clicking *Reset*.



### SAP HANA Security


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

*Enable SSL Encryption* 



</td>
<td valign="top">

Specify whether to enable SSL encryption on connections to the remote SAP HANA database of the SAP BW/4HANA system. The default value is *true*. 

To use SSL encryption with the remote SAP HANA database, the Data Provisioning Agent must already be correctly configured for SSL support.



</td>
</tr>
<tr>
<td valign="top">

*Validate Server Certificate*



</td>
<td valign="top">

Specify whether to validate the certificate of the remote SAP HANA server. The default value is *true*.

> ### Note:  
> A certificate signed by a certificate authority \(CA\) is needed here. If the certificate is self-signed and not CA signed, select *false*.



</td>
</tr>
</table>



### SAP HANA Credentials


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

Enter the SAP HANA database user name \(case sensitive\).

> ### Note:  
> The SAP HANA user needs read privileges for the ABAP schema in the SAP HANA database.



</td>
</tr>
<tr>
<td valign="top">

*Password*



</td>
<td valign="top">

Enter the appropriate corresponding password.



</td>
</tr>
</table>



### Features

To enable *Model Import*, select a Data Provisioning Agent.



<a name="loio1caba954bc604e00bf8e82e383a46368__section_qpx_zk3_2nb"/>

## What happens when you've created the connection

On saving the connection, SAP Datasphere retrieves SAP HANA host and port via the SAP Analytics Cloud tunnel connection.

You can now find your new connection in the list of the available connections for the space and can use it in the Business Builder to import analytic queries from your connected SAP BW∕4HANA system into SAP Datasphere. During the model import alongside other objects we will create and deploy remote tables in the repository. The remote tables can be used in the following places:

-   In the remote table monitor to replicate data.

-   In the view editor of the data builder to build views on top \(by dragging the object in from the repository browser\)

-   In the data flow editor of the data builder to use them as sources \(by dragging the object in from the repository browser\).


> ### Note:  
> In the view or data flow editor in the data builder, SAP BW/4HANA Model Transfer connections with their remote tables are not available as sources in the *Sources* tab of the source tree. Instead, as described above, the remote tables are available from the *Repository* tab.

