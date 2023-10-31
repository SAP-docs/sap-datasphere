<!-- loio33f8ef4ec359409fb75925a68c23ebc3 -->

# Configure the Size of Your SAP Datasphere Tenant

Configure the size of your tenant by specifying resource sizes based on your business needs. Capacity Units \(CU\) are allocated to obtain storage and compute resources for your tenant.

You can configure the size of a subscription-based tenant and a consumption-based tenant with a standard plan.

To do so, you must have an SAP Datasphere administrator role.



<a name="loio33f8ef4ec359409fb75925a68c23ebc3__section_jqc_kwk_zsb"/>

## Configuring the Sizes of Resources

**For Subscription-Based Tenants and Consumption-Based Tenants with Standard Plan**

In the *Tenant Configuration* page of the *Configuration* area, you can increase the sizes for the various resources, within the permitted size combinations, to obtain a configuration that fits your exact needs, and then click *Save*.

> ### Caution:  
> Once you save the size configuration of your tenant, be aware that some resources cannot be resized later. Exception: If you need to decrease the memory, see SAP note [3224686](https://launchpad.support.sap.com/#/notes/3224686).

Also, once you click *Save*:

-   The whole process may take more than 90 minutes. The configuration process is not long, but the operational process in the background can take a while.

-   In case an error occurs, you are notified that the configuration cannot be completed and that you need to try again later by clicking the *Retry* button \(which replaces the *Save* button in such a case\). The delay depends on the error \(for example, if there is an error on the SAP HANA Cloud database side, you may need to retry after 60 minutes\).

-   You can only make changes to SAP HANA Compute and SAP HANA Storage once every 6 hours.

-   If you try to change your SAP HANA configuration, SAP HANA Cloud functionalities \(Spaces, DPServer, Serving of Queries\) will not be available for around 10 minutes. If you run into issues after the configuration, use the *Retry* button.


> ### Note:  
> **Only for Subscription-Based Tenants:** 
> 
> -   If your tenant has been provisioned with the minimum number of capacity units \(4300\), you can directly work with your tenant. The capacity units are allocated as follows: 256 GB of storage and 2 compute blocks.
> 
> -   If your tenant has been provisioned with a higher number of capacity units, you must finalize the size of the tenant. When you log into your tenant for the first time, a message indicates that you must configure the tenant and includes a link that takes you to the *Tenant Configuration* page of the *Configuration* area. You can leave the default sizes or specify other sizes for the various resources and click *Save*. As long as you have not finalized this tenant size, you can use only administration features of SAP Datasphere \(but you cannot create spaces in *Space Management*\). At a later point in time, if you haven’t yet allocated all the capacity units or if you’ve acquired additional capacity units, you can allocate them and increase the sizes for the various resources.
> 
> -   If you need further resources, please reach out to SAP.
> 
> -   See the blog [SAP Datasphere: Configure the Size of YourSAP Datasphere Tenant](https://blogs.sap.com/2022/02/18/configure-the-size-of-your-sap-data-warehouse-cloud-tenant/) \(published in February 2022\).



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

*Storage*

</td>
<td valign="top">

Select the size of disk storage.

You can specify from 256 GB \(minimum\), by increments of 256 GB.

</td>
</tr>
<tr>
<td valign="top">

*Compute Blocks*

</td>
<td valign="top">

Select the number of compute blocks.

You can specify from 2 blocks \(minimum\), by increments of 1 block. Each compute block provides a range of 60 to 64 GB of RAM, depending on the hyperscaler.

The number for memory is calculated based on the compute blocks and you cannot directly modify it.

**Dependencies between storage and compute blocks**: the storage and compute blocks depend on each other. When you modify a parameter, the other one needs to be changed accordingly. The minimum and maximum allowed storage sizes depend on the total memory defined by the selected compute blocks. The storage size must be higher than the memory size and can only be increased up to 4 times as much as the memory. All the possible size combinations of storage and compute blocks are controlled in the *Tenant Configuration* page. When the size combination you enter is allowed, the sizes are kept. When the size combination you enter is not allowed, error messages guide you to modify the sizes.

</td>
</tr>
<tr>
<td valign="top">

*Memory*

</td>
<td valign="top">

Displays the size of memory calculated based on the selected number of compute blocks.

> ### Note:  
> If you’re using a tenant in regions EU10 or US10 with the hyperscaler Amazon Web Services \(AWS\), you can choose among the maximum available memory sizes in the *Predefined* area. This area is visible only if you’re using a tenant in these regions.
> 
> For more information on the SAP HANA database sizes supported by regions, see [Memory and Storage Sizes Supported by SAP HANA Database](https://help.sap.com/docs/HANA_CLOUD/9ae9104a46f74a6583ce5182e7fb20cb/798c2c6ba7ae41e898f423aa34491ac3.html) in the *SAP HANA Cloud Administration Guide*.



</td>
</tr>
</table>

**Additional Data Warehouse Configuration**


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

You can specify from 0 TB \(minimum\) to 90 TB \(maximum\), by increments of 5 TB.

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
> -   When you provision a non-productive tenant, you’ll need to request the SAP BW bridge Cloud-ABAP Service for your tenant by opening an incident via ServiceNow with the component DWC-BWB.
> 
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

\[optional\] Select the number of compute blocks to allocate to Data Integration applications. You can increase the number of blocks to assign a maximum of 7200 node hours. You can decrease the number of blocks until you reach the minimum number of node hours included in your plan.

</td>
</tr>
<tr>
<td valign="top">

*Execution Hours*

</td>
<td valign="top">

The number of node hours available for Data Integration applications per month is calculated from the number of allocated compute blocks.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Parallel Jobs*

</td>
<td valign="top">

The maximum number of parallel jobs is calcuated from the number of execution hours assigned. For every 100 execution hours, you are given one extra parallel job, up to a maxiumum of 10.

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

Included by default. The amount of GB used per hour available for Catalog assets, activities and metadata cannot be changed.

</td>
</tr>
<tr>
<td valign="top">

*Catalog Crawling*

</td>
<td valign="top">

Included by default. The number of blocks used by Catalog crawling cannot be changed.

</td>
</tr>
<tr>
<td valign="top">

*Execution Hours*

</td>
<td valign="top">

The number of hours consumed by Catalog usage every month.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Parallel Jobs*

</td>
<td valign="top">

The maximum number of parallel Catalog jobs cannot be changed.

</td>
</tr>
</table>

**Information for subscription-based tenants only**


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

*Estimated Consumption*

</td>
<td valign="top">

Displays the total number of capacity units consumed by the storage and compute resources you've specified.

</td>
</tr>
<tr>
<td valign="top">

*Your Subscription*: *Available Units*

</td>
<td valign="top">

Displays the number of capacity units that are available for the tenant.

</td>
</tr>
<tr>
<td valign="top">

*Your Consumption*: *Units in Use*

</td>
<td valign="top">

Displays the number of capacity units that you've already allocated to the storage and compute resources.

</td>
</tr>
<tr>
<td valign="top">

*Your Consumption*: *Remaining Units*

</td>
<td valign="top">

Displays the number of capacity units that you can still allocate to the storage and compute resources.

</td>
</tr>
</table>

**Information for consumption-based tenants created in SAP BTP only**


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

Displays the total number of capacity units consumed per month by the storage and compute resources you've specified.

</td>
</tr>
</table>

