<!-- loio2f80b57359254b5cbb4faac794ade90c -->

# Creating and Configuring Your SAP Datasphere Tenant

You can request SAP to provision a subscription-based tenant or create your own consumption-based tenant in SAP BTP. In both cases, you then proceed to configure your SAP Datasphere tenant.


<table>
<tr>
<th valign="top">

Characteristics



</th>
<th valign="top">

Subscription-Based Tenant



</th>
<th valign="top">

Consumption-Based Tenant \(Standard Plan or Free Plan\)



</th>
</tr>
<tr>
<td valign="top">

 **Provisioning** 



</td>
<td valign="top">

-   For information about region availability, see the [SAP Discovery Center](https://discovery-center.cloud.sap/serviceCatalog/sap-data-warehouse-cloud).

-   SAP provisions your tenant with the number of capacity units you've purchased, based on your subscription contract.

-   The system owner of SAP Datasphere is notified via email when the tenant is provisioned.




</td>
<td valign="top">

-   For information about region availability, see the [SAP Discovery Center](https://discovery-center.cloud.sap/serviceCatalog/sap-data-warehouse-cloud)

-   You create your SAP Datasphere service instance \(tenant\) in SAP BTP. See [Create Your SAP Datasphere Service Instance in SAP BTP](create-your-sap-datasphere-service-instance-in-sap-btp-54288aa.md).

-   The system owner of SAP Datasphere, who's been specified during the provisioning step, is notified via email when the tenant is provisioned.

-   For information about limitations for a free plan, see SAP note [3227267](https://launchpad.support.sap.com/#/notes/3227267).




</td>
</tr>
<tr>
<td valign="top">

 **Size Configuration** 



</td>
<td valign="top">

-   The minimal configuration provided for SAP Datasphere resources is: 256 GB of storage and 2 compute blocks.

    > ### Note:  
    > For test tenants, the minimal configuration is 128 GB of storage and 1 compute block. With the minimal configuration, you cannot add storage nor SAP BW Bridge storage unless you add more compute blocks.

-   Once logged to your tenant, you must finalize the size configuration of the tenant \(except if provisioned with the minimum number of capacity units: 4300\). See [Configure the Size of Your SAP Datasphere Tenant](configure-the-size-of-your-sap-datasphere-tenant-33f8ef4.md).

    > ### Note:  
    > After finalizing the configuration, you can only change the size of your SAP BW Bridge storage later if you don’t have any SAP BW Bridge instances.

-   At any time, you can increase the sizes of the resources until all the capacity units are allocated. See [Configure the Size of Your SAP Datasphere Tenant](configure-the-size-of-your-sap-datasphere-tenant-33f8ef4.md).

    To view all supported size combinations, go to the [SAP Datasphere Capacity Unit Estimator](https://datasphere-estimator-sac-saceu10.cfapps.eu10.hana.ondemand.com/).




</td>
<td valign="top">

**Standard plan**:

-   The minimal configuration provided for SAP Datasphere resources is: 256 GB of storage and 2 compute blocks.

-   Once logged to your tenant, you can increase the sizes of the resources at any time. See [Configure the Size of Your SAP Datasphere Tenant](configure-the-size-of-your-sap-datasphere-tenant-33f8ef4.md).

    To view all supported size combinations, go to the [SAP Datasphere Capacity Unit Estimator](https://datasphere-estimator-sac-saceu10.cfapps.eu10.hana.ondemand.com/).


**Free plan**:

-   The minimal and only possible configuration provided for SAP Datasphere resources is: 128 GB of storage and 1 compute blocks.

-   Once logged to your tenant, you cannot increase the sizes of the resources \(unless you update your plan from free to standard\).




</td>
</tr>
<tr>
<td valign="top">

 **Metering** 



</td>
<td valign="top">

-   You've already paid for a certain number of capacity units in your contract.




</td>
<td valign="top">

**Standard plan**:

-   The number of consumed capacity units are reported on a monthly basis to your SAP BTP account.


**Free plan**:

-   The usage of a free plan tenant is reported to your SAP BTP account but SAP does not charge you for using this tenant.




</td>
</tr>
<tr>
<td valign="top">

 **Time Limitation** 



</td>
<td valign="top">

-   Dependent on the contract.




</td>
<td valign="top">

**Standard plan**:

-   No time limitation.


**Free plan**:

-   The time limitation is 90 days. You can update the tenant from free to standard plan before the 90-day expiration \(the number of days before the expiration is displayed in the top panel of the SAP Datasphere free-plan tenant\). If you do not perform the update within 90 days, the tenant is automatically deleted. The remaining service instance cannot be reused and should be deleted at any time by an administrator of your SAP BTP account.

    See [Update Your Free Plan to Standard Plan in SAP BTP](update-your-free-plan-to-standard-plan-in-sap-btp-f173be2.md).




</td>
</tr>
<tr>
<td valign="top">

 **Number of tenants** 



</td>
<td valign="top">

-   1




</td>
<td valign="top">

**Standard plan**:

-   No limitation.


**Free plan**:

-   1 per SAP BTP global account.




</td>
</tr>
</table>

