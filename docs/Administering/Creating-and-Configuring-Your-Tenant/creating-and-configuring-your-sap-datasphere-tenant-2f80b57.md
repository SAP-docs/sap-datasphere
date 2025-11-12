<!-- loio2f80b57359254b5cbb4faac794ade90c -->

# Creating and Configuring Your SAP Datasphere Tenant

Creating and Configuring Your SAP Datasphere Tenant: Learn how to create and configure your own tenant in SAP BTP, select a data center region, and distribute workloads across availability zones. This information is essential for managing and optimizing your data center infrastructure.

You can create your own tenant in the SAP BTP Cockpit. The procedure is the same for both subscription-based and consumption-based contracts. Some details may vary depending on the chosen service plan \(free or standard\). For more information about limitations for a free plan, see SAP Note [3227267](https://launchpad.support.sap.com/#/notes/3227267).

When the tenant is configured, a data center region is selected. The main role of a data center is to guarantee the uninterrupted operation of computer systems. It also provides secure storage, processing, and networking capabilities for your data. A data center refers to the physical location, which could be a building or a group of buildings, housing computer systems and their components.

Each data center region has multiple availability zones. Your workloads are deployed in these various zones. By distributing workloads across different zones, we ensure our services remain available, even if a specific zone experiences issues. By keeping backup data within the same data center zone, the latency for data transfers and access is minimized. This infrastructure strategy balances the workload and enhances performance. The zone deployment contributes to a more robust and reliable infrastructure, ensuring near-zero downtime for your critical processing needs.


<table>
<tr>
<th valign="top">

Characteristics

</th>
<th valign="top">

Standard Plan

</th>
<th valign="top">

Free Plan

</th>
</tr>
<tr>
<td valign="top">

**Provisioning** 

</td>
<td valign="top">

-   For information about region availability, see the [SAP Discovery Center](https://discovery-center.cloud.sap/serviceCatalog/sap-data-warehouse-cloud).
-   The SAP BTP subaccount administrator must trigger the SAP Datasphere instance creation. Tenant creation will not be triggered by SAP.
-   You must create and configure the to-be-provisioned SAP Datasphere service instance \(tenant\) in SAP BTP. See [Create Your SAP Datasphere Service Instance in SAP BTP](create-your-sap-datasphere-service-instance-in-sap-btp-54288aa.md).

-   The system owner of SAP Datasphere, who has been specified during the provisioning, is notified via email when the tenant is provisioned.



</td>
<td valign="top">

-   For information about region availability, see the [SAP Discovery Center](https://discovery-center.cloud.sap/serviceCatalog/sap-data-warehouse-cloud).
-   The SAP BTP subaccount administrator must trigger the SAP Datasphere instance creation. Tenant creation will not be triggered by SAP.
-   You must create and configure the to-be-provisioned SAP Datasphere service instance \(tenant\) in SAP BTP. See [Create Your SAP Datasphere Service Instance in SAP BTP](create-your-sap-datasphere-service-instance-in-sap-btp-54288aa.md).

-   The system owner of SAP Datasphere, who has been specified during the provisioning, is notified via email when the tenant is provisioned.



</td>
</tr>
<tr>
<td valign="top">

**Size Configuration**

> ### Note:  
> For maximum size configuration options, see the tables below.



</td>
<td valign="top">

-   Tenants are initially created with minimal configuration that includes 128 GB of storage and 32 GB of memory \(2 compute blocks\).
-   Once logged to your tenant, upscaling can be done at any time. See [Configure the Size of Your SAP Datasphere Tenant](configure-the-size-of-your-sap-datasphere-tenant-33f8ef4.md).

    > ### Note:  
    > After finalizing the configuration, you can only change the size of your SAP BW Bridge storage later if you don’t have any SAP BW Bridge instances.


To view all supported size combinations, go to the [SAP Datasphere Capacity Unit Estimator](https://datasphere-estimator-sac-saceu10.cfapps.eu10.hana.ondemand.com/).

</td>
<td valign="top">

-   Tenants are created with 128 GB of storage and 32 GB of memory \(2 compute blocks\).
-   You cannot upscale free plan tenants. You need to update your plan from free to standard if any sizing configuration is required.



</td>
</tr>
<tr>
<td valign="top">

**Metering** 

</td>
<td valign="top">

-   The number of consumed capacity units is reported on a hourly basis to your SAP BTP account.




</td>
<td valign="top">

:

-   The usage of a free plan tenant is reported to your SAP BTP account, but SAP does not charge you for using this tenant.




</td>
</tr>
<tr>
<td valign="top">

**Time Limitation** 

</td>
<td valign="top">

-   **Subscription Contract**: dependent on the contract.
-   **Consumption Based Contract**: no time limitation.



</td>
<td valign="top">

:

The time limitation is 90 days and the trial duration cannot be extended.

You can update the tenant from free to standard plan before the 90-day expiration \(the number of days before the expiration is displayed in the top panel of the SAP Datasphere free-plan tenant\).

If you do not perform the update within 90 days, the tenant is automatically deleted. The remaining service instance cannot be reused and should be deleted at any time by an administrator of your SAP BTP account.

See [Update Your Free Plan to Standard Plan in SAP BTP](update-your-free-plan-to-standard-plan-in-sap-btp-f173be2.md).

</td>
</tr>
<tr>
<td valign="top">

**Number of tenants** 

</td>
<td valign="top">

No limitation.

In the case of a subscription contract, the available capacity units can be distributed among all your tenants.

</td>
<td valign="top">

1 per SAP BTP global account.

</td>
</tr>
</table>



<a name="loio2f80b57359254b5cbb4faac794ade90c__section_vdz_s2c_yxb"/>

## Maximum Configuration Values

The maxium configuration size of your tenant depends on regional availability and your server type.

> ### Note:  
> -   Data integration includes 200h/month from the minimum free package.
> -   Catalog includes 0.5 GB/h from the minimum free package.

**Amazon Web Services \(AWS\)**


<table>
<tr>
<th valign="top">

Hyperscaler Regional Availability

</th>
<th valign="top">

Memory

</th>
<th valign="top">

Storage

</th>
<th valign="top">

BW Bridge

</th>
<th valign="top">

Data Lake

</th>
<th valign="top">

Data Integration

</th>
<th valign="top">

Catalog

</th>
<th valign="top">

vCPU

</th>
</tr>
<tr>
<td valign="top">

Australia

</td>
<td valign="top">

5970 GB

</td>
<td valign="top">

16000 GB

</td>
<td valign="top">

4096 GB

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

440 \(Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Brazil \(São Paulo\)

</td>
<td valign="top">

5970 GB

</td>
<td valign="top">

16000 GB

</td>
<td valign="top">

4096 GB

</td>
<td valign="top">

Not Supported

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

440 \(Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Canada \(Montreal\)

</td>
<td valign="top">

5970 GB

</td>
<td valign="top">

16000 GB

</td>
<td valign="top">

4096 GB

</td>
<td valign="top">

Not Supported

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

440 \(Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Europe \(Frankfurt\)

</td>
<td valign="top">

12000 GB

</td>
<td valign="top">

61440 GB

</td>
<td valign="top">

4096 GB

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

442 \(High Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

EU Access \(Frankfurt\)

</td>
<td valign="top">

5970 GB

</td>
<td valign="top">

16000 GB

</td>
<td valign="top">

4096 GB

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

440 \(Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Japan \(Tokyo\)

</td>
<td valign="top">

5970 GB

</td>
<td valign="top">

16000 GB

</td>
<td valign="top">

4096 GB

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

440 \(Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Singapore

</td>
<td valign="top">

5970 GB

</td>
<td valign="top">

16000 GB

</td>
<td valign="top">

4096 GB

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

440 \(Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

South Korea

</td>
<td valign="top">

5970 GB

</td>
<td valign="top">

16000 GB

</td>
<td valign="top">

4096 GB

</td>
<td valign="top">

Not Supported

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

440 \(Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

US East

</td>
<td valign="top">

12000 GB

</td>
<td valign="top">

61440 GB

</td>
<td valign="top">

4096 GB

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

442 \(High Memory Performance Class\)

</td>
</tr>
</table>

**Microsoft Azure**


<table>
<tr>
<th valign="top">

Hyperscaler Regional Availability

</th>
<th valign="top">

Memory

</th>
<th valign="top">

Storage

</th>
<th valign="top">

BW Bridge

</th>
<th valign="top">

Data Lake

</th>
<th valign="top">

Data Integration

</th>
<th valign="top">

Catalog

</th>
<th valign="top">

vCPU

</th>
</tr>
<tr>
<td valign="top">

Brazil

</td>
<td valign="top">

5600 GB

</td>
<td valign="top">

27840 GB

</td>
<td valign="top">

Supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

412 \(Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Canada

</td>
<td valign="top">

5600 GB

</td>
<td valign="top">

27840 GB

</td>
<td valign="top">

Not Supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

412 \(Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Europe \(Amsterdam\)

</td>
<td valign="top">

11150 GB

</td>
<td valign="top">

55760 GB

</td>
<td valign="top">

Supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

412 \(Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Europe \(Switzerland\)

</td>
<td valign="top">

5600 GB

</td>
<td valign="top">

27840 GB

</td>
<td valign="top">

Supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

412 \(Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

US West

</td>
<td valign="top">

11150 GB

</td>
<td valign="top">

55760 GB

</td>
<td valign="top">

Supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

412 \(Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

US East

</td>
<td valign="top">

5600 GB

</td>
<td valign="top">

27840 GB

</td>
<td valign="top">

Supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

412 \(Memory Performance Class\)

</td>
</tr>
</table>

**Google Cloud Platform \(GCP\)**


<table>
<tr>
<th valign="top">

Hyperscaler Regional Availability

</th>
<th valign="top">

Memory

</th>
<th valign="top">

Storage

</th>
<th valign="top">

BW Bridge

</th>
<th valign="top">

Data Lake

</th>
<th valign="top">

Data Integration

</th>
<th valign="top">

Catalog

</th>
<th valign="top">

vCPU

</th>
</tr>
<tr>
<td valign="top">

Australia

</td>
<td valign="top">

3700 GB

</td>
<td valign="top">

28928 GB

</td>
<td valign="top">

Supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

204 \(High Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Brazil

</td>
<td valign="top">

5750 GB

</td>
<td valign="top">

28928 GB

</td>
<td valign="top">

Supported

</td>
<td valign="top">

90TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

124 \(High Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Europe \(Frankfurt\)

</td>
<td valign="top">

11520 GB

</td>
<td valign="top">

28928 GB

</td>
<td valign="top">

Supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

412 \(High Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

India \(Mumbai\)

</td>
<td valign="top">

5750 GB

</td>
<td valign="top">

28928 GB

</td>
<td valign="top">

Supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

204 \(High Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Israel

</td>
<td valign="top">

3700 GB

</td>
<td valign="top">

28928 GB

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

124 \(High Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Japan

</td>
<td valign="top">

5750 GB

</td>
<td valign="top">

28928 GB

</td>
<td valign="top">

Supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

204 \(High Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Saudi Arabia

> ### Note:  
> Only available to customers representing critical national infrastructure or the public sector.



</td>
<td valign="top">

5750 GB

</td>
<td valign="top">

28928 GB

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

204 \(High Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

Saudi Arabia

> ### Note:  
> Available to non-regulated customers.



</td>
<td valign="top">

5750 GB

</td>
<td valign="top">

28928 GB

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

204 \(High Memory Performance Class\)

</td>
</tr>
<tr>
<td valign="top">

US Central

</td>
<td valign="top">

11520 GB

</td>
<td valign="top">

28928 GB

</td>
<td valign="top">

Supported

</td>
<td valign="top">

90 TB

</td>
<td valign="top">

7200 h/month

</td>
<td valign="top">

20.5 GB/h

</td>
<td valign="top">

412 \(High Memory Performance Class\)

</td>
</tr>
</table>

