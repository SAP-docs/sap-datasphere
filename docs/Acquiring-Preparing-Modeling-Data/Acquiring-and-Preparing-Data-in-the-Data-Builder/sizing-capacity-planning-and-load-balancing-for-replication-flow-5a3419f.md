<!-- loio5a3419f3be6e49f794248f20331b255b -->

# Sizing, Capacity Planning, and Load Balancing for Replication Flows

Learn more about capacity planning, load balancing, performance, and related aspects for replication flows.

This text contains the following sections:

-   [Concepts](sizing-capacity-planning-and-load-balancing-for-replication-flow-5a3419f.md#loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_Sizing_Concepts)
-   [Sizing for Initial Load](sizing-capacity-planning-and-load-balancing-for-replication-flow-5a3419f.md#loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_Sizing_InitialLoad)
-   [Sizing for Delta Loading](sizing-capacity-planning-and-load-balancing-for-replication-flow-5a3419f.md#loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_Sizing_Delta)
-   [Examples](sizing-capacity-planning-and-load-balancing-for-replication-flow-5a3419f.md#loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_Sizing_Examples)
-   [Capacity Planning At Tenant Level](sizing-capacity-planning-and-load-balancing-for-replication-flow-5a3419f.md#loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_Sizing_Capacity)
-   [Load Balancing](sizing-capacity-planning-and-load-balancing-for-replication-flow-5a3419f.md#loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_Sizing_LoadBalancing)
-   [Further Information](sizing-capacity-planning-and-load-balancing-for-replication-flow-5a3419f.md#loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_FurtherInfo)



<a name="loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_Sizing_Concepts"/>

## Concepts

**Replication objects** are the entities of data to be transferred. For SAP S/4HANA systems, for example, it's CDS views \(see also [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md)\). A replication flow can contain a maximum of 500 replication objects.

Big replication objects are divided into **partitions** that can be transferred in parallel. Partitioning is done automatically during the initial steps of the replication.

**Replication flow jobs** are the technical runtime artefacts \(background jobs\) that do the data transfer itself and the necessary related tasks, such as setup, partitioning, or log clean-up \(also referred to as housekeeping\). By default, a replication flow can utilize up to two replication flow jobs.

A replication flow job can process up to five **work orders** for data transfer and five work orders for housekeeping. \(Work orders are internal objects that are needed to organize the work efficiently.\) If a replication object is divided into partitions, each partition is processed by one work order.

Each data transfer work order requires a thread, that is, a technical connection to both the source and target, while a housekeeping work order requires a single thread to either source or target system.

Every replication object has housekeeping and data transfer work orders assigned. The total number of work orders for data transfer and housekeeping, respectively, for a replication flow depends on the number of objects in the replication flow, data partitioning for each object, load type, and current state of replication. The number of data transfer and housekeeping work orders that can be processed in parallel is limited by the maximum number of threads to source and target, respectively, that are configured in the replication flow, and the number of replication flow jobs configured for the SAP Datasphere tenant.

Each replication flow counts towards the total possible maximum of 16 parallel jobs in one tenant. This means that if you have 16 replication flow jobs, you can process up to 80 work orders for data transfer and 80 work orders for housekeeping. With one thread per work order, the maximum total number of threads is 160 for the source and 160 for the target. The number of replication flows that can run simultaneously is not fixed at 16. It depends on how many threads each flow consumes. In the simplest case, if each replication flow requires only one data transfer thread, up to 80 flows can run in parallel. Conversely, a replication flow with one object but with many partitions, or a single large flow with many objects and partitions, might consume most or all the available threads by itself. As partitions finish complete data transfer, fail with transient or permanent errors, or move to delta load, threads are released, and additional flows can start. Note that the replication flow jobs are shared by all the replication flows in the tenant.

For more information, see [3649926](https://me.sap.com/notes/3649926)

> ### Note:  
> For users who are familiar with SAP Data Intelligence Cloud:
> 
> -   In SAP Data Intelligence Cloud, the source and the target are referred to as systems. In SAP Datasphere, the comparable concept is referred to as a connection.
> 
> -   Replication flow jobs in SAP Datasphere are comparable to worker graphs in SAP Data Intelligence Cloud.
> 
> -   Replication objects are comparable to data sets. \(In SAP Data Intelligence Cloud, data set refers to the object of a replication flow, such as a CDS view or a table, not to an individual data record.\)



<a name="loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_Sizing_InitialLoad"/>

## Sizing for Initial Load

For the initial load, the default setting is that a replication flow can utilize a maximum of 16 threads each to the source and target, so that a total maximum of 16 data transfer and housekeeping work orders can be processed utilizing up to 3 replication flow jobs.

The actual throughput depends on a variety of factors, such as the source and the target of the replication flow, how many replication objects there are, the size and structure of the individual replication objects, or what other operations take place in your system landscape in parallel to the replication flow. If you want to increase the throughput, you can change the maximum number of threads for initial loading in the source settings and target settings, respectively, for your replication flow. This can be helpful, for example, if you have very big replication objects that are divided into partitions, so that multiple partitions can be processed in parallel if there are enough threads available. For more information, see [Configure a Replication Flow](configure-a-replication-flow-3f5ba0c.md).



<a name="loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_Sizing_Delta"/>

## Sizing for Delta Loading

For delta loading, the default is that each object is processed as one partition by one data transfer work order, resulting in a total of 5 data transfer work orders and one replication flow job being utilized. For ABAP-based sources, you can change the number of threads to a maximum of 16 \(in the source settings\).



<a name="loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_Sizing_Examples"/>

## Examples

-   A replication flow has 6 objects and is configured with a maximum of 16 threads to the source and target, respectively. During the initial steps of the replication, only housekeeping work orders \(such as setup and partitioning\) exist for each object in the replication flow. Therefore there will only be 6 housekeeping work orders \(one for each object\), and hence a maximum of 6 technical connections \(threads\) are opened to source and target and processed using one replication flow job. After the data partitioning is completed for each object, and assuming each object has 3 partitions, these partitions will be processed using 18 data transfer work orders \(6 objects with 3 partitions per object and one work order per partition\). Since the replication flow is configured with a maximum of 16 threads to the source and target, respectively, only 16 out of the 18 data transfer tasks can be processed in parallel. This means a maximum of 3 replication flow jobs can be utilized.
-   For delta loading, this setup would result in a total of 6 data transfer work orders and one replication flow job. For AzureSQL and SAP HANA sources, an additional housekeeping work order \(log purge\) is processed for each object during delta loading, which can be covered by the same replication flow job.

-   A replication flow has 16 objects and is configured with a maximum of 16 threads to source and target, respectively. During the initial steps of the replication, there will be 16 housekeeping tasks \(one for each object\), hence a maximum of 16 technical connections \(threads\) are opened to the source and target, respectively, and processed using 3 replication flow jobs. After the data partitioning is completed for each object, and assuming each object has 3 partitions, these partitions will be processed using 48 data transfer work orders, one for each partition \(16 objects with 3 partitions per object\). Since the replication flow is configured with a maximum of 16 threads for the source and target, only 16 of the 48 data transfer tasks can be processed in parallel. This means that a maximum of 3 replication flow jobs can be utilized.

    For delta loading, this setup would result in a total of 16 data transfer work orders. For AzureSQL and SAP HANA sources, an additional 16 housekeeping work orders \(log purge\) are processed, which can be covered by the same 3 replication flow jobs.




<a name="loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_Sizing_Capacity"/>

## Capacity Planning At Tenant Level

For replication flows, the most important parameters at tenant level are execution hours \(also referred to as node hours\), compute blocks for data integration, and maximum parallel jobs, plus premium outbound integration if you want to use non-SAP targets.

> ### Note:  
> One source object can be used in several replication flows. However, you must consider that if the same source is being read at the same time, it can impact the performance.

For more information, see [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/33f8ef4ec359409fb75925a68c23ebc3.html "Configure the size of your tenant by specifying resource sizes based on your business needs. Capacity Units (CU) are allocated to obtain storage and compute resources for your tenant.") :arrow_upper_right:, particularly the Premium Outbound Integration section \(if applicable\) and the Data Integration section.



<a name="loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_Sizing_LoadBalancing"/>

## Load Balancing

There are various measures that you can take to improve utilization of available resources and avoid bottlenecks. However, all of these involve trade-offs between conflicting requirements. It may take some planning and experimenting until you arrive at the best possible configuration.

-   If you split a replication flow that includes a large number of objects into several replication flows with a few objects each, you can run these smaller flows at different times and thus distribute the load on your system more evenly. It may even make sense to review the distribution of objects across replication flows – for example, if you have some very big replication objects, you could create a separate replication flow for each of these objects.

    From the perspective of consumption measurement, it does not make a difference how many replication flows you use, as the relevant value \(execution hours\) is calculated based on the execution time of replication flow jobs.

    On the other hand, more replication flows also mean higher administration effort.

-   You can assign more threads in the source settings and target settings for your replication flow to increase the throughput. The system then picks up the loads in a round-robin fashion. However, this approach has its limits. For example, assigning too many threads for the source and target in one replication flow may result in throughput improvements \(because of increased parallel processing for this replication flow, but may cause performance issues for other flows. Additionally, it can result in issues with overall performance across all spaces in the tenant, as the replication flow jobs in an SAP Datasphere tenant are shared among all the replication flows \(across all spaces\).




<a name="loio5a3419f3be6e49f794248f20331b255b__section_ReplFlow_FurtherInfo"/>

## Further Information

For more detailed information and examples, including example calculations of data volume and of required compute blocks for data integration, see [Replication Flow Blog Series Part 4 - Sizing](https://community.sap.com/t5/technology-blogs-by-sap/replication-flow-blog-series-part-4-sizing/ba-p/13579486).

