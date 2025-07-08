<!-- loioe9a287849ccf41bb8a132d12dd3fdc8f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enable SAP HANA for SQL data warehousing on Your SAP Datasphere Tenant

Use SAP HANA for SQL data warehousing to build calculation views and other SAP HANA Cloud HDI objects directly in your SAP Datasphere run-time database and then exchange data between your HDI containers and your SAP Datasphere spaces. SAP HANA for SQL data warehousing can be used to bring existing HDI objects into your SAP Datasphere environment, and to allow users familiar with the HDI tools to leverage advanced SAP HANA Cloud features.



<a name="loioe9a287849ccf41bb8a132d12dd3fdc8f__prereq_jch_t41_mfc"/>

## Prerequisites

To enable SAP HANA for SQL data warehousing on your SAP Datasphere tenant, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Administration* and *Configuration* areas in the *System* tool.

The *DW Administrator* global role, for example, grants these privileges.For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md).



## Context

To enable SAP HANA for SQL data warehousing on your SAP Datasphere tenant, you must map your tenant to your SAP Business Technology Platform account.

> ### Note:  
> The SAP Datasphere tenant and SAP Business Technology Platform organization and space must be in the same data center \(for example, eu10, us10\). This feature is not available for Free Tier plan tenants \(see SAP Note [3227267](https://me.sap.com/notes/3227267)\).

A tenant may have both Kyma mappings and Cloud Foundry mappings simultaneously. You can also map instances using the Instance Mapping REST API \(see [Create and Manage Instance Mappings Using the REST API](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-administration-guide/creating-and-managing-instance-mappings-using-rest-api) in the *SAP HANA Cloud Administration Guide*\).

For information about working with SAP Datasphere and HDI containers, see [Exchanging Data with SAP HANA for SQL data warehousing HDI Containers](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/1aec7ca95af24208a61c1a444b249d95.html "Users with a space administrator role can use SAP HANA for SQL data warehousing to build calculation views and other SAP HANA Cloud HDI objects directly in the run-time SAP HANA Cloud database and then exchange data between HDI containers and SAP Datasphere spaces. SAP HANA for SQL data warehousing can be used to bring existing HDI objects into your SAP Datasphere environment, and to allow users familiar with the HDI tools to leverage advanced SAP HANA Cloud features.") :arrow_upper_right:.



<a name="loioe9a287849ccf41bb8a132d12dd3fdc8f__steps_xxb_cty_tsb"/>

## Procedure

1.  In the side navigation area, click :wrench: \(*Configuration*\) ** \> *Instance Maping*.

2.  Add a mapping for one of these environment types: Cloud Foundry or Kyma.


    <table>
    <tr>
    <th valign="top">

    Environment Type
    
    </th>
    <th valign="top">

    Environment Instance ID and Group
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Cloud Foundry* 
    
    </td>
    <td valign="top">
    
    Enter the organization and space GUIDs that you are mapping to:

    -   Your SAP Business Technology Platform organization GUID.

        > ### Tip:  
        > You can use the Cloud Foundry CLI to find your organization GUID:
        > 
        > ```
        > cf org <ORG> --guid
        > ```
        > 
        > See [https://cli.cloudfoundry.org/en-US/v6/org.html](https://cli.cloudfoundry.org/en-US/v6/org.html).

    -   \[Optional\] Your SAP Business Technology Platform space inside the organization. If you only specify the organization GUID, the instance is mapped to all spaces in that organization.

        > ### Tip:  
        > You can use the Cloud Foundry CLI to find your space GUID:
        > 
        > ```
        > cf space <SPACE> --guid
        > ```
        > 
        > See [https://cli.cloudfoundry.org/en-US/v6/space.html](https://cli.cloudfoundry.org/en-US/v6/space.html).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Kyma* 
    
    </td>
    <td valign="top">
    
    Enter the cluster ID and namespace that you are mapping to:

    -   Your cluster ID. The cluster ID must be a GUID and the namespace can be no longer than 64 characters. Allowed characters are all lowercase letters, numbers, and dash \(-\).
    -   \[Optional\] Your namespace. If no namespace is provided, the instance is mapped to all namespaces in the cluster.

    > ### Tip:  
    > You can use the following methods to find your cluster ID GUID and your namespace:
    > 
    > 
    > <dl>
    > <dt><b>
    > 
    > kubectl CLI
    > 
    > </b></dt>
    > <dd>
    > 
    > To find your**cluster ID GUID**, run the following command:
    > 
    > ```
    > kubectl get configmap sap-btp-operator-config -n kyma-system -o jsonpath='{.data.CLUSTER_ID}'
    > ```
    > 
    > To find your **namespace**, run the following command:
    > 
    > ```
    > kubectl get namespaces 
    > ```
    > 
    > 
    > 
    > </dd><dt><b>
    > 
    > Kyma Console
    > 
    > </b></dt>
    > <dd>
    > 
    > 
    > <dl>
    > <dt><b>
    > 
    > Cluster ID GUID
    > 
    > </b></dt>
    > <dd>
    > 
    > 1.  In the left sidebar, click *Namespaces*. Then select *kyma-system* from the main page.
    > 
    > 2.  In the left sidebar, click *Configuration* \> *Config Maps*. Then select *sap-btp-operator-config* from the main page.
    > 
    > 3.  The cluster ID GUID is located on the main page.
    > 
    > 
    > 
    > 
    > </dd><dt><b>
    > 
    > Namespace
    > 
    > </b></dt>
    > <dd>
    > 
    > In the left sidebar, click *Namespaces* to see all namespaces in the Kyma cluster.
    > 
    > 
    > 
    > </dd>
    > </dl>
    > 
    > 
    > 
    > </dd>
    > </dl>


    
    </td>
    </tr>
    </table>
    
    For more information, see [SAP HANA Instance Mapping](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-administration-guide/sap-hana-instance-mapping) in the *SAP HANA Cloud Administration Guide*.

3.  Click the *Save* button to apply your changes.

    Your tenant is mapped to another environment context. You can now create HDI containers outside of SAP Datasphere.

4.  Build one or more new HDI containers in the SAP Business Technology Platform Space and they will be created in the SAP Datasphere run-time database \(identified by the *Database ID* on the SAP Datasphere *About* dialog\).

    For information about setting up your build, see [Binding Applications to an SAP HANA Cloud Instance](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-getting-started-guide/binding-applications-to-sap-hana-cloud-instance).




<a name="loioe9a287849ccf41bb8a132d12dd3fdc8f__postreq_pr2_t51_mfc"/>

## Next Steps

When one or more HDI containers are available in your tenant, users with a space administrator role can work with them \([Exchanging Data with SAP HANA for SQL data warehousing HDI Containers](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/1aec7ca95af24208a61c1a444b249d95.html "Users with a space administrator role can use SAP HANA for SQL data warehousing to build calculation views and other SAP HANA Cloud HDI objects directly in the run-time SAP HANA Cloud database and then exchange data between HDI containers and SAP Datasphere spaces. SAP HANA for SQL data warehousing can be used to bring existing HDI objects into your SAP Datasphere environment, and to allow users familiar with the HDI tools to leverage advanced SAP HANA Cloud features.") :arrow_upper_right:\).

