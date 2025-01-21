<!-- loio1992c6b7154c4bc080d83c8977382ff4 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Apache Kafka Connections

Use the connection to connect to an Apache Kafka cluster.



This topic contains the following sections:

-   [Supported Features](apache-kafka-connections-1992c6b.md#loio1992c6b7154c4bc080d83c8977382ff4__Kafka_usage)
-   [Configuring Connection Properties](apache-kafka-connections-1992c6b.md#loio1992c6b7154c4bc080d83c8977382ff4__connection_properties)

For information about the required prerequisites, see [Prepare Connectivity to Apache Kafka](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/1483cebf45a242aca94236240d94d2c7.html "To be able to successfully validate and use a connection to Apache Kafka (on-premise) for replication flows, certain preparations have to be made.") :arrow_upper_right:.



<a name="loio1992c6b7154c4bc080d83c8977382ff4__Kafka_usage"/>

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

You can use the connection to add target objects to a replication flow.

For more information, see [Apache Kafka Targets](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/6df55db4028842c1b1866e709ffef456.html "If you use Apache Kafka as the target for your replication flow, you need to consider the following additional specifics and conditions.") :arrow_upper_right:.

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Premium Outbound Integration](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/4e9c6acb5d6a43fa9a6471837399e71c.html "To use a non-SAP target in a replication flow, you need premium outbound integration.") :arrow_upper_right: and [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).



</td>
</tr>
</table>



<a name="loio1992c6b7154c4bc080d83c8977382ff4__connection_properties"/>

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

*Kafka Brokers* 

</td>
<td valign="top">

Enter a comma-separated list of brokers in the format <code><i class="varname">&lt;host&gt;</i>:<i class="varname">&lt;port&gt;</i></code>. 

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

\[optional\] Set to *true* if your source is an on-premise source and you want to use the connection for replication flows. The default is *false*. 

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

\[optional\] Select *Derive Virtual Host and Port from Connection Details* or *Enter Virtual Host and Port in Separate Fields*. 

If host and port entered in the connection details match the virtual host and port from the Cloud Connector configuration, you can select *Derive Virtual Host and Port from Connection Details* and don't need to enter the values manually.

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

Select the authentication type to use to connect to the Kafka brokers. 

You can select:

-   *No Authentication*
-   *User Name And Password*

    > ### Note:  
    > For basic authentication with user name and password, we recommend to use TLS encryption to ensure secure communication.

-   *Salted Challenge Response Authentication Mechanism \(256\)*
-   *Salted Challenge Response Authentication Mechanism \(512\)* \(default\)
-   *Kerberos with Username and Password*
-   *Kerberos with Keytab File*



</td>
</tr>
<tr>
<td valign="top">

*SASL Authentication Type* 

</td>
<td valign="top">

\[read-only\] Displays the Simple Authentication and Security Layer \(SASL\) authentication mechanism to use depending on your selection for *Authentication Type*. 

The mechanisms are:

-   *PLAIN*: plaintext password defined in RFC 4616.
-   *SCRAM-256*: Salted Challenge Response Authentication Mechanism \(SCRAM\) password-based challenge-response authentication from a user to a server -based on SHA 256.
-   *SCRAM-512*: SCRAM password-based challenge-response authentication from a user to a server - based on SHA 512.
-   *GSSAPI*: Generic Security Service Application Program Interface authentication applicable for Kerberos V5.



</td>
</tr>
</table>



### Kerberos

If *Authentication Type* = *Kerberos with Username and Password* or *Kerberos with Keytab File*:


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

*Kafka Kerberos Service Name*

</td>
<td valign="top">

Enter the name of the Kerberos service used by the Kafka broker.

</td>
</tr>
<tr>
<td valign="top">

*Kafka Kerberos Realm*

</td>
<td valign="top">

Enter the realm defined for the Kafka Kerberos broker.

</td>
</tr>
<tr>
<td valign="top">

*Kafka Kerberos Config*  

</td>
<td valign="top">

Upload the content of the krb5.conf configuration file. 

Choose <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location.

Once uploaded, you can check the configuration file by clicking the <span class="SAP-icons-V5"></span> \(inspection\) button.

</td>
</tr>
</table>



### Credentials \(SCRAM\)

If *Authentication Type* = *Salted Challenge Response Authentication Mechanism \(512\)* or *Salted Challenge Response Authentication Mechanism \(256\)*:


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

*Kafka SASL User Name* 

</td>
<td valign="top">

Enter the user name that is used for Kafka SASL SCRAM authentication. 

</td>
</tr>
<tr>
<td valign="top">

*Kafka SASL Password* 

</td>
<td valign="top">

Enter the Kafka SASL SCRAM connection password. 

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

Enter the user name that is used for Kafka SASL PLAIN authentication. 

</td>
</tr>
<tr>
<td valign="top">

*Password* 

</td>
<td valign="top">

Enter the Kafka SASL PLAIN connection password. 

</td>
</tr>
</table>



### Credentials \(Kerberos with Keytab File\)

If *Authentication Type* = *Kerberos with Keytab File*:


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

Enter the name of the user that is used to connect to the Kerberos service. 

</td>
</tr>
<tr>
<td valign="top">

*Keytab File* 

</td>
<td valign="top">

Upload the content of the keytab file. 

Choose <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location.

Once uploaded, you can check the keytab file by clicking the <span class="SAP-icons-V5"></span> \(inspection\) button.

</td>
</tr>
</table>



### Credentials \(Kerberos with User Name And Password\)

If *Authentication Type* = *Kerberos with Username and Password*:


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

Enter the name of the user that is used to connect to the Kerberos service. 

</td>
</tr>
<tr>
<td valign="top">

*Password* 

</td>
<td valign="top">

Enter the Kerberos password. 

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

*Use TLS*

</td>
<td valign="top">

Select *true* \(default\) to use TLS encryption.

</td>
</tr>
<tr>
<td valign="top">

*Validate Server Certificate*

</td>
<td valign="top">

Select *true* \(default\) to validate the TLS server certificate.

</td>
</tr>
<tr>
<td valign="top">

\[if *Use TLS* = *true* and *Validate Server Certificate* = *true*:\]*Use mTLS*

</td>
<td valign="top">

Select *true* to use mutual authentication with validating both client and server certificates. The default is *false*.

</td>
</tr>
<tr>
<td valign="top">

\[if *Use mTLS* = *true*:\] *Client Key*

</td>
<td valign="top">

Upload the client key. 

Choose <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location.

> ### Note:  
> The supported filename extensions for the key are .pem \(privacy-enhanced mail\) and .key.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use mTLS* = *true*:\] *Client Certificate*

</td>
<td valign="top">

Upload the client certificate. 

Choose <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location.

> ### Note:  
> The supported filename extensions for the certificate are .pem \(privacy-enhanced mail\) and .crt.



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

*Replication Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
</table>

