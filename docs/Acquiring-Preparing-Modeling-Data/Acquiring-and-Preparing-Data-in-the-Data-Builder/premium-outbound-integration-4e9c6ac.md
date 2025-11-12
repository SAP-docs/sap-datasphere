<!-- loio4e9c6acb5d6a43fa9a6471837399e71c -->

# Premium Outbound Integration

To use a non-SAP target in a replication flow, you need premium outbound integration.



<a name="loio4e9c6acb5d6a43fa9a6471837399e71c__section_c1k_5sd_3cc"/>

## Getting Started

This topic is relevant for you if you want to use one of the following as the target for your replication flow:

-   Amazon Simple Storage Service

-   Google Cloud Storage

-   Microsoft Azure Data Lake Gen2

-   Google BigQuery

-   Apache Kafka

-   Confluent Kafka

-   Secure File Transfer Protocol \(SFTP\)

Before you can create a replication flow for any of these targets, your administrator needs to allocate at least one premium outbound integration block in SAP Datasphere tenant configuration \(in addition to the data integration blocks that you need for any replication flow, irrespective of its target\). For more information about tenant configuration, see [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/33f8ef4ec359409fb75925a68c23ebc3.html "Configure the size of your tenant by specifying resource sizes based on your business needs. Capacity Units (CU) are allocated to obtain storage and compute resources for your tenant.") :arrow_upper_right:.

> ### Example:  
> You want to replicate data into Google BigQuery. You are expecting a data volume of 300 GB for initial load and a change data volume \(delta\) of 60 GB per month. Considering that you need one premium outbound integration block per 20 GB of data to be transferred, you need 18 premium outbound integration blocks \(15 for initial load and 3 for delta load\) for the first month and 3 premium outbound blocks for each subsequent month.

For detailed information about how to estimate the data volume to expect, see also [Replication Flow Blog Series Part 4 - Sizing](https://community.sap.com/t5/technology-blogs-by-sap/replication-flow-blog-series-part-4-sizing/ba-p/13579486) and SAP Note [3470559](https://me.sap.com/notes/3470559).

> ### Note:  
> To avoid interrupting critical integration scenarios, running replication flows will continue running \(and consuming capacity units\) if the assigned number of execution hours or premium outbound integration blocks is exceeded. If you don't want that \(for example if you're just running a replication flow for testing purposes and want to keep costs to a minimum\), make sure that the data volume for your replication flow is small enough.

What exactly you need to do to set up your replication flow depends on the target you're planning to use. For more information, see the documentation for the respective target type:

-   [Cloud Storage Provider Targets](cloud-storage-provider-targets-43d93a2.md)

-   [Google BigQuery Targets](google-bigquery-targets-56d4472.md)

-   [Apache Kafka Targets](apache-kafka-targets-6df55db.md)

-   [Confluent Kafka Targets](confluent-kafka-targets-74b3c95.md)




<a name="loio4e9c6acb5d6a43fa9a6471837399e71c__section_rjl_wsd_3cc"/>

## Monitoring

When you open the *Flows* monitor for a replication flow with premium outbound integration, a value called *Used Premium Outbound Data Volume* is shown in the overview panel on the left. This is the total volume for **all** replication flow runs with premium outbound integration in this tenant during the last 360 days. The value is updated once per hour.

> ### Note:  
> -   The value may change significantly from one day to the other, for example when you run an initial load for a replication flow, or when an initial load drops out of the statistics because it happened more than 360 days ago.
> 
> -   The retention period has been increased from 90 days to 360 days starting as of July 11, 2024, so depending on when you access this feature you may see the data for less than 360 days.

Further usage-related information is available on the *Tenant Configuration* page of the *Configuration* area. In particular, you can see how much data volume has been used for premium outbound integration in this tenant in the current month and whether the allocated number of execution hours has been exceeded. \(The latter value is updated once every six hours.\)

