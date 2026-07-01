<!-- loiod9ead8bb44ac456d99a141b4e3f5e973 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Snowflake Connections

Use the connection to connect to and access data from a Snowflake database.



This topic contains the following sections:

-   [Supported Features](snowflake-connections-d9ead8b.md#loiod9ead8bb44ac456d99a141b4e3f5e973__Snowflake_usage)
-   [Prerequisites](snowflake-connections-d9ead8b.md#loiod9ead8bb44ac456d99a141b4e3f5e973__Snowflake_prerequisites)
-   [Configuring Connection Properties](snowflake-connections-d9ead8b.md#loiod9ead8bb44ac456d99a141b4e3f5e973__Snowflake_connection_properties)



<a name="loiod9ead8bb44ac456d99a141b4e3f5e973__Snowflake_usage"/>

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

Replication Flows

</td>
<td valign="top">

You can use the connection to add source objects to a replication flow \(see [Select Source and Target Connections for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/STABI/en-US/10891192186c4920b08939a7b46adc79.html "Select the source connection you want to read data from and the target connection you want to replicate data to.") :arrow_upper_right:\).

</td>
</tr>
</table>



<a name="loiod9ead8bb44ac456d99a141b4e3f5e973__Snowflake_prerequisites"/>

## Prerequisites

Before you can use the connection for replication flows, the following is required:

-   The connection requires a Snowflake warehouse - a cluster of compute resources in Snowflake. To successfully validate the connection, ensure that either the Snowflake user has a default warehouse assigned in the user profile, or explicitly specify a warehouse in the connection details \(which overrides the default warehouse\).

    For more information, see [Virtual warehouses](https://docs.snowflake.com/en/user-guide/warehouses) in the *Snowflake* documentation.

-   The connection type supports key pair authentication. For information about generating the private and public keys, see [Key-pair authentication and key-pair rotation](https://docs.snowflake.com/en/user-guide/key-pair-auth) in the *Snowflake* documentation.
-   If you want to prevent your data from being routed publicly through the internet, you can use Cloud Connector as a TLS tunnel between the customer virtual private network and SAP Datasphere to privately route the data.

    When configuring Cloud Connector, ensure you have created the system mapping with the following settings:

    -   *Back-end Type*: Non-SAP System

    -   *Protocol*: HTTPS

    -   *Allow Principal Propagation*: deselected

    -   *Host in Request Header*: Use Internal Host


    For more information, see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:.




<a name="loiod9ead8bb44ac456d99a141b4e3f5e973__Snowflake_connection_properties"/>

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

Enter the host name of the server on which the Snowflake database is running.

> ### Note:  
> GCP regional endpoints are not supported.



</td>
</tr>
<tr>
<td valign="top">

*Port*  

</td>
<td valign="top">

Enter port number of the Snowflake database server. 

> ### Note:  
> The port number can vary depending on whether SSL is used or not.



</td>
</tr>
<tr>
<td valign="top">

*Database Name*  

</td>
<td valign="top">

Enter the name of the Snowflake database to which you want to connect. 

</td>
</tr>
<tr>
<td valign="top">

*Warehouse*  

</td>
<td valign="top">

\[optional\] By default, the warehouse assigned to the Snowflake user's profile is used for the connection. Enter another Snowflake warehouse name if you want to override the default warehouse. 

> ### Note:  
> The connection validation fails if you don't enter a warehouse and the user doesn't have a default warehouse assigned.



</td>
</tr>
</table>



### Cloud Connector

> ### Note:  
> Cloud Connector is not required if your Snowflake database is available on the public internet.


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

\[optional\] Set to *true* if you want to use replication flows to replicate data from a Snowflake database that does not have a public endpoint. The default is *false*. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

\[optional\] Select a location ID. 

> ### Note:  
> To select another location ID than the default location, *Connection* privilege with *Read* permission is required.



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

Displays *Key Pair*. 

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

Enter the user who is accessing the Snowflake server. 

</td>
</tr>
<tr>
<td valign="top">

*Private Key*  

</td>
<td valign="top">

Enter the private key used for key-pair authentication. The private key must be in PKCS\#8 format, and the server must know the user public key. 

Choose <span class="SAP-icons-V5"></span> \(Browse\) and select the file.

</td>
</tr>
<tr>
<td valign="top">

*Passphrase*  

</td>
<td valign="top">

\[optional\] When using an encrypted private key, enter the passphrase needed to decrypt the private key. 

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

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties. If your source is an on-premise source, make sure you have maintained the properties in the *Cloud Connector* section. 

</td>
</tr>
</table>

