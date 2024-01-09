<!-- loiof173be27e9cb4c758c0f1fa133d9edda -->

# Update Your Free Plan to Standard Plan in SAP BTP

Update your service instance from free plan to standard plan.

In SAP Business Technology Platform \(SAP BTP\), if you have an SAP Datasphere service instance with a free plan, which you can use for 90 days, you can update it to a standard plan \(no time limitation\) for productive purposes. The number of days before the expiration is displayed in the top panel of SAP Datasphere.

> ### Note:  
> If you do not update to a standard plan within 90 days, your SAP Datasphere tenant will be suspended. While the tenant is suspended, you can still upgrade your service instance from the free to standard plan, but after 5 days of suspension, your tenant will be deleted and there is no way to recover it.
> 
> If your tenant is deleted, the service instance will still be shown in your Global Account, but it is not functional. You can delete it and create a new SAP Datasphere service instance with a free plan.

To do so, you must have SAP BTP administration authorization on the subaccount that is entitled to SAP Datasphere.

1.  In SAP BTP, select the subaccount and the space where the service instance with a free plan was created.

2.  Navigate to *Instances and Subscriptions*.

3.  In the *Service Instances* page, find the SAP Datasphere service instance with the free plan, click the button at the end of the row and select *Update*.

    > ### Note:  
    > After updating your free plan to standard plan, you must wait at least 24 hours before changing the tenant settings on the *Tenant Configuration* page.

4.  In the *Update Instance* dialog, select *standard* and click *Update Instance*.

    You can view the progress of the update. The status of the instance becomes green when the update is completed.

    > ### Note:  
    > The update process takes around 30 minutes, and during this time some features might not work as expected.


