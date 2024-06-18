<!-- loio33f8ef4ec359409fb75925a68c23ebc3 -->

# Configure the Size of Your SAP Datasphere Tenant

Configure the size of your tenant by specifying resource sizes based on your business needs. Capacity Units \(CU\) are allocated to obtain storage and compute resources for your tenant.

You can configure the size of a subscription-based tenant and a consumption-based tenant with a standard plan.

To do so, you must have an SAP Datasphere administrator role.



<a name="loio33f8ef4ec359409fb75925a68c23ebc3__section_jqc_kwk_zsb"/>

## Configuring the Sizes of Resources

In the *Tenant Configuration* page of the *Configuration* area, you can increase the sizes for the various resources, within the permitted size combinations, to obtain a configuration that fits your exact needs, and then click *Save*.

> ### Caution:  
> Once you save the size configuration of your tenant, be aware that some resources cannot be resized later. Storage cannot be downsized. If you require a storage downsize, you must recreate the tenant. Exception: If you need to decrease the memory, see SAP note [3224686](https://launchpad.support.sap.com/#/notes/3224686).

Also, once you click *Save*:

-   The whole process may take more than 90 minutes. The configuration process is not long, but the operational process in the background can take a while.

-   In case an error occurs, you are notified that the configuration cannot be completed and that you need to try again later by clicking the *Retry* button \(which replaces the *Save* button in such a case\). The delay depends on the error \(for example, if there is an error on the SAP HANA Cloud database side, you may need to retry after 60 minutes\).

-   You can only make changes to SAP HANA Compute and SAP HANA Storage once every 24 hours.

-   If you try to change your SAP HANA configuration, SAP HANA Cloud functionalities \(Spaces, DPServer, Serving of Queries\) will not be available for around 10 minutes. If you run into issues after the configuration, use the *Retry* button.




<a name="loio33f8ef4ec359409fb75925a68c23ebc3__section_gdn_g1y_l5b"/>

## Supported Sizes

To view all supported size combinations for compute and storage resources and the number of capacity units consumed, go to the [SAP Datasphere Capacity Unit Estimator](https://datasphere-estimator-sac-saceu10.cfapps.eu10.hana.ondemand.com/).



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
> The performance class you select determines the number of vCPUs allocated to your tenant.



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

You can increase the amount of memory from 32 GB \(minimum\), by increments of 16 GB. You can reduce the amount of memory, but the lower limit depends on how much space you have assigned to space management.

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

Enable this to access the SAP HANA Automated Predictive Library \(APL\) and SAP HANA Predictive Analysis Library \(PAL\) machine learning libraries.

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

\[optional\] Select the size of data lake disk storage.

You can specify from 0 TB \(minimum\) to 90 TB \(maximum\), by increments of 1 TB.

Data lake storage includes data lake compute.

To reduce the size of your data lake storage, you must first delete your data lake instance, and re-create it in the size that you want.

> ### Note:  
> Deletion cannot be reversed and all data stored in the data lake instance will be deleted.
> 
> You cannot delete your data lake storage if it's connected to a space. You must first disconnect the space:
> 
> 1.  Go to *Space Management*, choose a space.
> 2.  Select *Edit*.
> 3.  Under *General Settings*, clear the *Use this space to access data lake* checkbox.
> 
> Data lake is not available in all regions. See SAP note [3144215](https://launchpad.support.sap.com/#/notes/3144215).



</td>
</tr>
<tr>
<td valign="top">

*SAP BW Bridge Storage*

</td>
<td valign="top">

\[optional\] Select the size of SAP BW bridge using the dropdown menu, starting from 0 GB \(minimum\).

SAP BW Bridge includes SAP BTP, ABAP environment, runtime and compute.

> ### Caution:  
> You can only change the SAP BW Bridge storage allocation, if no SAP BW Bridge instances are created.

The process for allocating capacity units to SAP BW Bridge is not part of the configuration process.

> ### Note:  
> -   First finalize the size configuration of your tenant, then open the incident as a next step. Once the incident has been processed, you can create the SAP BW bridge instance in the dedicated page *SAP BW Bridge* of the *Configuration* area with the size you’ve allocated \(see [Provisioning the SAP BW Bridge Tenant](https://help.sap.com/viewer/e2d2b48377c14490b55466b5f1872640/DEV_CURRENT/en-US/c356f4ce55744aa09ac2d79a5235c300.html "You can provision SAP BW bridge as an optional feature in SAP Datasphere.") :arrow_upper_right:\).
> 
> -   SAP BW Bridge is not available in all regions. See SAP note [3144215](https://launchpad.support.sap.com/#/notes/3144215).
> 
> -   When using a test tenant with the minimal configuration \(128 GB of storage and 1 compute block\), you cannot add SAP BW Bridge storage unless you add more compute blocks.
> 
> -   As soon as you click *Save*, the allocated capacity units will be assigned to SAP BW Bridge.



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

\[optional\] Select the number of compute blocks to allocate to Data Integration applications which provide enhanced data integration capabilities. This comprises the replication flow that enables data integration with delta processing which is the recommended integration solution for all supported source and target systems.

You can increase the number of blocks to assign a maximum of 7200 node hours. You can decrease the number of blocks until you reach the minimum number of node hours included in your plan.

> ### Note:  
> Data flows are not part of this commercial package.



</td>
</tr>
<tr>
<td valign="top">

*Execution Hours*

</td>
<td valign="top">

The number of node hours available for Data Integration applications per month is calculated from the number of allocated compute blocks.

Every month you're entitled to running up to 200 hours of jobs. Using more than 200 hours has no impact in other jobs. The consumption of data integration is not limited to avoid interrupting critical integration scenarios, but you will be billed for the overusage when it happens.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Parallel Jobs*

</td>
<td valign="top">

The maximum number of parallel jobs is calculated from the number of execution hours assigned. For every 100 execution hours, you are given one extra parallel job, up to a maximum of 10.

Each parallel job means that roughly 5 datasets, from one or several replication flows, can be run in parallel. If more replication flows are running, processing will be queued and replication will occur less frequently.

</td>
</tr>
<tr>
<td valign="top">

*Data Integration*: *Allocated Execution Hours*

</td>
<td valign="top">

Displays the number of hours allocated to Data Integration applications.

</td>
</tr>
<tr>
<td valign="top">

*Data Integration*: *Used Execution Hours*

</td>
<td valign="top">

Displays the number of hours used by Data Integration applications.

</td>
</tr>
<tr>
<td valign="top">

*Data Integration*: *Exceeded Execution Hours*

</td>
<td valign="top">

Displays the execution hours you have used that exceed the amount allocated by your tenant configuration.

> ### Note:  
> This only appears if you have used more hours than allocated.



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

You can increase or decrease the number of storage blocks allocated for premium outbound integration. Each block provides 20 GB of storage.

</td>
</tr>
<tr>
<td valign="top">

*Outbound Volume*

</td>
<td valign="top">

The outbound volume is calculated from the number of allocated blocks.

</td>
</tr>
<tr>
<td valign="top">

*Premium Outbound Usage*: *Allocated Data Volume*

</td>
<td valign="top">

Displays the number of GB allocated to premium outbound integration.

</td>
</tr>
<tr>
<td valign="top">

*Premium Outbound Usage*: *Used Data Volume*

</td>
<td valign="top">

Displays the number of GB used by premium outbound integration.

</td>
</tr>
<tr>
<td valign="top">

*Premium Outbound Usage*: *Exceeded Data Volume*

</td>
<td valign="top">

Displays the data volume you have used that exceeds the amount allocated by your tenant configuration.

> ### Note:  
> This only appears if you have used more data than allocated.



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

Displays the amount of storage you have used that exceeds the amount allocated by your tenant configuration.

> ### Note:  
> This only appears if you have used more storage space than allocated.



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

*Units in Use per Month*

</td>
<td valign="top">

Displays the estimated number of capacity units consumed per month by the storage and compute resources you've specified.

</td>
</tr>
<tr>
<td valign="top">

*Units in Use per Hour*

</td>
<td valign="top">

Displays the estimated number of capacity units consumed per hour by the storage and compute resources you've specified.

</td>
</tr>
</table>

