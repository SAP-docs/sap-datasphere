<!-- loio8f9c3725cfe84e08b3e951e7af06ce57 -->

# Integrating Data from SAP Business Data Cloud

SAP Business Data Cloud is a fully managed SaaS solution that unifies and governs all SAP data and seamlessly connects with third-party data—giving line-of-business leaders context to make even more impactful decisions.



<a name="loio8f9c3725cfe84e08b3e951e7af06ce57__section_dsp_in_bdc"/>

## SAP Datasphere in SAP Business Data Cloud

If your SAP Datasphere tenant is part of an SAP Business Data Cloud formation, then the SAP Business Data Cloud administrator can activate data packages to allow the contained data products to be installed in SAP Datasphere.

![](images/BDC_diagram_-_expanded_BDX_BDC_on_the_bottom_with_DBX_024dbaa.png)

For detailed information, see the [SAP Business Data Cloud](https://help.sap.com/docs/SAP_BUSINESS_DATA_CLOUD) documentation.



<a name="loio8f9c3725cfe84e08b3e951e7af06ce57__section_insight_apps"/>

## SAP Business Data Cloud Intelligent Applications

An SAP Business Data Cloud can install intelligent applications to the SAP Datasphere and SAP Analytics Cloud tenants in the formation \(see [Installing Intelligent Applications](https://help.sap.com/docs/SAP_BUSINESS_DATA_CLOUD/f7acf8c9dad54e99b5ce5ebc633ed8e1/35b64d44efd54502a935f67ba66ffd4e.html) in the *SAP Business Data Cloud* documentation\).

When an intelligent application is installed:

-   SAP-managed spaces are created in SAP Datasphere to contain the intelligent application content.
-   Replication flows, tables, views, and analytic models are created in these spaces to ingest, prepare and expose the required data to SAP Analytics Cloud.

![](images/BDC_diagram_-_with_DBX_only_insight_apps_9d8148a.png)

SAP Datasphere users can work with intelligent application content in the following ways:

-   Review the installed content \(see [Reviewing Installed Intelligent Applications](reviewing-installed-intelligent-applications-6446487.md)\).
-   Upload permissions records to control access to the data \(see [Applying Row-Level Security to Data Delivered through Intelligent Applications](applying-row-level-security-to-data-delivered-through-intelligent-applications-c83225f.md)\).
-   Build on top of the delivered data products and content to extend the app \(see [Extending Intelligent Applications](extending-intelligent-applications-3c15868.md)\)



<a name="loio8f9c3725cfe84e08b3e951e7af06ce57__section_data_products"/>

## SAP Business Data Cloud Data Products

An SAP Business Data Cloud can activate data packages to allow the contained data products to be installed in SAP Datasphere \(see [Activating Data Packages](https://help.sap.com/docs/SAP_BUSINESS_DATA_CLOUD/f7acf8c9dad54e99b5ce5ebc633ed8e1/fcf9975b49ea4adeb837e4be16116175.html) in the *SAP Business Data Cloud* documentation\).

![](images/with_DBX_only_data_packages_6c65420.png)

When a data package is activated, SAP Datasphere users can work with data products in the following ways:

-   An SAP Datasphere administrator must choose the spaces to which data products from the originating SAP system can be installed \(see [Authorize Spaces to Install SAP Business Data Cloud Data Products](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/67ec785b5de842488781f20c4ab52a9f.html "An SAP Datasphere administrator must choose the spaces to which SAP Business Data Cloud data products from an activated data package can be installed.") :arrow_upper_right:\).
-   SAP Datasphere modelers can install data products to their space for use in their modeling projects \(see [Evaluating and Installing Data Products](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/ea7cb802cbea47b39a441888873c3a49.html "Use the catalog Data Product collection to view data products for use in your modeling and other projects. You can see detailed metadata for each data product and if you have the appropriate permissions, install it to an SAP Datasphere space.") :arrow_upper_right:.
-   SAP Datasphere Catalog administrators can share data products to SAP Databricks \(see  <?sap-ot O2O class="- topic/xref " href="09881ade3e20468a98aa90e44f8c44ff.xml" text="" desc="" xtrc="xref:9" xtrf="file:/home/builder/src/dita-all/auy1749630208053/loiob8faae83b519439fb4ea9d0eb1a5f26e_en-US/src/content/localization/en-us/8f9c3725cfe84e08b3e951e7af06ce57.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> \).



<a name="loio8f9c3725cfe84e08b3e951e7af06ce57__section_sap_managed_spaces"/>

## SAP-Managed Spaces

SAP-managed spaces are automatically created to contain the data products and content installed from SAP Business Data Cloud:

-   By default, no users are granted access to these spaces, but a SAP Datasphere administrator can add users to the spaces to monitor data integration and review the content.
-   All the delivered content is SAP-managed, read-only, and cannot be modified as it is protected by a namespace \(see [Namespaces](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/7094f24d272c4ae4893b726095ab969e.html "Content managed by SAP and partners and delivered through SAP Business Data Cloud is protected by namespaces. Any object whose technical name is preceded by a namespace and a dot (for example, sap.s4h.Entity) cannot be edited.") :arrow_upper_right:\).
-   No user can create any objects in SAP-managed spaces.

