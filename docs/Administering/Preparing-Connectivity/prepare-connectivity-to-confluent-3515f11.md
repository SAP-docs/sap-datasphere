<!-- loio3515f11430044e479cc4934cd221e010 -->

# Prepare Connectivity to Confluent

To be able to use a connection to Confluent Platform \(on-premise\) for replication flows, certain preparations have to be made.



<a name="loio3515f11430044e479cc4934cd221e010__section_ixm_3zr_51c"/>

## Replication Flows

Before you can use the connection for replication flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to Confluent Platform \(Kafka brokers\) and to the Schema Registry.

    > ### Note:  
    > Separate Cloud Connector instances might be used for the two endpoints. The Schema Registry might be used in one Cloud Connector location is while connecting to the Kafka brokers happens in another location.


