<!-- loio3e6f8f274e1d42759f536d3004025d24 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Import an Object from a Connection or Other Source

Drag objects from the *Sources* tab of the *Source Browser* to add them as sources in your data flow, graphical view, or SQL view. In an E/R model, you can add objects from any connections and other sources, and prepare them for use in other editors.



<a name="loio3e6f8f274e1d42759f536d3004025d24__context_hbr_k4y_jsb"/>

## Context

> ### Note:  
> In the data flow editor, tables taken from connections are simply connected to \(and not imported\).



<a name="loio3e6f8f274e1d42759f536d3004025d24__steps_qjw_4c4_ppb"/>

## Procedure

1.  If the *Source Browser* panel is not visible on the left of the screen, click *Source Browser* in the toolbar to show it.

2.  Click the *Sources* tab.

     The *Sources* tab lists all the connections and other data sources that have been integrated to the space from which you can import tables. These can include: 

    -   *Connections* - Lists all the connections that have been created in the space \(see [Integrating Data via Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of sources, cloud as well as on-premise sources, SAP as well as Non-SAP sources, and partner tools. They allow space members to use objects from the connected source to acquire, prepare and access data from those sources in SAP Datasphere. To connect to different sources, SAP Datasphere provides different connection types.") :arrow_upper_right:\).

        You can browse and search on up to 1,000 objects per connection. To browse all available objects, hover over any schema and click <span class="FPA-icons"></span> \(Import from Connection\) to open the *Import Objects from Connection* dialog \(see [Import Multiple Objects from a Connection](import-multiple-objects-from-a-connection-e720b13.md)\).

    -   Open SQL Schemas - Each Open SQL schema appears as a root node in this tab \(see [Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/3de55a78a4614deda589633baea28645.html "Create a database user in your space to read and write directly to the SAP HANA Cloud database on which SAP Datasphere runs. Each database user has an Open SQL schema, which is attached to a space schema and provides a secure method for exchanging data with the space.") :arrow_upper_right:\).
    -   HDI Containers - Each SAP HDI container added to the space appears as a root node in this tab \(see [Exchanging Data with SAP SQL Data Warehousing HDI Containers](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/1aec7ca95af24208a61c1a444b249d95.html "You can enable SAP SQL Data Warehousing on your SAP Datasphere tenant to exchange data between your HDI containers and your SAP Datasphere spaces without the need for data movement.") :arrow_upper_right:\).

    ![](images/Source_Browser_-_Sources_Tab_Collapsed_4ebf04c.png)

3.  Expand the source from which you want to import a table and then expand any sub-folders until you arrive at the table you want to import:

    ![](images/Source_Browser_-_Sources_Tab_ede29aa.png)

4.  Drag the table you want to import and drop it on the diagram canvas:

    ![](images/Source_Browser_-_Sources_Tab_Drag_Source_3dd91cf.png)

5.  In the *Import Table* dialog, accept the default business and technical names or overwrite them and then click *Import and Deploy*:

    ![](images/Import_Table_Dialog_ee879cd.png) 

    The source is added to your diagram and is imported to the repository. From now on it is available to everyone in your space on the *Repository* tab of the *Source Browser*:

    -   Connections - Tables are imported as remote tables

        > ### Note:  
        > In the data flow editor, tables taken from connections are simply connected to \(and not imported\).

    -   Open SQL queries - Tables are imported as local tables
    -   HDI containers - Tables are imported as local tables

    ![](images/Source_Browser_-_Source_Added_971a5aa.png)


