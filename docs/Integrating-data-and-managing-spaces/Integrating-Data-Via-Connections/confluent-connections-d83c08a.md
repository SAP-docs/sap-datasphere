<!-- loiod83c08ad4eaf49dba9602b1d51c07a52 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Confluent Connections

Use the connection to connect to Apache Kafka hosted on either the Confluent Platform or Confluent Cloud. The connection type has two endpoints: the Kafka brokers and the Schema Registry.



This topic contains the following sections:

-   [Supported Features](confluent-connections-d83c08a.md#loiod83c08ad4eaf49dba9602b1d51c07a52__Confluent_usage)
-   [Configuring Connection Properties For Confluent Platform](confluent-connections-d83c08a.md#loioa5d1e1d2885f4a69ae3cc5049eb0cabf)
-   [Configuring Connection Properties For Confluent Cloud](confluent-connections-d83c08a.md#loio8cd75f509baf41bdb859fd2efa045c84)

For information about the required prerequisites, see [Prepare Connectivity to Confluent](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/3515f11430044e479cc4934cd221e010.html "To be able to successfully validate and use a connection to Confluent Platform (on-premise) for replication flows, certain preparations have to be made.") :arrow_upper_right:.



<a name="loiod83c08ad4eaf49dba9602b1d51c07a52__Confluent_usage"/>

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

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).

With Schema Registry, replication flows use a schema reference when serializing a Kafka topic message instead of providing the schema definition in every message. In the target settings of the replication flow configuration, you can decide to use Schema Registry.

For more information, see [Using Confluent Kafka As the Target](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/74b3c95464f246aa8c3fd510661daa6d.html "If you use Confluent Kafka as the target for your replication flow, you need to consider the following additional specifics and conditions.") :arrow_upper_right:.

</td>
</tr>
</table>

<a name="loioa5d1e1d2885f4a69ae3cc5049eb0cabf"/>

<!-- loioa5d1e1d2885f4a69ae3cc5049eb0cabf -->

## Configuring Connection Properties For Confluent Platform





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

*System Type* 

</td>
<td valign="top">

Select *Confluent Platform* \(default\). 

</td>
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

Set the property to *true* if your platform is on-premise. The default is *false*.

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

Select the location ID for the Cloud Connector instance that is set up for connecting to the Kafka brokers.

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



### Schema Registry


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

Enter the URL of the Schema Registry service. The required format is <code><i class="varname">&lt;protocol&gt;</i>://<i class="varname">&lt;host&gt;</i>:<i class="varname">&lt;port&gt;</i></code>. 

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type* 

</td>
<td valign="top">

Select the authentication type to be used to connect to the Schema Registry.

You can select:

-   *User Name And Password* \(default\)

    > ### Note:  
    > We recommended that you configure Schema Registry to use HTTPS for secure communication, because the basic protocol passes user name and password in plain text.

-   *No Authentication*



</td>
</tr>
<tr>
<td valign="top">

*User Name* 

</td>
<td valign="top">

\[if *Authentication Type* = *User Name And Password*\] Enter the name of the user used to connect to the Schema Registry. 

</td>
</tr>
<tr>
<td valign="top">

*Password* 

</td>
<td valign="top">

\[if *Authentication Type* = *User Name And Password*\] Enter the password. 

</td>
</tr>
</table>



### Cloud Connector For Schema Registry


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

Select the location ID for the Cloud Connector instance that is set up for connecting to the Schema Registry.

> ### Note:  
> Since Schema Registry might be used in another location than the Kafka brokers, you have to enter the Cloud Connector properties for Schema Registry separately from the properties for the Kafka brokers.



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



### Security For Schema Registry


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

<a name="loio8cd75f509baf41bdb859fd2efa045c84"/>

<!-- loio8cd75f509baf41bdb859fd2efa045c84 -->

## Configuring Connection Properties For Confluent Cloud





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

*System Type* 

</td>
<td valign="top">

Select *Confluent Cloud*. 

</td>
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

\[read-only\] Displays *API Key and Secrect* for authentication based on API keys. 

</td>
</tr>
</table>



### Credentials \(API Key and Secret\)


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

*API Key* 

</td>
<td valign="top">

Enter the Confluent Cloud API key that is used to control access to Confluent Cloud. 

</td>
</tr>
<tr>
<td valign="top">

*Secret* 

</td>
<td valign="top">

Enter the Confluent Cloud API secrect. 

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
</table>



### Schema Registry


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

Enter the URL of the Schema Registry service. The required format is <code><i class="varname">&lt;protocol&gt;</i>://<i class="varname">&lt;host&gt;</i>:<i class="varname">&lt;port&gt;</i></code>. 

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type* 

</td>
<td valign="top">

Select the authentication type to be used to connect to the Schema Registry.

You must select:

-   *User Name And Password* \(default\)

    > ### Note:  
    > We recommended that you configure Schema Registry to use HTTPS for secure communication, because the basic protocol passes user name and password in plain text.




</td>
</tr>
<tr>
<td valign="top">

*User Name* 

</td>
<td valign="top">

Enter the Confluent Cloud API key that is used to control access to the Schema Registry. 

</td>
</tr>
<tr>
<td valign="top">

*Password* 

</td>
<td valign="top">

Enter the Confluent Cloud API secret. 

</td>
</tr>
</table>



### Security For Schema Registry


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

