<!-- loio3515f11430044e479cc4934cd221e010 -->

# Prepare Connectivity to Confluent

To be able to successfully validate and use a connection to Confluent Platform \(on-premise\) for replication flows, certain preparations have to be made.



<a name="loio3515f11430044e479cc4934cd221e010__section_ixm_3zr_51c"/>

## Replication Flows

Before you can use the connection for replication flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to Confluent Platform \(Kafka brokers\) and to the Schema Registry.

    > ### Note:  
    > Separate Cloud Connector instances might be used for the two endpoints. The Schema Registry might be used in one Cloud Connector location is while connecting to the Kafka brokers happens in another location.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).


**Related Information**  


[Confluent Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/d83c08ad4eaf49dba9602b1d51c07a52.html#loiod83c08ad4eaf49dba9602b1d51c07a52 "Use the connection to connect to Apache Kafka hosted on either the Confluent Platform or Confluent Cloud. The connection type has two endpoints: the Kafka brokers and the Schema Registry.") :arrow_upper_right:

