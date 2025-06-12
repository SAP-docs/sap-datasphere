<!-- loio67ec785b5de842488781f20c4ab52a9f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Authorize Spaces to Install SAP Business Data Cloud Data Products

An SAP Datasphere administrator must choose the spaces to which SAP Business Data Cloud data products from an activated data package can be installed.

> ### Note:  
> This procedure only applies to manual data product installation. It doesn't apply to the installation of SAP Business Data Cloud intelligent applications.



<a name="loio67ec785b5de842488781f20c4ab52a9f__section_gk4_vnk_d2c"/>

## Context

SAP systems provide their SAP Business Data Cloud data products to SAP Datasphere via SAP Business Data Cloud formations \(see [Integrate SAP Business Data Cloud Provisioned Systems](https://help.sap.com/docs/SAP_BUSINESS_DATA_CLOUD/f7acf8c9dad54e99b5ce5ebc633ed8e1/d6ec89febd8a40dbb7fb461b60bef289.html) in the *SAP Business Data Cloud* documentation\). When your SAP Datasphere tenant is added to an SAP Business Data Cloud formation, the connections to the source systems of the formation become available in SAP Datasphere. Both systems and connections can be found under <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Business Data Products*.

Before an SAP Datasphere modeler can install data products from an SAP system to any target spaces, an SAP Datasphere administrator must authorize these spaces in <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Business Data Products*.



<a name="loio67ec785b5de842488781f20c4ab52a9f__section_am1_wnk_d2c"/>

## Procedure

1.  In the side navigation area of SAP Datasphere, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Business Data Products*.

2.  \[optional\] Select the system \(with its connection\) and choose *Edit Business Name* to provide a more reasonable business name to the connection.

3.  Select the system and click <span class="SAP-icons-V5"></span> \(Details\) to open the side panel.

4.  In the side panel, choose *Add* to authorize one or more spaces to install data products from the system, and confirm your selection.

5.  To remove one or more spaces from your selection, choose *Remove*.

    > ### Note:  
    > You can only remove a space if no data products are installed in this space \(see the *Data Products Installed* column in the list of selected spaces\).




<a name="loio67ec785b5de842488781f20c4ab52a9f__section_rdk_py3_22c"/>

## Results

An SAP Datasphere modeler installing the data products in the  catalog can select authorized spaces as target spaces \(in the *Import Entities* wizard\). When a data product is installed:

-   The connection is created in an ingestion space if it does not already exist.
-   The data product objects are created and deployed in the ingestion space and shared with the target spaces selected during installation.

For more information, see:

-   [Evaluating and Installing Data Products](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/ea7cb802cbea47b39a441888873c3a49.html "Use the catalog Data Product collection to view data products for use in your modeling and other projects. You can see detailed metadata for each data product and if you have the appropriate permissions, install it to an SAP Datasphere space or share it to Databricks in SAP Business Data Cloud.") :arrow_upper_right:
-   [Business Data Product Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/5661d8813b4c4eb395158cd90e0f4b2f.html "If your SAP Datasphere tenant is included in an SAP Business Data Cloud formation, Business Data Product connections are used to connect to other SAP systems included in the same formation.") :arrow_upper_right:

