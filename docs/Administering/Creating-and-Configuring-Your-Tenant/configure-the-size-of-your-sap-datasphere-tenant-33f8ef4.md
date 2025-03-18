<!-- loio33f8ef4ec359409fb75925a68c23ebc3 -->

# Configure the Size of Your SAP Datasphere Tenant

Configure the size of your tenant by specifying resource sizes based on your business needs. Capacity Units \(CU\) are allocated to obtain storage and compute resources for your tenant.

You can configure the size of a subscription-based tenant and a consumption-based tenant with a standard plan.

To do so, you must have an SAP Datasphere administrator role.



<a name="loio33f8ef4ec359409fb75925a68c23ebc3__section_jqc_kwk_zsb"/>

## Configuring the Sizes of Resources

In the *Tenant Configuration* page of the *Configuration* area, you can increase the sizes for the various resources, within the permitted size combinations, to obtain a configuration that fits your exact needs, and then click *Save*.

> ### Caution:  
> Once you save the size configuration of your tenant, some resources cannot be resized later. Storage cannot be downsized. If you require storage downsize, you must recreate the tenant. Exception: If you need to decrease the memory, see SAP note [3224686](https://launchpad.support.sap.com/#/notes/3224686).

Also, once you click *Save*:

-   The whole process could take more than 90 minutes. The configuration process is not long, but the operational process in the background can take a while.

-   In case an error occurs, you are notified that the configuration cannot be completed and that you need to try again later by clicking the *Retry* button \(which replaces the *Save* button in such a case\). The delay depends on the error \(for example, if there is an error on the SAP HANA Cloud database side, you can retry after 60 minutes\).

-   You can only change SAP HANA Compute and SAP HANA Storage once every 24 hours.

-   If you try to change your SAP HANA configuration, SAP HANA Cloud functionality \(Spaces, DPServer, Serving of Queries\) will not be available for around 10 minutes. If you run into issues after the configuration, use the *Retry* button.




<a name="loio33f8ef4ec359409fb75925a68c23ebc3__section_gdn_g1y_l5b"/>

## Supported Sizes

To view all supported size combinations for compute and storage resources and the number of capacity units consumed, go to the [https://datasphere-estimator-sac-saceu10.cfapps.eu10.hana.ondemand.com/](https://datasphere-estimator-sac-saceu10.cfapps.eu10.hana.ondemand.com/).



<a name="loio33f8ef4ec359409fb75925a68c23ebc3__section_vnr_2qt_ytb"/>

## Tenant Configuration Page Properties

**Base Configuration**


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

*Performance Class*

</td>
<td valign="top">

Select a performance class for your tenant:

-   Memory
-   Compute
-   High-Memory
-   High-Compute

> ### Note:  
> **vCPU Allocation** table below.



</td>
</tr>
<tr>
<td valign="top">

*Storage*

</td>
<td valign="top">

Set the size of disk storage.

You can specify from 128 GB \(minimum\), by increments of 64 GB.

</td>
</tr>
<tr>
<td valign="top">

*Memory*

</td>
<td valign="top">

Set the memory allocated to your tenant.

You can increase the amount of memory from 32 GB \(minimum\), by increments of 16 GB.

You can reduce the amount of memory, but the lower limit depends on how much space you have assigned to space management.

For more information, see [Allocate Storage to a Space](../Creating-Spaces-and-Allocating-Storage/allocate-storage-to-a-space-f414c3d.md).

</td>
</tr>
<tr>
<td valign="top">

*vCPU*

</td>
<td valign="top">

Displays the number of vCPUs allocated to your tenant. The number is calculated based on the selected performance class, and memory used by your tenant.

</td>
</tr>
<tr>
<td valign="top">

*Enable the SAP HANA Cloud Script Server* 

</td>
<td valign="top">

Enable this option to access the SAP HANA Automated Predictive Library \(APL\) and SAP HANA Predictive Analysis Library \(PAL\) machine learning libraries.

</td>
</tr>
</table>

**Additional Configuration**


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

*Data Lake Storage*

</td>
<td valign="top">

\[optional\] Select the size of data lake disk storage. The performance class you select determines the number of vCPUs allocated to your tenant.

You can specify from 0 TB \(minimum\) to 90 TB \(maximum\), by increments of 1 TB.

Data lake storage includes data lake compute.

To reduce the size of your data lake storage, you must first delete your data lake instance, and re-create it in the size that you want.

> ### Note:  
> Deletion cannot be reversed and all data stored in the data lake instance is deleted.
> 
> You cannot delete your data lake storage if it's connected to a space. You must first disconnect the space:
> 
> 1.  Go to *Space Management*and choose a space.
> 2.  Select *Edit*.
> 3.  Under *General Settings*, clear the *Use this space to access data lake* checkbox.
> 
> Data lake is not available in all regions. See SAP Note [3144215](https://launchpad.support.sap.com/#/notes/3144215).



</td>
</tr>
<tr>
<td valign="top">

*SAP BW Bridge Storage*

</td>
<td valign="top">

\[optional\] Select the size of SAP BW bridge using the dropdown menu.

SAP BW Bridge includes SAP BTP, ABAP environment, and an own HANA Cloud runtime and compute.

> ### Caution:  
> You can only change the size of SAP BW bridge in Tenant Configuration as long as the tenant has not been created. After tenant creation, SAP BW bridge can be upsized by creating a support case on component DS-BWB.

> ### Note:  
> -   First finalize the size configuration of your tenant. Then, you can create the SAP BW bridge instance in the dedicated page *SAP BW Bridge* of the *Configuration* area with the size you’ve allocated \(see [Provisioning the SAP BW Bridge Tenant](https://help.sap.com/viewer/e2d2b48377c14490b55466b5f1872640/DEV_CURRENT/en-US/c356f4ce55744aa09ac2d79a5235c300.html "You can provision SAP BW bridge as an optional feature in SAP Datasphere.") :arrow_upper_right:\).
> 
> -   For data center availability, check SAP note [3144215](https://launchpad.support.sap.com/#/notes/3144215).
> 
> -   As soon as you click *Save*, the allocated capacity units will be assigned to SAP BW Bridge.



</td>
</tr>
</table>

**Object Store**


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

*Storage*

</td>
<td valign="top">

Select the size of storage in TB.

You can specify the storage size starting from 1 TB.

Storage is correlated to SAP HANA Data Lake Files \(HDLF\) size.

> ### Note:  
> You may incur higher consumption costs because data lake files keep a previous copy of any file affected by an operation for a given retention time to allow for operations such as `RESTORESNAPSHOT`. These previous copies incur data lake storage costs. For example, you may have a 10 MB table, and the storage will be higher than that because of the number of operations initiated and copied. For more information, see [Restoring data in Data Lake Files](https://help.sap.com/docs/hana-cloud-data-lake/user-guide-for-data-lake-files/restoring-data-in-data-lake-files#context) and [Limitations of Data Lake files](https://help.sap.com/docs/hana-cloud-data-lake/user-guide-for-data-lake-files/limitations-of-data-lake-files).
> 
> Storage is rounded to the next whole GB. For example, if all of the files in storage consume 1.2 GB, then the memory is rounded up to the next full gigabyte. In this example, it would round up to 2 GB.



</td>
</tr>
<tr>
<td valign="top">

*Compute*

</td>
<td valign="top">

Select the number of block-hours starting from 1.

Values set here are mapped to Spark Compute and the number of Object Store Requests.

4 GB of Spark Compute are equal to 0.149 Object Store Compute Blocks.

1000 Object Store Requests are equal to 0.026 Object Store Compute Blocks.

</td>
</tr>
</table>

**Elastic Compute Node**


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

*Performance Class*

</td>
<td valign="top">

\[optional\] Select a performance class for your elastic compute node block-hours:

-   Memory
-   Compute
-   High-Compute

> ### Note:  
> The performance class you select determines the number of vCPUs and the RAM allocated to your tenant.

You can only use one performance class at a time. To use a different performance class, you must re-configure your *Tenant Configuration* settings.

</td>
</tr>
<tr>
<td valign="top">

*Block Specifications*

</td>
<td valign="top">

Displays the number of vCPUs and the amount of RAM allocated to your tenant.

</td>
</tr>
<tr>
<td valign="top">

*Block-Hours*

</td>
<td valign="top">

\[optional\] Set the number of blocks-hours scheduled for elastic compute node consumption. Each block-hour is an additional block of vCPu and RAM for your tenant to use in one hour. The maximum number of block-hours you can consume in one hour is four.

</td>
</tr>
<tr>
<td valign="top">

*Elastic Compute Node Usage: Allocated Block-Hours*

</td>
<td valign="top">

Displays the number of blocks currently scheduled for elastic compute node consumption.

</td>
</tr>
<tr>
<td valign="top">

*Elastic Compute Node Usage: Used Block-Hours*

</td>
<td valign="top">

Displays the total number of blocks consumed by elastic compute nodes. The total is independent of which performance-class is selected.

</td>
</tr>
<tr>
<td valign="top">

*Elastic Compute Node Usage: Exceeded Block-Hours*

</td>
<td valign="top">

Displays the block-hours you have used that exceed the amount allocated by your tenant configuration.

> ### Note:  
> This option only appears if you have used more block-hours than allocated.



</td>
</tr>
</table>

**Data Integration**


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

*Data Integration*

</td>
<td valign="top">

\[optional\] \] Enter the number of blocks to allocate to data integration applications \(replication flows\).

Even if you don’t allocate blocks here, you have a default number of execution hours for data integration \(depending on your contract\). For more information about this, as well as about how many execution hours you get per block, see the SAP Datasphere and SAP Datasphere, Test Tenant Supplemental Terms and Conditions, which are a part of the [Service Level Agreement](https://help.sap.com/viewer/86054eedd0dd480f92b0824c281923d5/cloud/en-US/962dfadea39843efaa806323b9a872fe.html "The Service Level Agreement (SLA) is a contract between SAP and its customers that forms the basis of your contractual relationship with SAP when referenced in specific order forms.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

*Execution Hours*

</td>
<td valign="top">

Displays the number of execution hours available for data integration applications per month. It is calculated by multiplying the number of allocated compute blocks by the number of execution hours per block \(per your contract\). You can increase or decrease the data integration node hours without downtime. The amount of job processing in parallel is automatically adjusted within the limits set: Every 100h of your allocated data integration hours gets one extra parallel pod for job processing. For example, if you have 400h or data integration, you will have a maximum of four parallel pods available for processing.

> ### Note:  
> If you exceed the available execution hours, your data integration processes \(such as replication flow runs\) continues running to avoid interrupting critical integration scenarios, which can result in additional costs \(depending on your plan\).



</td>
</tr>
<tr>
<td valign="top">

*Maximum Parallel Jobs*

</td>
<td valign="top">

Displays the maximum number of jobs that can run in parallel.

The minimal configuration of SAP Datasphere supports 2 parallel jobs. For every additional 100 execution hours allocated, you get one extra parallel job, up to a maximum of 10.

Each parallel job means that roughly 5 replication objects \(from one or more replication flows\) can be processed in parallel.

If the number of running replication flows exceeds the maximum number of parallel jobs, processing is queued, and replication occurs less frequently.

</td>
</tr>
<tr>
<td valign="top">

*Data Integration*: *Allocated Execution Hours*

</td>
<td valign="top">

Displays the number of execution hours allocated to data integration applications so that you can easily compare it against the used execution hours.

</td>
</tr>
<tr>
<td valign="top">

*Data Integration*: *Used Execution Hours*

</td>
<td valign="top">

Displays the number of hours used by data integration applications in the current month. The value is updated once every 6 hours.

</td>
</tr>
<tr>
<td valign="top">

*Data Integration*: *Exceeded Execution Hours*

</td>
<td valign="top">

Displays the execution hours that you have used in the current month that exceed the amount allocated in tenant configuration.

> ### Note:  
> This option only appears if you have used more hours than allocated.



</td>
</tr>
</table>

**Premium Outbound Integration**


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

*Outbound Blocks*

</td>
<td valign="top">

Enter the number of blocks to be used for premium outbound integration. Having at least one block assigned here is a prerequisite for using a non-SAP target in a replication flow. For more information, see [Premium Outbound Integration](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/4e9c6acb5d6a43fa9a6471837399e71c.html "To use a non-SAP target in a replication flow, you need premium outbound integration.") :arrow_upper_right:.

Each block gives you 20 GB of data volume for transfer.

</td>
</tr>
<tr>
<td valign="top">

*Outbound Volume*

</td>
<td valign="top">

Displays the data volume available for premium outbound integration per month. It is calculated by multiplying the number of allocated blocks by 20 GB.

> ### Note:  
> If you exceed the assigned volume, your data integration processes \(such as replication flow runs\) continues running to avoid interrupting critical integration scenarios, which can result in additional costs \(depending on your plan\).



</td>
</tr>
<tr>
<td valign="top">

*Premium Outbound Usage*: *Allocated Data Volume*

</td>
<td valign="top">

Displays the monthly allocated data volume \(in GB\) for premium outbound integration so that you can easily compare it against the used volume.

</td>
</tr>
<tr>
<td valign="top">

*Premium Outbound Usage*: *Used Data Volume*

</td>
<td valign="top">

Displays the used data volume \(in GB\) for premium outbound integration in the current month. The value is updated once every 6 hours.

</td>
</tr>
<tr>
<td valign="top">

*Premium Outbound Usage*: *Exceeded Data Volume*

</td>
<td valign="top">

Displays the data volume that you have used in the current month that exceeds the amount allocated in tenant configuration.

> ### Note:  
> This option only appears if you have used more data than allocated.



</td>
</tr>
</table>

**Catalog**


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

*Catalog Storage*

</td>
<td valign="top">

Included by default. You can increase or decrease the number of storage blocks allocated for the catalog.

</td>
</tr>
<tr>
<td valign="top">

*Storage*

</td>
<td valign="top">

The amount of storage available for the catalog is calculated from the number of allocated blocks.

</td>
</tr>
<tr>
<td valign="top">

*Catalog Usage*: *Allocated Storage*

</td>
<td valign="top">

Displays the number of GB allocated to the catalog.

</td>
</tr>
<tr>
<td valign="top">

*Catalog Usage*: *Used Storage*

</td>
<td valign="top">

Displays the number of GB used by the catalog.

</td>
</tr>
<tr>
<td valign="top">

*Catalog Usage*: *Exceeded Storage*

</td>
<td valign="top">

Displays the amount of storage that you have used that exceeds the amount allocated by your tenant configuration.

> ### Note:  
> This option only appears if you have used more storage space than allocated.



</td>
</tr>
</table>

**Capacity Units**


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

*Purchased units*

</td>
<td valign="top">

Displays the capacity units purchased for the month.

</td>
</tr>
<tr>
<td valign="top">

*Estimated Units*

</td>
<td valign="top">

Displays the number of units anticipated to be charged to the user by the end of the month. This calculation assumes that the current configuration stays unchanged and all pay-per-use services are fully utilized.

</td>
</tr>
<tr>
<td valign="top">

*Available Units*

</td>
<td valign="top">

Displays the estimated capacity units left for this month. This number is calculated as Purchased Units - Estimated Units = Available Units.

</td>
</tr>
<tr>
<td valign="top">

*Your Consumption*

</td>
<td valign="top">

Displays the amount charged to the users this month for all services. This calculation accounts for any configuration changes made during the month and the precise usage of pay-per-use services.

</td>
</tr>
</table>



<a name="loio33f8ef4ec359409fb75925a68c23ebc3__section_w4d_15g_sbc"/>

## vCPU Allocation

When you set your base configuration, the performance class you select and the hyperscaler you are using determines the amount of memory in GB available for each vCPU in the system. For example, an AWS system with 32 GB of memory has 2 vCPUs, whereas an AWS system with 320 GB of memory has 20 vCPUs. The tables below list the memory to vCPU ratio for each hyperscaler.

**Performance Class: Memory**


<table>
<tr>
<th valign="top">

Hyperscaler

</th>
<th valign="top">

Memory

</th>
<th valign="top">

vCPUs

</th>
</tr>
<tr>
<td valign="top">

AWS

</td>
<td valign="top">

32-960 GB

</td>
<td valign="top">

16

</td>
</tr>
<tr>
<td valign="top">

AWS

</td>
<td valign="top">

1024-1792 GB

</td>
<td valign="top">

16

</td>
</tr>
<tr>
<td valign="top">

AWS

</td>
<td valign="top">

1800 GB

</td>
<td valign="top">

15

</td>
</tr>
<tr>
<td valign="top">

AWS

</td>
<td valign="top">

5970 GB

</td>
<td valign="top">

13.57

</td>
</tr>
<tr>
<td valign="top">

GCP

</td>
<td valign="top">

32-960 GB

</td>
<td valign="top">

16

</td>
</tr>
<tr>
<td valign="top">

GCP

</td>
<td valign="top">

1024-1856 GB

</td>
<td valign="top">

16

</td>
</tr>
<tr>
<td valign="top">

GCP

</td>
<td valign="top">

1904

</td>
<td valign="top">

16

</td>
</tr>
<tr>
<td valign="top">

Azure

</td>
<td valign="top">

32-1024 GB

</td>
<td valign="top">

16

</td>
</tr>
<tr>
<td valign="top">

Azure

</td>
<td valign="top">

1088-1920 GB

</td>
<td valign="top">

16

</td>
</tr>
<tr>
<td valign="top">

Azure

</td>
<td valign="top">

2800 GB

</td>
<td valign="top">

13.72

</td>
</tr>
<tr>
<td valign="top">

Azure

</td>
<td valign="top">

3744 GB

</td>
<td valign="top">

16

</td>
</tr>
<tr>
<td valign="top">

Azure

</td>
<td valign="top">

5600 GB

</td>
<td valign="top">

13.59

</td>
</tr>
</table>

**Performance Class: High Memory**


<table>
<tr>
<th valign="top">

Hyperscaler

</th>
<th valign="top">

Memory

</th>
<th valign="top">

vCPUs

</th>
</tr>
<tr>
<td valign="top">

AWS

</td>
<td valign="top">

3600 GB

</td>
<td valign="top">

30

</td>
</tr>
<tr>
<td valign="top">

AWS

</td>
<td valign="top">

9000 GB

</td>
<td valign="top">

20.36

</td>
</tr>
<tr>
<td valign="top">

AWS

</td>
<td valign="top">

12000 GB

</td>
<td valign="top">

27.15

</td>
</tr>
<tr>
<td valign="top">

GCP

</td>
<td valign="top">

3700 GB

</td>
<td valign="top">

23.72

</td>
</tr>
<tr>
<td valign="top">

GCP

</td>
<td valign="top">

5750 GB

</td>
<td valign="top">

28.19

</td>
</tr>
<tr>
<td valign="top">

GCP

</td>
<td valign="top">

8630 GB

</td>
<td valign="top">

20.95

</td>
</tr>
<tr>
<td valign="top">

GCP

</td>
<td valign="top">

11520 GB

</td>
<td valign="top">

27.96

</td>
</tr>
<tr>
<td valign="top">

Azure

</td>
<td valign="top">

3776 GB

</td>
<td valign="top">

31.47

</td>
</tr>
<tr>
<td valign="top">

Azure

</td>
<td valign="top">

5595 GB

</td>
<td valign="top">

27.43

</td>
</tr>
<tr>
<td valign="top">

Azure

</td>
<td valign="top">

7440 GB

</td>
<td valign="top">

18.05

</td>
</tr>
<tr>
<td valign="top">

Azure

</td>
<td valign="top">

11150 GB

</td>
<td valign="top">

20.95

</td>
</tr>
</table>

**Performance Class: Compute**


<table>
<tr>
<th valign="top">

Hyperscaler

</th>
<th valign="top">

Memory

</th>
<th valign="top">

vCPUs

</th>
</tr>
<tr>
<td valign="top">

AWS

</td>
<td valign="top">

32-912 GB

</td>
<td valign="top">

8

</td>
</tr>
<tr>
<td valign="top">

GCP

</td>
<td valign="top">

32-608 GB

</td>
<td valign="top">

8

</td>
</tr>
<tr>
<td valign="top">

Azure

</td>
<td valign="top">

32-480 GB

</td>
<td valign="top">

8

</td>
</tr>
</table>

**Performance Class: High Compute**


<table>
<tr>
<th valign="top">

Hyperscaler

</th>
<th valign="top">

Memory

</th>
<th valign="top">

vCPUs

</th>
</tr>
<tr>
<td valign="top">

AWS

</td>
<td valign="top">

32-352 GB

</td>
<td valign="top">

4

</td>
</tr>
<tr>
<td valign="top">

GCP

</td>
<td valign="top">

32-288 GB

</td>
<td valign="top">

4

</td>
</tr>
<tr>
<td valign="top">

Azure

</td>
<td valign="top">

32-352 GB

</td>
<td valign="top">

4

</td>
</tr>
</table>

