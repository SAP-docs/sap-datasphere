<!-- loioebe9dc05a40c47d3bf8a932120c10609 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Creating Data Products

In addition to the SAP-managed data products made available to you by activating data packages, you can create your own data products with data coming from SAP BW, SAP IBP, or any other source that you connect to SAP Datasphere.



## Create a Data Product

1.  Prepare the data from which you want to create the data product. You must have one or more tables containing data that you want to include in your data product.
2.  Identify a file space that will serve to stage the data tables that will be contained in your data product. If your data is currently in an SAP HANA Database space, you can share the relevant tables to the file space \(see [Sharing Entities and Task Chains to Other Spaces](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/64b318f8afd74bb78467cf56eb44294f.html "Share a table or view to another space to allow users assigned to that space to use it as a source for their objects. Share a task chain to another space to allow it to be added to and controlled by another task chain in the space that you share it to.") :arrow_upper_right:.

    > ### Note:  
    > Data products created in this way can only contain data stored in file spaces.

3.  Navigate to the <span class="SAP-icons-V5"></span> \(*Data Sharing Cockpit*\) and create your data product \(see [Creating Data Products for SAP Business Data Cloud](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/b07e95d07a1e4569b87d9bb57b732bcf.html "Create a custom data product on a Delta Share runtime for SAP Business Data Cloud. This custom data product can then be shared with any system in the formation that supports it, such as SAP Databricks.") :arrow_upper_right:.
4.  Once your data product is created and listed it becomes available in the <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\) in both SAP Datasphere and the SAP Business Data Cloud Cockpit. You can then:
    -   Install your data product in your SAP Datasphere modeling space \(see [Installing Data Products](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/ea7cb802cbea47b39a441888873c3a49.html "Use the catalog Data Product collection to view data products for use in your modeling and other projects. You can see detailed metadata for each data product and if you have the appropriate permissions, install it to an SAP Datasphere space.") :arrow_upper_right:\).
    -   Share your data product with other consumers in your SAP Business Data Cloud formation \(see [Sharing Data Products](https://help.sap.com/docs/business-data-cloud/governing-and-publishing-data-in-catalog/sharing-data-products) in the *SAP Business Data Cloud* documentation.


