<!-- loio6df55db4028842c1b1866e709ffef456 -->

# Using Apache Kafka As the Target

If you use Apache Kafka as the target for your replication flow, you need to consider the following additional specifics and conditions.

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).

You can only replicate to **new** target objects \(Kafka topics\).

You can use the following **formats**:

-   Apache Avro

-   JSON


You can choose from the following **compression types**:

-   No Compression

-   Gzip

-   Snappy

-   LZ4

-   Zstandard


The **target container** is automatically set to "/" and cannot be changed.

You can **rename** target objects \(Kafka topics\). The following conditions apply:

-   The new name may consist of the following characters: small latin letters \(a-z\), capital latin letters \(A-Z\), numbers \(0-9\), period \(.\), underscore \(\_\), hyphen \(-\).

-   The maximum length for the new name is 249 characters.


