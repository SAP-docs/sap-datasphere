<!-- loio2509fe4d86aa472b9858164b55b38077 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Local Table

Create a table to contain data by defining its column structure. Tables created in SAP Datasphere can be filled with data from a CSV file or via a data flow. You can also import tables from a connection or a CSN file.



<a name="loio2509fe4d86aa472b9858164b55b38077__context_zdj_zhd_djb"/>

## Context

This procedure explains how to create an empty table by defining its columns. You can, alternatively:

-   Create a table by importing a CSV file \(see [Creating a Local Table from a CSV File](creating-a-local-table-from-a-csv-file-8bba251.md)\).
-   Create a table as the output of a data flow \(see [Add or Create a Target Table](add-or-create-a-target-table-0fa7805.md)\).
-   Import a table from:
    -   A connection via the *Sources* tab of the *Source Browser* in any of the data builder editors \(see [Import an Object from a Connection or Other Source](../import-an-object-from-a-connection-or-other-source-3e6f8f2.md)\).
    -   A CSN file via the *Import* menu in the data builder start page or an ER model \(see [Importing Objects from a CSN/JSON File](../Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md)\).




## Procedure

1.  In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *New Table* to open the editor.

2.  Enter the following properties as appropriate:


    <table>
    <tr>
    <th valign="top">

    Property


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Business Name 


    
    </td>
    <td valign="top">
    
    Enter a descriptive name to help users identify the object. This name can be changed at any time. 


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Technical Name 


    
    </td>
    <td valign="top">
    
    Displays the name used in scripts and code, synchronized by default with the *Business Name*.

    To override the default technical name, enter a new one in the field. Technical names can contain only alphanumeric characters and underscores.

    > ### Note:  
    > Once the object is saved, the technical name can no longer be modified.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Semantic Usage


    
    </td>
    <td valign="top">
    
    Select the way your entity should be used. 

    Choose from the following:

    -   *Fact* - Contains one or more measures and attributes. This is the principal type of object used by BI clients \(see [Creating a Fact](../Modeling-Data-in-the-Data-Builder/creating-a-fact-30089bd.md)\).
    -   *Dimension* - Contains attributes containing master data like a product list or store directory, and supporting hierarchies \(see [Creating a Dimension](../Modeling-Data-in-the-Data-Builder/creating-a-dimension-5aae0e9.md)\).
    -   *Hierarchy* - Contains attributes defining a parent-child hierarchy \(see [Creating an External Hierarchy](../Modeling-Data-in-the-Data-Builder/creating-an-external-hierarchy-dbac7a8.md)\).
    -   *Text* - Contains attributes used to provide textual content in one or more languages \(see [Create a Text Entity for Attribute Translation](../Modeling-Data-in-the-Data-Builder/create-a-text-entity-for-attribute-translation-b25726d.md)\).
    -   *Relational Dataset* - \[default\] Contains columns with no specific analytical purpose.
    -   *Analytical Dataset \(Deprecated\)* - Use *Fact* instead \(see [Analytical Datasets \(Deprecated\)](../Modeling-Data-in-the-Data-Builder/analytical-datasets-deprecated-70dab71.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Object \(Open SQL Schema/HDI Container\)


    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the technical name of the Open SQL Schema or HDI Container and the object name.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status


    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the deployment and error status of the object. 

    For more information, see [Saving and Deploying Objects](../Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).


    
    </td>
    </tr>
    </table>
    
3.  Based on the *Semantic Usage* of your entity, review and modify its *Columns*, *Attributes*, and/or *Measures*:

    -   *Fact* - Review the lists of measures and attributes \(see [Creating a Fact](../Modeling-Data-in-the-Data-Builder/creating-a-fact-30089bd.md)\).
    -   *Dimension* - Review the list of attributes \(see [Creating a Dimension](../Modeling-Data-in-the-Data-Builder/creating-a-dimension-5aae0e9.md)\).
    -   *Hierarchy* - Define the parent and child columns \(see [Creating an External Hierarchy](../Modeling-Data-in-the-Data-Builder/creating-an-external-hierarchy-dbac7a8.md)\).
    -   *Text* - Review the list of attributes \(see [Create a Text Entity for Attribute Translation](../Modeling-Data-in-the-Data-Builder/create-a-text-entity-for-attribute-translation-b25726d.md)\).
    -   *Relational Dataset* - Review the list of columns \(see [Columns](columns-8f0f40d.md)\).

4.  Complete or consult other sections as appropriate:

    -   *Associations* - Create associations to other entities \(see [Create an Association](../create-an-association-66c6998.md)\).
    -   *Business Purpose* - Provide a description, purpose, contacts, and tags to help other users understand your entity.
    -   *Table Services* - Enable the *In-Memory Storage* option to store the table data directly in memory \(see [Accelerate Table Data Access with In-Memory Storage](accelerate-table-data-access-with-in-memory-storage-407d1df.md)\).

        > ### Note:  
        > If the connection of your remote table source is configured as data access: *Remote Only,* you can navigate only to the *Remote Table Statistics*monitor.

    -   *Dependent Objects* - If your entity is used as a source or association target for other entities, then they are listed here \(see [Review the Objects That Depend on Your Table or View](../Creating-Finding-Sharing-Objects/review-the-objects-that-depend-on-your-table-or-view-ecac5fd.md)\).

5.  \[optional\] Click <span class="SAP-icons"></span> \(Edit Custom CSN Annotations\) to open the *Edit Custom CSN Annotations* dialog. For more information, see [Edit a Custom CSN Annotation](../edit-a-custom-csn-annotation-820d013.md) 

6.  Click <span class="FPA-icons"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons"></span> \(Deploy\) to save and deploy it immediately.

    For more information, see [Saving and Deploying Objects](../Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).

7.  Once your table is deployed, you can:

    -   Import data from a CSV file or delete all table data \(see [Load or Delete Local Table Data](load-or-delete-local-table-data-870401f.md)\).
    -   Manually add, edit, duplicate, or delete individual records \(see [Maintain Local Table Data](maintain-local-table-data-4bd5e64.md)\).
    -   Understand the lineage and impacts of the table

        \(see [Impact and Lineage Analysis](../Creating-Finding-Sharing-Objects/impact-and-lineage-analysis-9da4892.md)\).



