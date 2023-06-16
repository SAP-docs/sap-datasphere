<!-- loio7d2b21d974e44bdc9d548cf7532b5a43 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Using the Source Browser

You use the *Source Browser* to add objects as sources for your data flow, graphical view, SQL view, or intelligent lookup. In an E/R model you add objects to visualize them together in a diagram, including importing objects from connections and other sources, and prepare them for use in other editors.

The *Source Browser* is available in the left panel in each of these editors, and gives you access to all the objects that have been imported into or created in the space, and also to all the connections and other sources that are available in the space:

-    The *Repository* tab lists all the tables, views, and intelligent lookups that are available in the space \(including objects shared to the space\). The following categories can be available:

    -   *Tables* - Contains all remote and local tables in the space \(see [Acquiring Data in the Data Builder](Acquiring-and-Preparing-Data-in-the-Data-Builder/acquiring-data-in-the-data-builder-1f15a29.md)\).
    -   *Views* - Contains all graphical and SQL views present in the space \(see [Modeling Data in the Data Builder](Modeling-Data-in-the-Data-Builder/modeling-data-in-the-data-builder-5c1e3d4.md)\).

        > ### Note:  
        > You cannot use views with input parameters as sources in a data flow.

    -   *Intelligent Lookups* - Contains all intelligent lookups present in the space \(see [Creating an Intelligent Lookup](creating-an-intelligent-lookup-8f29f80.md)\).
    -   *Shared Objects* - Contains all objects shared to the space \(see [Sharing Tables and Views To Other Spaces](Creating-Finding-Sharing-Objects/sharing-tables-and-views-to-other-spaces-64b318f.md).

-    The *Sources* tab lists all the connections and other data sources that have been integrated to the space from which you can import tables. These can include: 

    -   *Connections* - Lists all the connections that have been created in the space \(see [Integrating Data via Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of sources, cloud as well as on-premise sources, SAP as well as Non-SAP sources, and partner tools. They allow space members to use objects from the connected source to acquire, prepare and access data from those sources in SAP Datasphere. To connect to different sources, SAP Datasphere provides different connection types.") :arrow_upper_right:\).

        You can browse and search on up to 1,000 objects per connection. To browse all available objects, hover over any schema and click <span class="FPA-icons"></span> \(Import from Connection\) to open the *Import Objects from Connection* dialog \(see [Import Multiple Objects from a Connection](import-multiple-objects-from-a-connection-e720b13.md)\).

    -   Open SQL Schemas - Each Open SQL schema appears as a root node in this tab \(see [Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/3de55a78a4614deda589633baea28645.html "Create a database user in your space to read and write directly to the SAP HANA Cloud database on which SAP Datasphere runs. Each database user has an Open SQL schema, which is attached to a space schema and provides a secure method for exchanging data with the space.") :arrow_upper_right:\).
    -   HDI Containers - Each SAP HDI container added to the space appears as a root node in this tab \(see [Exchanging Data with SAP SQL Data Warehousing HDI Containers](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/1aec7ca95af24208a61c1a444b249d95.html "Use SAP SQL Data Warehousing to build calculation views and other SAP HANA Cloud HDI objects directly in your SAP Datasphere run-time database and then exchange data between your HDI containers and your SAP Datasphere spaces. SAP SQL Data Warehousing can be used to bring existing HDI objects into your SAP Datasphere environment, and to allow users familiar with the HDI tools to leverage advanced SAP HANA Cloud features.") :arrow_upper_right:\).


