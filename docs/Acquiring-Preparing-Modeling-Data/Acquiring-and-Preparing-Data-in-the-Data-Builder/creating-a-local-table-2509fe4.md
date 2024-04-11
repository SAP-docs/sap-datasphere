<!-- loio2509fe4d86aa472b9858164b55b38077 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Local Table

Create a table and define columns to receive data from a flow or a CSV file. You can also import tables from a connection or a CSN file.



<a name="loio2509fe4d86aa472b9858164b55b38077__context_zdj_zhd_djb"/>

## Context

This procedure explains how to create an empty table by defining its columns. You can, alternatively:

-   Create a table by importing a CSV file \(see [Creating a Local Table from a CSV File](creating-a-local-table-from-a-csv-file-8bba251.md)\).
-   Create a table as the output of a flow \(see [Add or Create a Target Table](add-or-create-a-target-table-0fa7805.md)\).
-   Import a table from:
    -   A connection or other source in the *Sources* tab of the *Source Browser* in any of the data builder editors \(see [Import an Object from a Connection or Other Source](../import-an-object-from-a-connection-or-other-source-3e6f8f2.md)\).
    -   A CSN file via the *Import* menu in the data builder start page or an ER model \(see [Importing Objects from a CSN/JSON File](../Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md)\).




## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New Table* to open the editor.

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
    
    Package
    
    </td>
    <td valign="top">
    
    Select the package to which the object belongs. 

    Packages are used to group related objects in order to facilitate their transport between tenants.

    > ### Note:  
    > Once a package is selected, it cannot be changed here. Only a user with the DW Space Administrator role \(or equivalent privileges\) can modify a package assignment in the *Packages* editor.

    For more information, see [Creating Packages to Export](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/24aba84ceeb3416881736f70f02e3a0a.html "Users with the DW Space Administrator role can create packages to model groups of related objects for transport between tenants. Modelers can add objects to packages via the Package field, which appears in editors when a package is created in their space. Once a package is complete and validated, the space administrator can export it to the Content Network. The structure of your package is preserved and, as the objects it contains evolve, you can easily export updated versions of it.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Semantic Usage
    
    </td>
    <td valign="top">
    
    Select the way your entity should be used for data modeling purposes. 

    Choose from the following:

    -   *Fact* - Contains one or more measures and attributes. A fact typically has associations pointing to one or more dimensions and is consumed by analytic models \(see [Creating a Fact](../Modeling-Data-in-the-Data-Builder/creating-a-fact-30089bd.md)\).
    -   *Dimension* - Contains attributes containing master data like a product list or store directory, and supporting hierarchies \(see [Creating a Dimension](../Modeling-Data-in-the-Data-Builder/creating-a-dimension-5aae0e9.md)\).
    -   *Hierarchy* - Contains attributes defining a parent-child hierarchy \(see [Creating an External Hierarchy](../Modeling-Data-in-the-Data-Builder/creating-an-external-hierarchy-dbac7a8.md)\).
    -   *Hierarchy with Directory* - Contains one or more parent-child hierarchies \(see [Creating a Hierarchy with Directory](../Modeling-Data-in-the-Data-Builder/creating-a-hierarchy-with-directory-36c39ee.md)\).
    -   *Text* - Contains attributes used to provide textual content in one or more languages \(see [Create a Text Entity for Attribute Translation](../Modeling-Data-in-the-Data-Builder/create-a-text-entity-for-attribute-translation-b25726d.md)\).
    -   *Relational Dataset* - \[default\] Contains columns with no specific analytical purpose.
    -   *Analytical Dataset \(Deprecated\)* - Use *Fact* instead \(see [Analytical Datasets \(Deprecated\)](../Modeling-Data-in-the-Data-Builder/analytical-datasets-deprecated-70dab71.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delta Capture
    
    </td>
    <td valign="top">
    
    Track the delta changes that are made in the table adding 2 delta capture columns: `Change Type` and `Change Date`. See [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md)
    
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
    -   *Hierarchy with Directory* - Define all the necessary attributes and settings \(see [Creating a Hierarchy with Directory](../Modeling-Data-in-the-Data-Builder/creating-a-hierarchy-with-directory-36c39ee.md)\).
    -   *Text* - Review the list of attributes \(see [Create a Text Entity for Attribute Translation](../Modeling-Data-in-the-Data-Builder/create-a-text-entity-for-attribute-translation-b25726d.md)\).
    -   *Relational Dataset* - Review the list of columns \(see [Columns](columns-8f0f40d.md)\).

4.  Complete or consult other sections as appropriate:

    -   *Associations* - Create associations to other entities \(see [Create an Association](../create-an-association-66c6998.md)\).
    -   *Business Purpose* - Provide a description, purpose, contacts, and tags to help other users understand your entity.
    -   *Table Services* - Enable the *Memory Storage* option to store the table data directly in memory \(see [Accelerate Table Data Access with In-Memory Storage](accelerate-table-data-access-with-in-memory-storage-407d1df.md)\).

        > ### Note:  
        > If the connection of your remote table source is configured as data access: *Remote Only,* you can navigate only to the *Remote Table Statistics* monitor.

    -   *Partitions*- Define partitions for your local table. For more information, see [Partitioning Local Tables](partitioning-local-tables-03191f3.md).
    -   *Dependent Objects*- If your entity is used as a source or as association target for other entities, then they are listed here. For more information, see [Review the Objects That Depend on Your Table or View](../Creating-Finding-Sharing-Objects/review-the-objects-that-depend-on-your-table-or-view-ecac5fd.md).

5.  \[optional\] Click <span class="SAP-icons-V5"></span> \(Edit Custom CSN Annotations\) to open the *Edit Custom CSN Annotations* dialog. For more information, see [Edit a Custom CSN Annotation](../edit-a-custom-csn-annotation-820d013.md) 

6.  Click <span class="FPA-icons-V3"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy it immediately.

    For more information, see [Saving and Deploying Objects](../Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).

7.  Once your table is deployed, you can:

    -   Import data from a CSV file or delete all table data \(see [Load or Delete Local Table Data](load-or-delete-local-table-data-870401f.md)\).
    -   Manually add, edit, duplicate, or delete individual records \(see [Maintain Local Table Data](maintain-local-table-data-4bd5e64.md)\).
    -   Understand the lineage and impacts of the table

        \(see [Impact and Lineage Analysis](../Creating-Finding-Sharing-Objects/impact-and-lineage-analysis-9da4892.md)\).



