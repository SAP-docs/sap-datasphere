<!-- loioeeae3aca6d0040149f7b1e658c434f15 -->

# Generic JDBC Connections

Use a *Generic JDBC* connection to access data from tables and views in any supported data source for which a JDBC driver is available.

You can use this connection type to connect to most databases for which SAP Datasphere does not already provide a connection type. In general, the connection type supports most databases that have SQL-based data types and functions, and a JDBC driver. For latest information about supported data sources and versions, see the [SAP HANA smart data integration Product Availability Matrix \(PAM\)](https://support.sap.com/content/dam/launchpad/en_us/pam/pam-essentials/TIP/PAM_HANA_SDI_2_0.pdf).

> ### Note:  
> For information about unsupported data sources, see SAP Note [3130999](https://me.sap.com/notes/3130999).

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).



<a name="loioeeae3aca6d0040149f7b1e658c434f15__section_j1b_byq_spb"/>

## Prerequisites

See: [Prepare Connectivity for Generic JDBC](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/648fabfc94ad4da7853ef9a4d284aeac.html "To be able to successfully validate and use a Generic JDBC connection for remote tables certain preparations have to be made.") :arrow_upper_right:



<a name="loioeeae3aca6d0040149f7b1e658c434f15__JDBC_usage"/>

## Using the Connection

The connection type supports the remote table feature.

Supported data access methods for remote tables:

-   Remote
-   Replication \(snapshot\)

For more information, see [Replicating Data and Monitoring Remote Tables](../Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md). 



<a name="loioeeae3aca6d0040149f7b1e658c434f15__section_nrb_hcc_x4b"/>

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

*JDBC Driver Class* 

</td>
<td valign="top">

Enter the JDBC driver class for the database you are using. 

</td>
</tr>
<tr>
<td valign="top">

*JDBC URL*

</td>
<td valign="top">

Enter the URL for the JDBC driver.

> ### Note:  
> The JDBC URL is stored as plain text and is not stored in encrypted form. It is visible when editing the connection or when accessing the remote source with a database analysis user. Therefore, do not provide any sensitive information like passwords in the URL.



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

Enter the database user name.

</td>
</tr>
<tr>
<td valign="top">

*Password*

</td>
<td valign="top">

Enter the password for the database user.

</td>
</tr>
</table>



### Features

To enable *Remote Tables*, select a Data Provisioning Agent.

