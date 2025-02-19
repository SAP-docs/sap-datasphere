<!-- loioea7cb802cbea47b39a441888873c3a49 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Evaluating and Installing SAP Business Data Cloud Data Products

When you find an SAP Business Data Cloud data product that interests you, you can view information about it to make sure it’s the right one for your business needs. You can then install it in your SAP Datasphere space.



<a name="loioea7cb802cbea47b39a441888873c3a49__prereq_fcb_p1y_tyb"/>

## Prerequisites

To search for and view the details of a data product, you must be assigned one of the following:

-   The *Catalog User* role
-   A custom role with the *Read* permission for *Catalog Asset*

To install the data product to a space and then use it, the following must already be set up:

-   An SAP Datasphere administrator must choose the spaces to which the data product can be installed \(see [Defining Allowed Spaces for Unified Customer Landscape Connections](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/67ec785b5de842488781f20c4ab52a9f.html "For remote systems that are integrated with SAP Datasphere in the Unified Customer Landscape, connections are generated in SAP Datasphere. These generated connections are not assigned to any spaces yet. In the Configuration tool, users with an administrator role can control which spaces users with an integrator role can add the connection to. Once added to a space, space users can use the connection to replicate data with replication flows from the remote systems.") :arrow_upper_right:\)
-   You must additionally be assigned one of the following:
    -   The *DW Modeler* or *DW Space Administrator* role
    -   A custom role with the following settings. This custom role can be the same role that has the *Catalog Asset* privilege set:
        -   *Read* permission for *Spaces*
        -   *Create*, *Read*, *Update*, and *Delete* permissions for *Space Files*
        -   *Create*, *Read*, and *Update* for *Data Warehouse Data Builder*



<a name="concept_bx2_pkv_zcc"/>

<!-- concept\_bx2\_pkv\_zcc -->

## Evaluating an SAP Business Data Cloud Data Product

SAP Business Data Cloud data products are high-quality, coherent data sets that you can use via APIs in various SAP or third-party products across different data regions to help you make better business decisions. A single data product contains a coherent set of data that can include business objects, entities, analytic data, and more.

On the catalog search page, you can discover data products by selecting the **SAP Business Data Cloud***Data Products* filter. To further narrow your focus, enter part of a data product's name and search for it or apply filters.

When you find a data product, review its details page to learn more about it. You'll see summary information about the data product, like its name and the data provider, the list of entities within the data product, and links to resources for how to use it \(see [SAP Business Data Cloud Data Product Details](sap-business-data-cloud-data-product-details-71f4d15.md)\).

After you've evaluated the data product and decide it's the one you need, you can install it to your space \(see steps below\).

<a name="task_abn_f2n_gcc"/>

<!-- task\_abn\_f2n\_gcc -->

## Installing an SAP Business Data Cloud Data Product to an SAP Datasphere Space



<a name="task_abn_f2n_gcc__context_hzr_g2n_gcc"/>

## Context

After you decide that the data product is what you need and checked that it has an active status, you can install it to an SAP Datasphere space by selecting the appropriate API. If the data product is inactive, ask your administrator for help.

The following diagram displays the flow for data products.

![](images/BDC_diagram_-_no_DBX_data_packages_only_56bce1b.png)



<a name="task_abn_f2n_gcc__steps_zsy_dfn_gcc"/>

## Procedure

1.  In the side navigation area, click <span class="SAP-icons-V5"></span>\(*Catalog*\).

2.  On the catalog search page, search for a data product by entering a portion of its name or use the filters. For more information, see [Finding Data and Assets in the Catalog](finding-data-and-assets-in-the-catalog-1047825.md).

3.  When you find the data product you want, check that it has an active status and select it, to open its details page.

    You can review the list of APIs by choosing the tab *Overview* \> *Details*.

4.  For the row you want, select the *Install* button.

    The *Import Entities* wizard opens.

    > ### Tip:  
    > If you're reviewing the details of a particular API, you can select the *Install* button from the API details page.

5.  Select a target space and select *Next Step*.

6.  On the *Review Entities* page, review the entities that you will import.

    You'll be able to see a list of all the objects that will be created in SAP Datasphere *Data Builder*.

7.  Select *Start Import and Deploy*.

    A notification is sent immediately, and this notification will update as the import process continues. After the import completes, you will have two notifications.

    -   Select the first notification to see the imported entities listed in the <span class="SAP-icons-V5"></span> \(*Repository Explorer*\).
    -   Select the second notification to view the import log messages.

        If any entity could not be created, an error is given.





<a name="task_abn_f2n_gcc__result_cbk_bhn_gcc"/>

## Results

The data product objects are created and deployed in the ingestion space and shared with your space:

-   You can view the objects in the *Repository Explorer*.
-   You can view and work with them in the <span class="FPA-icons-V3"></span> \(*Data Builder*\). Select the space where the data product was installed to. To work with the objects, see [Preparing Data in the Data Builder](https://help.sap.com/viewer/ac696daa26f0413db39626bc2971e6c2/DEV_CURRENT/en-US/a43c8134d5df4f869d63a2976df9ed94.html "Users with a modeler role can use views and intelligent lookups in the Data Builder to combine, clean, and otherwise prepare data.") :arrow_upper_right: and [Modeling Data in the Data Builder](Modeling-Data-in-the-Data-Builder/modeling-data-in-the-data-builder-5c1e3d4.md).
-   In the catalog, users can discover the objects. Select the *Assets* tab and use the filters or the search to find the objects. The objects are discoverable only if an authenticated system user for the source system has access permission to the space where the data product was installed. For more information about automatic extraction, see [Understanding Different Methods for Extracting Metadata](https://help.sap.com/viewer/97d1d2f0e35d410c893e95a5ff3bee6f/DEV_CURRENT/en-US/b4f364186a9a4dddbd3f757d89decf94.html "Depending on the type of source system connected to the catalog, metadata for data and assets is extracted automatically or manually. These different methods help you ensure that the data and assets in the catalog are up-to-date.") :arrow_upper_right:.

    > ### Note:  
    > If the entity has a replication flow, two objects are created: one object is created by the replication flow \(a delta object\), and the other object is the actual object that is used as part of the installation of the data product. Both objects will have the same business name, but the technical name will be different. The delta object's name is appended with "\_Delta".


**Related Information**  


[Defining Allowed Spaces for Unified Customer Landscape Connections](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/67ec785b5de842488781f20c4ab52a9f.html "For remote systems that are integrated with SAP Datasphere in the Unified Customer Landscape, connections are generated in SAP Datasphere. These generated connections are not assigned to any spaces yet. In the Configuration tool, users with an administrator role can control which spaces users with an integrator role can add the connection to. Once added to a space, space users can use the connection to replicate data with replication flows from the remote systems.") :arrow_upper_right:

[Importing Entities with Semantics from SAP S/4HANA](Acquiring-and-Preparing-Data-in-the-Data-Builder/importing-entities-with-semantics-from-sap-s-4hana-845fedb.md "You can use the Import Entities wizard to load metadata from your SAP S/4HANA Cloud and SAP S/4HANA on-premise connections via semantically-rich objects. The wizard creates Business Builder and Data Builder entities (along with all the objects on which they depend) in SAP Datasphere.")

