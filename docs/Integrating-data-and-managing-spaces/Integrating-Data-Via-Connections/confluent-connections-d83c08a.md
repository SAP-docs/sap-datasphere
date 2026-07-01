<!-- loiod83c08ad4eaf49dba9602b1d51c07a52 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Confluent Connections

Use the connection to connect to Apache Kafka hosted on either the Confluent Platform or Confluent Cloud. The connection type has two endpoints: the Kafka brokers and the Schema Registry.



This topic contains the following sections:

-   [Supported Features](confluent-connections-d83c08a.md#loiod83c08ad4eaf49dba9602b1d51c07a52__Confluent_usage)
-   [Prerequisites](confluent-connections-d83c08a.md#loiod83c08ad4eaf49dba9602b1d51c07a52__Confluent_prerequisites)
-   [Configuring Connection Properties For Confluent Platform](confluent-connections-d83c08a.md#loioa5d1e1d2885f4a69ae3cc5049eb0cabf)
-   [Configuring Connection Properties For Confluent Cloud](confluent-connections-d83c08a.md#loio8cd75f509baf41bdb859fd2efa045c84)



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

You can use the connection to add source and target objects to a replication flow \(see [Select Source and Target Connections for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/STABI/en-US/10891192186c4920b08939a7b46adc79.html "Select the source connection you want to read data from and the target connection you want to replicate data to.") :arrow_upper_right:\).

</td>
</tr>
</table>



<a name="loiod83c08ad4eaf49dba9602b1d51c07a52__Confluent_prerequisites"/>

## Prerequisites

Before you can use the connection for replication flows, the following is required:

-   The connection requires Confluent Schema Registry as additional endpoint. Schema Registry is a service that centrally stores data schemas for Kafka messages to ensure data consistency and compatibility as schemas evolve.

    For more information, see the *Confluent* documentation:

    -   [Schema Registry for Confluent Platform](https://docs.confluent.io/platform/current/schema-registry/index.html)
    -   [Schema Registry for Confluent Cloud](https://docs.confluent.io/cloud/current/sr/sr-overview.html)

-   A Cloud Connector configuration to connect to the Kafka brokers and to the Schema Registry is required in the following cases:

    -   Your Confluent Platform is on-premise.
    -   For Confluent Cloud: If you want to prevent your data from being routed publicly through the internet, you can use Cloud Connector as a TLS tunnel between the customer virtual private network and SAP Datasphere to privately route the data.

    Two service endpoints and their corresponding Cloud Connector system mappings are required:

    -   Bootstrap server and all internal Kafka broker endpoints \(via TCP protocol\) - used for connecting to the cluster and data replication \(read and write\)
    -   Service Registry endpoint \(via HTTPS protocol\) - used for managing schemas in Confluent

    > ### Note:  
    > Separate Cloud Connector instances might be used for the two endpoints. The Schema Registry might be used in one Cloud Connector location while connecting to the Kafka brokers happens in another location.

    When configuring Cloud Connector for the Kafka brokers, ensure that you create separate system mappings for the bootstrap server address and for each internal Kafka broker address. Pay particular attention to the following settings:

    -   *Back-end Type*: Non-SAP System

    -   *Protocol*: TCP

    -   *Internal Host*: bootstrap server address or Kafka broker address
    -   *Port or Port Range*: port for bootstrap server address or Kafka broker address
    -   *Virtual Host*: can be arbitrary
    -   *Virtual Port*: can be arbitrary
    -   *Check Internal Host*: deselected

    > ### Note:  
    > To retrieve all broker addresses for a bootstrap server, you can use external client tools such as the kcat \(formerly kafkacat\) command-line utility \(see [Configure kcat to Authenticate to Confluent Cloud](https://docs.confluent.io/platform/current/tools/kafkacat-usage.html#configure-kcat-to-authenticate-to-ccloud) in the *Confluent* documentation\) or use programmatic clients implementing the Apache Kafka Client API \(see [Admin Client API](https://docs.confluent.io/kafka/kafka-apis.html#admin-client-api) in the *Confluent* documentation\).

    When configuring Cloud Connector for Schema Registry, ensure you create the system mapping with the following settings:

    -   *Back-end Type*: Non-SAP System

    -   *Protocol*: HTTPS

    -   *Internal Host*: schema Registry address
    -   *Port or Port Range*: port for the schema registry
    -   *Virtual Host*: can be arbitrary
    -   *Virtual Port*: can be arbitrary
    -   *Allow Principal Propagation*: deselected

    -   *Host in Request Header*: Use Virtual Host

    -   *Check Internal Host*: deselected

    For more information, see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:.


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

> ### Note:  
> We recommend to provide the bootstrap server address only. Internal broker addresses will be resolved during runtime.



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
> To select another location ID than the default location, *Connection* privilege with *Read* permission is required.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Virtual Destination* 

</td>
<td valign="top">

Select how you want to specify the virtual destination. 

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

> ### Note:  
> We recommend to enter the bootstrap server host. Internal brokers will be resolved during runtime.



</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Port* 

</td>
<td valign="top">

Enter the virtual port that you defined during Cloud Connector configuration. 

> ### Note:  
> We recommend to enter the bootstrap server port. Internal brokers will be resolved during runtime.



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
    > We recommend that you configure Schema Registry to use HTTPS for secure communication, because the basic protocol passes user name and password in plain text.

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

Set the property to *true* if your platform is on-premise. The default is *false*.

> ### Note:  
> Since Schema Registry might be used in another location than the Kafka brokers, you have to enter the Cloud Connector properties for Schema Registry separately from the properties for the Kafka brokers.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

Select the location ID for the Cloud Connector instance that is set up for connecting to the Schema Registry. 

> ### Note:  
> To select another location ID than the default location, *Connection* privilege with *Read* permission is required.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Virtual Destination* 

</td>
<td valign="top">

Select how you want to specify the virtual destination. 

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

> ### Note:  
> We recommend to provide the bootstrap server address only. Internal broker addresses will be resolved during runtime.



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

Set the property to *true* if you want to use replication flows and your Confluent Cloud-managed Kafka brokers do not have a public endpoint. The default is *false*.

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

Select the location ID for the Cloud Connector instance that is set up for connecting to the Kafka brokers.

> ### Note:  
> To select another location ID than the default location, *Connection* privilege with *Read* permission is required.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Virtual Destination* 

</td>
<td valign="top">

Select how you want to specify the virtual destination. 

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

> ### Note:  
> We recommend to enter the bootstrap server host. Internal brokers will be resolved during runtime.



</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Port* 

</td>
<td valign="top">

Enter the virtual port that you defined during Cloud Connector configuration.

> ### Note:  
> We recommend to enter the bootstrap server port. Internal brokers will be resolved during runtime.



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

Enter the Confluent Cloud API secret. 

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

> ### Note:  
> When using Cloud Connector for private connectivity, you must use TLS for the Kafka brokers.



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
    > We recommend that you configure Schema Registry to use HTTPS for secure communication, because the basic protocol passes user name and password in plain text.




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

Set the property to *true* if you want to use replication flows and your Schema Registry does not have a public endpoint. The default is *false*.

> ### Note:  
> Since Schema Registry might be used in another location than the Kafka brokers, you have to enter the Cloud Connector properties for Schema Registry separately from the properties for the Kafka brokers.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

Select the location ID for the Cloud Connector instance that is set up for connecting to the Schema Registry.

> ### Note:  
> To select another location ID than the default location, *Connection* privilege with *Read* permission is required.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Virtual Destination* 

</td>
<td valign="top">

Select how you want to specify the virtual destination. 

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

