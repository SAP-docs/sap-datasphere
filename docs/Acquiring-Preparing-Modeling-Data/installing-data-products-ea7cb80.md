<!-- loioea7cb802cbea47b39a441888873c3a49 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Installing Data Products

Use the catalog *Data Product* collection to view data products for use in your modeling and other projects. You can see detailed metadata for each data product and if you have the appropriate permissions, install it to an SAP Datasphere space.



<a name="loioea7cb802cbea47b39a441888873c3a49__prereq_fcb_p1y_tyb"/>

## Prerequisites

Your SAP Datasphere system must be part of an SAP Business Data Cloud formation \(see [Integrating Data from SAP Business Data Cloud](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/8f9c3725cfe84e08b3e951e7af06ce57.html "Users with an SAP Business Data Cloud administrator role can install intelligent applications to SAP Datasphere and activate data packages to allow modelers to work with data products.") :arrow_upper_right:\).

A user with an administrator role must choose the spaces to which the data product can be installed \(see [Authorize Spaces to Install SAP Business Data Cloud Data Products](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/67ec785b5de842488781f20c4ab52a9f.html "An SAP Datasphere administrator must choose the spaces to which SAP Business Data Cloud data products from an activated data package can be installed.") :arrow_upper_right:\).

To search for and evaluate objects in the *Data Products* collection, you must have

-   A global role that grants you the following privileges:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Catalog Asset* \(`–R–––--`\) - To access the catalog and view objects in the *Assets* and *Data Products* collections.

-   A scoped role that grants you access to the space or spaces where you can install data products, with the following privileges :
    -   *Spaces* \(`–R–––--`\) - To access a space.
    -   *Space Files* \(`CRUD–--`\) - To install data products to or uninstall data products from a space.
    -   *Data Warehouse Data Builder* \(`CRUD–--`\) - To create, edit, or remove objects in the *Data Builder*.


The *Catalog User* global role and the *DW Modeler* scoped role template, applied together for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

<a name="concept_bx2_pkv_zcc"/>

<!-- concept\_bx2\_pkv\_zcc -->

## Evaluating a Data Product

Data products are high-quality, coherent data sets that you can use via APIs in various SAP or third-party products across different data regions to help you make better business decisions. A single data product can include business objects, entities, analytic data, and more. On the search page in the SAP Datasphere catalog, select the *Data Products* collection and then select one or more filters to narrow the search results. These data products are from tenants that are part of SAP Business Data Cloud formations.

To know for sure if a data product will meet your needs, you can view its details to evaluate how it can help you. Some of the information that you can review includes properties about the data product, like its name and the data provider, the list of entities within the data product, and links to resources for how to use it \(see [Data Product Details](data-product-details-71f4d15.md)\).

After you've evaluated and found a data product, you can install it in your space \(see steps below\).

> ### Note:  
> If you're an administrator for SAP Business Data Cloud, you can access the catalog from the SAP Business Data Cloud cockpit to share the data product to an SAP or partner system \(see [Sharing Data Products to Target Systems](https://help.sap.com/docs/business-data-cloud/governing-and-publishing-data-in-catalog/sharing-data-products-to-sap-databricks) in the SAP Business Data Cloud documentation\).

<a name="dataproduct_installdspspace"/>

<!-- dataproduct\_installdspspace -->

## Installing a Data Product to an SAP Datasphere Space



<a name="dataproduct_installdspspace__context_hzr_g2n_gcc"/>

## Context

Data products that have both an *Active* release status and *Current* functional status can be installed to an SAP Datasphere space by selecting the appropriate API. Data products with a release status of *Inactive* cannot be installed. Ask your administrator for help.

The following diagram displays the flow for data products.

![](images/SAP_Buiness_Data_Cloud_Overview_024dbaa.png)



<a name="dataproduct_installdspspace__steps_zsy_dfn_gcc"/>

## Procedure

1.  In the side navigation area, click <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\)** \> **<span class="FPA-icons-V3"></span> \(*Search*\).

2.  In the SAP Datasphere catalog, search for a data product by entering a portion of its name in the search field or use the filters. For more information, see [Searching for Data Products and Assets in the Catalog](searching-for-data-products-and-assets-in-the-catalog-1047825.md).

3.  When you find the data product you want, check that the release status is *Active*, the lifecycle status is *Active*, and the functional status is *Current*, and then select it.

    On its details page, you can review the list of APIs by choosing the tab *Overview* \> *Details*.

4.  For the row you want, check that the functional status is *Current*, and then select the *Install* action, and the *Import Entities* wizard will open.

    > ### Tip:  
    > If you're reviewing the details of a particular API, you can select the *Install* button from the API details page.

    > ### Note:  
    > Data products with outdated APIs cannot be installed. If the functional status of one or more of its APIs is *Outdated*, try waiting a few moments and then refresh the details page. If the APIs are still outdated, ask your administrator for help.

5.  Select a target space and select *Next Step*.

6.  On the *Review Entities* page, review the entities that you will import and then choose the appropriate data access method.

    -   *Remote Tables* - Federated access guarantees data freshness, but may reduce performance.
    -   *Replication flow to Local Tables* - Replication improves performance, but the freshness of your data will depend on your replication schedule.

    You'll be able to see a list of all the objects that will be created in the *Data Builder*.

7.  Select *Start Import and Deploy*.

    A notification is sent immediately, and this notification will update as the import process continues. After the import completes, you will have two notifications.

    -   Select the first notification to see the imported entities listed in the <span class="SAP-icons-V5"></span> \(*Repository Explorer*\).
    -   Select the second notification to view the import log messages.

        If any entity could not be created, an error is given.





<a name="dataproduct_installdspspace__result_cbk_bhn_gcc"/>

## Results

The data product objects \(including any custom fields defined in the source system\) are created and deployed in the ingestion space and shared with your space.

-   Navigate to the objects in the *Repository Explorer* and review the data based on the data access method you selected.
    -   *Remote Tables*: By default, data is only federated. To replicate the data, open the *Data Integration Monitor* \(see [Replicating Data and Monitoring Remote Tables](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html "In the Remote Tables monitor, you can find a remote table monitor per space. Here, you can copy data from remote tables that have been deployed in your space into SAP Datasphere, and you can monitor the replication of the data. You can copy or schedule copying the full set of data from the source, or you can set up replication of data changes in real-time via change data capturing (CDC).") :arrow_upper_right:\).
    -   *Replication flow to Local Tables*: Open the replication flow and run it \(or create a schedule\) to replicate the data \(see [Run a Replication Flow](Acquiring-and-Preparing-Data-in-the-Data-Builder/run-a-replication-flow-98a26b2.md)\).

-   View and work with the objects in the <span class="FPA-icons-V3"></span> \(*Data Builder*\). Select the space where the data product was installed. To work with the objects, see [Preparing Data](https://help.sap.com/viewer/ac696daa26f0413db39626bc2971e6c2/DEV_CURRENT/en-US/a43c8134d5df4f869d63a2976df9ed94.html "Users with a modeler role can use views and intelligent lookups in the Data Builder to combine, clean, and otherwise prepare data.") :arrow_upper_right: and [Modeling Data in the Data Builder](Modeling-Data-in-the-Data-Builder/modeling-data-in-the-data-builder-5c1e3d4.md).

<a name="concept_bm3_rhz_4gc"/>

<!-- concept\_bm3\_rhz\_4gc -->

## Updating Custom Fields for a Data Product

When you install an intelligent application via SAP Business Data Cloud, any required data products are installed in an ingestion space, but these data products don't include any custom fields defined in the source system \(see [Reviewing Installed Intelligent Applications](https://help.sap.com/docs/SAP_DATASPHERE/be5967d099974c69b77f4549425ca4c0/644648756d334daaaf35d4fc9a0feeda.html)\).

However, you can update these data products to include any required custom fields by reinstalling them as part of the extension process explained in [Extending Intelligent Applications](https://help.sap.com/docs/SAP_DATASPHERE/be5967d099974c69b77f4549425ca4c0/3c158685865d4b408938a148e828e21f.html) in the SAP Business Data Cloud documentation. From time to time, users might add or remove custom fields, or they might change existing custom fields. To ensure that the data products you installed have the latest updates to the custom fields, you must uninstall and then reinstall the data product.

During its lifecycle, a data product might have patch, minor version, and major version updates. Any custom fields defined in the source system are available as follows:

-   Patch or a minor version update: Any custom fields defined in the source system will continue to be available.
-   Major version update: Any custom fields defined in the source system will no longer be available and they must be added again.

<a name="task_zbr_nl5_gfc"/>

<!-- task\_zbr\_nl5\_gfc -->

## Modifying the Data Access for a Data Product



<a name="task_zbr_nl5_gfc__context_ygp_pl5_gfc"/>

## Context

When selecting a data access method, you will consider both storage and processing time costs and data freshness. You can at any time change the data access method for your data product.



## Procedure

1.  In the side navigation area, click <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\)** \> **<span class="FPA-icons-V3"></span> \(*Search*\).

2.  In the SAP Datasphere catalog, search for a data product by entering a portion of its name in the search field or use the filters. For more information, see [Searching for Data Products and Assets in the Catalog](searching-for-data-products-and-assets-in-the-catalog-1047825.md).

3.  When you find the data product you want, reinstall it.

    On the *Review Entities* page of the wizard, remember to switch the data access method to the one you want.


<a name="dataproduct_uninstalldspspace"/>

<!-- dataproduct\_uninstalldspspace -->

## Uninstalling a Data Product from an SAP Datasphere Space



<a name="dataproduct_uninstalldspspace__prereq_e1l_clv_s2c"/>

## Prerequisites

Remove all dependent objects for the data product before you uninstall a data product \(API\) from your SAP Datasphere space.



<a name="dataproduct_uninstalldspspace__context_apk_bqx_t2c"/>

## Context

If you no longer need a data product in a particular space, you can uninstall it.

> ### Note:  
> If the lifecycle status of a data product changes so that the data product is no longer active, the data product might not be visible in the catalog. For example, when the status of a custom Delta Share data product \(that was created in the Data Sharing Cockpit\) changes from *Listed* to *Delisted*, the data product will not appear in the catalog. If you can't find the data product that you want to uninstall, contact your administrator. For more information about custom Delta Share data products, see [Creating Custom Delta Share Data Products](https://help.sap.com/viewer/bb1899f0b39f415b9de29a845873d7af/DEV_CURRENT/en-US/b07e95d07a1e4569b87d9bb57b732bcf.html "Create a custom data product on a Delta Share runtime. This custom data product can then be shared with any system in the formation that supports it, such as SAP Databricks.") :arrow_upper_right: in the **Data Marketplace - Data Provider's Guide**.



## Procedure

1.  In the side navigation area, click <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\)** \> **<span class="FPA-icons-V3"></span> \(*Search*\).

2.  In the SAP Datasphere catalog, search for the data product by entering a portion of its name in the search field or use the filters. For more information, see [Searching for Data Products and Assets in the Catalog](searching-for-data-products-and-assets-in-the-catalog-1047825.md).

3.  When you find the data product you want to remove, select it to open its details page.

4.  Select *Overview* \> *Details* to see all available data product APIs.

5.  Find the API that you want to uninstall and select *Uninstall*.

    The dialog that appears shows a list of all spaces where the data product is installed. If any objects in a space still depend on the data product, preventing its removal, a note is displayed for that space.


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Steps
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Space with no dependent objects**
    
    </td>
    <td valign="top">
    
    1.  Select a system.
    2.  In the confirmation dialog, select *Uninstall* to uninstall the data product from that space.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Space with dependent objects**
    
    </td>
    <td valign="top">
    
    1.  Select a system to see all dependent objects.
    2.  To remove a single dependent object, select it, which opens it, and then delete it.
    3.  To remove several dependent objects, select the *View in Repository Explorer* button, which opens the *Repository Explorer*, and then delete all dependent objects.
    4.  After all dependent objects are removed, go back to the data product and uninstall it from the space.


    
    </td>
    </tr>
    </table>
    



<a name="dataproduct_uninstalldspspace__result_vdd_wfl_rgc"/>

## Results

After the data product is uninstalled, you'll get a notification. The data product is uninstalled as follows:

-   A data product that is installed to multiple spaces is only uninstalled from the selected space. The data product remains in the ingestion space where it is still available to the other spaces where it's installed.
-   A data product that is installed to only one space is uninstalled from the selected space and removed from the ingestion space. Furthermore, if the data product being uninstalled is also the only data product in the ingestion space, the ingestion space will be removed.

**Related Information**  


[Authorize Spaces to Install SAP Business Data Cloud Data Products](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/67ec785b5de842488781f20c4ab52a9f.html "An SAP Datasphere administrator must choose the spaces to which SAP Business Data Cloud data products from an activated data package can be installed.") :arrow_upper_right:

[Importing Entities with Semantics from SAP S/4HANA](Acquiring-and-Preparing-Data-in-the-Data-Builder/importing-entities-with-semantics-from-sap-s-4hana-845fedb.md "You can use the Import Entities wizard to load metadata from your SAP S/4HANA Cloud and SAP S/4HANA on-premise connections via semantically-rich objects. The wizard creates Business Builder and Data Builder entities (along with all the objects on which they depend) in SAP Datasphere.")

