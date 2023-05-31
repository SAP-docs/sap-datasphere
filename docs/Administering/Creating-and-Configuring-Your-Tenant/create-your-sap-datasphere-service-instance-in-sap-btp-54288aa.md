<!-- loio54288aa4843c4856aba8333742a661ea -->

# Create Your SAP Datasphere Service Instance in SAP BTP

Create your SAP Datasphere service instance in SAP Business Technology Platform.

> ### Note:  
> Creating an SAP Datasphere service instance in SAP Business Technology Platform \(SAP BTP\) results in provisioning an SAP Datasphere tenant.

If you've signed the Cloud Platform Enterprise Agreement \(CPEA\), you can access the SAP BTP cockpit and view all currently available services in a global account. You need to structure this global account into subaccounts and other related artefacts, such as directories and/or spaces.



<a name="loio54288aa4843c4856aba8333742a661ea__section_tl2_gh5_ytb"/>

## Prerequisites

To create your SAP Datasphere service instance in SAP BTP, you need the following prerequites:

-   Your global account has a commercial entitlement via cloud credits \(a consumption-based model\).

-   A Cloud Foundry subaccount which is entitled for SAP Datasphere. For more information, see [Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5ba357b4fa1e4de4b9fcc4ae771609da.html).
-   You have SAP BTP administration authorization on the subaccount that is entitled to SAP Datasphere.

-   You are using Google Chrome to properly view popups in SAP BTP.




<a name="loio54288aa4843c4856aba8333742a661ea__section_i3t_yg5_ytb"/>

## Service Plans


<table>
<tr>
<th valign="top">

Service Plan



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Standard



</td>
<td valign="top">

The standard plan provides an SAP Datasphere tenant for productive and non-productive use, which is represented by a service instance.



</td>
</tr>
<tr>
<td valign="top">

Free



</td>
<td valign="top">

The free plan provides an SAP Datasphere tenant for a limited time for trial use, which is represented by a service instance.



</td>
</tr>
</table>

> ### Note:  
> For information about region availability, see the [SAP Discovery Center](https://discovery-center.cloud.sap/serviceCatalog/sap-data-warehouse-cloud).



<a name="loio54288aa4843c4856aba8333742a661ea__section_t3t_yg5_ytb"/>

## Create a Tenant

The following procedure uses the SAP BTP cockpit to create the service instance.

In the *SAP Datasphere Administration Guide*, we provide high-level steps to create an SAP Datasphere tenant on SAP BTP. For more detailed information, or for instructions that use the Cloud Foundry Command-Line Interface, see the [SAP Business Technology \(SAP BTP\) documentation](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/73beb06e127f4e47b849aa95344aabe1.html).

> ### Note:  
> You can create only one free tenant under the global account.

1.  In the SAP BTP cockpit, navigate to the space in which you want to create the service instance, and click *Services* \> *Service Marketplace* in the left navigation area.

    For more information, see [Navigate to Orgs and Spaces](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5bf87353bf994819b8803e5910d8450f.html?q=Navigate%20to%20orgs%20and%20spaces).

2.  Search for "Datasphere", and click the SAP Datasphere service to open it.
3.  Click *Create* in the top-right corner.

    A wizard opens, in which you can select or specify the following parameters:


    <table>
    <tr>
    <th valign="top">

    Parameter


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">

    *Service*


    
    </td>
    <td valign="top">

    Select SAP Datasphere.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Plan*


    
    </td>
    <td valign="top">

    Select *Standard* or *Free*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Runtime Environment*


    
    </td>
    <td valign="top">

    Select *Cloud Foundry*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Space*


    
    </td>
    <td valign="top">

    \[no selection needed if you're creating the instance from the space area\] Select the SAP BTP space in which you want to create the service instance.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Instance Name*


    
    </td>
    <td valign="top">

    Enter a name to identify your instance \(up to 32 alphanumeric characters, periods, underscores, and hyphens; cannot contain white spaces\).


    
    </td>
    </tr>
    </table>
    
4.  Click *Next* and enter the following information about the SAP Datasphere system owner, who will be notified when the service instance is created: email, first name and last name.

    > ### Note:  
    > Alternatively, you can use a JSON file to provide the information above.

5.  Click *Next* to go to the final page of the wizard where you can review your selections, and then click *Create* to exit the wizard.

    An information message is displayed to confirm that the service instance creation is in progress.

    > ### Note:  
    > The creation of the instance can take a while.

6.  Click *View Instance* to go to your space *Service Instances* page, where the new instance is listed and you can view the progress of its creation.
7.  When the service instance is created, the SAP Datasphere system owner receives an email confirming its availability, and providing a link to navigate to the SAP Datasphere tenant, which the service instance represents.

    > ### Note:  
    > If the creation of the service instance fails \(the "failed" status is displayed\), you must first delete the failed instance and then create a new SAP Datasphere service instance. If you need support, you can open an incident via ServiceNow with the component DS-PROV.


