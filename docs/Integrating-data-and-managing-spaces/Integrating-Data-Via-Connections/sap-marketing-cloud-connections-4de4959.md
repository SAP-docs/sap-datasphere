<!-- loio4de4959620c24d12a53a3cc357d3e003 -->

# SAP Marketing Cloud Connections

Use an *SAP Marketing Cloud* connection to access data from SAP Marketing Cloud via its OData-based APIs for data integration and SAP HANA Smart Data Integration.



<a name="loio4de4959620c24d12a53a3cc357d3e003__section_j1b_byq_spb"/>

## Prerequisites

See: [Prepare Connectivity to SAP Marketing Cloud](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/f5e0c06fdc834c62a10eeb19d9a79bab.html "To be able to successfully validate and use a connection to SAP Marketing Cloud for remote tables or data flows, certain preparations have to be made.") :arrow_upper_right:



<a name="loio4de4959620c24d12a53a3cc357d3e003__CDI_usage"/>

## Using the Connection

The connection type supports the remote table as well as the data flow feature.

Supported data access methods for remote tables:

-   Remote
-   Replication \(snapshot\)
-   Replication \(real-time\)

For more information, see [Replicating Data and Monitoring Remote Tables](../Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md). 



<a name="loio4de4959620c24d12a53a3cc357d3e003__section_nrb_hcc_x4b"/>

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

To enable *Remote Tables*, select a Data Provisioning Agent.

*Data Flows* are enabled without the need to set any additional connection properties.

