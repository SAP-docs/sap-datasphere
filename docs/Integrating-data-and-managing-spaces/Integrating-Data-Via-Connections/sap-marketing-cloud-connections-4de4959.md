<!-- loio4de4959620c24d12a53a3cc357d3e003 -->

# SAP Marketing Cloud Connections

Use an *SAP Marketing Cloud* connection to access data from SAP Marketing Cloud via its OData-based APIs for data integration and SAP HANA Smart Data Integration.

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

This topic contains the following sections:

-   [Supported Features](sap-marketing-cloud-connections-4de4959.md#loio4de4959620c24d12a53a3cc357d3e003__Marketing_Cloud_usage)
-   [Prerequisites](sap-marketing-cloud-connections-4de4959.md#loio4de4959620c24d12a53a3cc357d3e003__Marketing_Cloud_prerequisites)
-   [Configuring Connection Properties](sap-marketing-cloud-connections-4de4959.md#loio4de4959620c24d12a53a3cc357d3e003__Marketing_Cloud_connection_properties)



<a name="loio4de4959620c24d12a53a3cc357d3e003__Marketing_Cloud_prerequisites"/>

## Prerequisites



### Remote Tables

Before you can use the connection for remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the CloudDataIntegrationAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f1a39d1a763e48c8872f45c110a5a4e2.html "Most connection types supporting remote tables use SAP HANA Smart Data Integration (SDI) and its Data Provisioning Agent. Before using the connection, the agent requires an appropriate setup.") :arrow_upper_right:.

-   A communication arrangement has been created for communication scenario `SAP_COM_0531` in the source system. 

    For more information, see [Integrating CDI](https://help.sap.com/viewer/e0cd7c1ecf3d4f2f9feb46ec1c5b68fb/latest/en-US/4a006b43551d4cb5aed6399c0ace6b98.html) in the *SAP Marketing Cloud* documentation.




### Data Flows

Before you can use the connection for data flows, the following is required:

-   A communication arrangement has been created for communication scenario `SAP_COM_0531` in the source system. 

    For more information, see [Integrating CDI](https://help.sap.com/viewer/e0cd7c1ecf3d4f2f9feb46ec1c5b68fb/latest/en-US/4a006b43551d4cb5aed6399c0ace6b98.html) in the *SAP Marketing Cloud* documentation.




<a name="loio4de4959620c24d12a53a3cc357d3e003__Marketing_Cloud_usage"/>

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

Data Flows

</td>
<td valign="top">

You can use the connection to add source objects to a data flow.

</td>
</tr>
</table>



<a name="loio4de4959620c24d12a53a3cc357d3e003__Marketing_Cloud_connection_properties"/>

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

*URL*

</td>
<td valign="top">

Enter the URL with the following syntax: <code><i class="varname">&lt;protocol&gt;</i>://<i class="varname">&lt;host&gt;</i><i class="varname">&lt;service path&gt;</i></code> 

Protocol: HTTP or HTTPS. The default value is HTTPS.

Host: Host for accessing the cloud OData service

Service path: Relative path \(without host and port\) to the Cloud Data Integration service endpoint \(where the CDI provider service is running at the cloud provider side\). The value must start with a forward slash \( / \).

</td>
</tr>
<tr>
<td valign="top">

*Root Path*

</td>
<td valign="top">

\[optional\] Enter the root path name to restrict browsing to a certain CDI namespace or provider.

</td>
</tr>
</table>



### Credentials \(User Name and Password\)


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

Enter the user name that the application must use for authentication. 

</td>
</tr>
<tr>
<td valign="top">

*Password*  

</td>
<td valign="top">

Enter the password for authentication. 

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

