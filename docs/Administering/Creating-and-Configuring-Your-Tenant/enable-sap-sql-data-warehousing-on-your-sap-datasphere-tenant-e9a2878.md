<!-- loioe9a287849ccf41bb8a132d12dd3fdc8f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enable SAP SQL Data Warehousing on Your SAP Datasphere Tenant

Use SAP SQL Data Warehousing to build calculation views and other SAP HANA Cloud HDI objects directly in your SAP Datasphere run-time database and then exchange data between your HDI containers and your SAP Datasphere spaces. SAP SQL Data Warehousing can be used to bring existing HDI objects into your SAP Datasphere environment, and to allow users familiar with the HDI tools to leverage advanced SAP HANA Cloud features.



## Context

To enable SAP SQL Data Warehousing on your SAP Datasphere tenant, an S-user must create an SAP ticket to connect your SAP BTP account.

> ### Note:  
> The SAP Datasphere tenant and SAP Business Technology Platform organization and space must be in the same data center \(for example, eu10, us10\). This feature is not available for Free Tier plan tenants \(see SAP Note [3227267](https://me.sap.com/notes/3227267)\).

For information about working with SAP Datasphere and HDI containers, see [Exchanging Data with SAP SQL Data Warehousing HDI Containers](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/1aec7ca95af24208a61c1a444b249d95.html "Users with a space administrator role can use SAP SQL Data Warehousing to build calculation views and other SAP HANA Cloud HDI objects directly in the run-time SAP HANA Cloud database and then exchange data between HDI containers and SAP Datasphere spaces. SAP SQL Data Warehousing can be used to bring existing HDI objects into your SAP Datasphere environment, and to allow users familiar with the HDI tools to leverage advanced SAP HANA Cloud features.") :arrow_upper_right:.



<a name="loioe9a287849ccf41bb8a132d12dd3fdc8f__steps_xxb_cty_tsb"/>

## Procedure

1.  In the side navigation area, click ![](../images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.

2.  In the *HDI Containers* section, click *Enable Access* and then click *Open Ticket* to create an SAP ticket for the `DWC-SM` component to request us to map your SAP Datasphere tenant to your SAP Business Technology Platform account.

3.  Provide the following information:


    <table>
    <tr>
    <th valign="top">

    Item
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Datasphere Tenant ID
    
    </td>
    <td valign="top">
    
    In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> **<span class="FPA-icons-V3"></span> \(*About*\).

    > ### Note:  
    > You need the *Tenant ID* for the ticket, and the *Database ID* when building your containers in the SAP Datasphere run-time database.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Business Technology Platform Org GUID
    
    </td>
    <td valign="top">
    
    Your SAP Business Technology Platform organization ID.

    You can use the Cloud Foundry CLI to find your organization GUID:

    ```
    cf org <ORG> --guid
    ```

    See [https://cli.cloudfoundry.org/en-US/v6/org.html](https://cli.cloudfoundry.org/en-US/v6/org.html).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Business Technology Platform Space GUID
    
    </td>
    <td valign="top">
    
    The SAP Business Technology Platform space inside the organization.

    You can use the Cloud Foundry CLI to find your space GUID:

    ```
    cf space <SPACE> --guid
    ```

    See [https://cli.cloudfoundry.org/en-US/v6/space.html](https://cli.cloudfoundry.org/en-US/v6/space.html).
    
    </td>
    </tr>
    </table>
    
    You will be notified when your ticket has been processed.

4.  Build one or more new HDI containers in the SAP Business Technology Platform Space and they will be created in the SAP Datasphere run-time database \(identified by the *Database ID* on the SAP Datasphere *About* dialog\).

    For information about setting up your build, see [Binding Applications to an SAP HANA Cloud Instance](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-getting-started-guide/binding-applications-to-sap-hana-cloud-instance).

5.  When one or more containers are available in the run-time database, the *Enable Access* button is replaced by the *\+* button in the *HDI Containers* section for all your SAP Datasphere spaces \(see [Add an HDI Container and Access its Objects in Your Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/5d55da5514b240ff8d3a970bf7dc6705.html "To access calculation views and other HDI objects as sources for your views and data flows, you must add the HDI container to your SAP Datasphere space.") :arrow_upper_right:\).


