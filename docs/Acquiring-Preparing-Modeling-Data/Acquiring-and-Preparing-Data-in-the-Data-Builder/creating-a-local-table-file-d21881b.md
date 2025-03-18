<!-- loiod21881b121bc4703861be6ead4aea2ab -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Local Table \(File\)

Create a local table \(file\) to store data in the object store. Load data to your local table \(file\) via replication flows and transform the data with transformation flows.



<a name="loiod21881b121bc4703861be6ead4aea2ab__section_wpc_3fg_xcc"/>

## Context

> ### Note:  
> The object store is not enabled by default in SAP Datasphere tenants. To enable it in your tenant, see SAP note [3525760](https://me.sap.com/notes/3525760).
> 
> For additional information on working with data in the object store, see SAP Note [3538038](https://me.sap.com/notes/3538038).
> 
> The object store cannot be enabled in SAP Datasphere tenants provisioned prior to version 2021.03. To request the migration of your tenant, see SAP note [3268282](https://me.sap.com/notes/3268282).

SAP Datasphere supports two types of local table to persist data:

-   Local tables – Are stored on disk or in-memory \(see [Creating a Local Table](https://help.sap.com/docs/SAP_DATASPHERE/c8a54ee704e94e15926551293243fd1d/2509fe4d86aa472b9858164b55b38077.html?locale=en-US&state=DRAFT&version=DEV)\). These tables can use delta capture and can only be created in a standard space \(with **SAP HANA Database \(Disk and In-Memory\)** storage \(see [Create a Space](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/bbd41b82ad4d4d9ba91341545f0b37e7.html?locale=en-US&state=DRAFT&version=DEV)\).
-   Local tables \(file\) – Are stored on files and are intended for file storage with large amounts of data at lower cost. These tables always use delta capture and can only be created in a file space \(with **SAP HANA Data Lake Files** storage \(see [Create a File Space to Load Big Data](https://help.sap.com/docs/SAP_DATASPHERE/c8a54ee704e94e15926551293243fd1d/947444683e524cfd9169d7671b72ba0c.html?locale=en-US&state=DRAFT&version=DEV)\).

You cannot create views and analytic models in file spaces, but you can share local tables \(file\) to standard spaces where they can be consumed by views, flows, and analytic models \(see [Sharing Entities and Task Chains to Other Spaces](../Creating-Finding-Sharing-Objects/sharing-entities-and-task-chains-to-other-spaces-64b318f.md)\).

SAP HANA Cloud, data lake allows SAP Datasphere to store and manage mass-data efficiently in a secured environment. The SAP HANA native SQL on files feature gives you a direct access to the data stored in the object store and enables large data-based business scenarios at lower costs.

As a local table \(file\) is capturing delta changes via flows, it creates different entities in the repository after it is deployed:

-   An active records entity for accessing the delta capture entity through a virtual table. It excludes the delta capture columns and deleted records, and keeps only the active records.
-   A delta capture entity that stores information on changes found in the delta capture table. It serves as target for flows at design time. In addition, every local table \(File\) has a specific folder in file storage \(inbound buffer\) to which a replication flow writes data files to a specific target object. To process data updates from this inbound buffer to the local table \(File\), and therefore make data visible, a merge task has to run via a task chain \(see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md)\). 



<a name="loiod21881b121bc4703861be6ead4aea2ab__section_s5h_mfg_xcc"/>

## Create a Local Table \(File\)

> ### Restriction:  
> -   You must be in a space that allows storage on SAP HANA Cloud data lake files.
> -   You can't switch from file table stored in data lake into a local table stored in SAP HANA database.
> -   *Data Preview* of local tables \(file\) displays only active records. This is different to local tables where the *Data Preview* displays records from the delta capture entity.
> -   *Delete Data from Table* will only mark records for deletion, but they will still be available for other apps to consume them.
> -   You can't import a CSV file.
> -   You can't switch off the delta capture option.
> -   You can't edit the data in the *Data Editor*.
> -   Default value is not supported



### Procedure

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
    
    Business Name
    
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
    
    Select the way your entity should be used for data modeling purposes. 

    Choose from the following:

    -   *Fact* - Contains one or more measures and attributes. A fact typically has associations pointing to one or more dimensions and is consumed by analytic models \(see [Create a Fact to Contain Measurable Data](../Modeling-Data-in-the-Data-Builder/create-a-fact-to-contain-measurable-data-30089bd.md)\).
    -   *Dimension* - Contains attributes containing master data like a product list or store directory, and supporting hierarchies \(see [Create a Dimension to Categorize Data](../Modeling-Data-in-the-Data-Builder/create-a-dimension-to-categorize-data-5aae0e9.md)\).
    -   *Hierarchy* - Contains attributes defining a parent-child hierarchy \(see [Create an External Hierarchy for Drill-Down](../Modeling-Data-in-the-Data-Builder/create-an-external-hierarchy-for-drill-down-dbac7a8.md)\).
    -   *Hierarchy with Directory* - Contains one or more parent-child hierarchies \(see [Create a Hierarchy with Directory](../Modeling-Data-in-the-Data-Builder/create-a-hierarchy-with-directory-36c39ee.md)\).
    -   *Text* - Contains attributes used to provide textual content in one or more languages \(see [Create a Text Entity for Attribute Translation](../Modeling-Data-in-the-Data-Builder/create-a-text-entity-for-attribute-translation-b25726d.md)\).
    -   *Relational Dataset* - \[default\] Contains columns with no specific analytical purpose.
    -   *Analytical Dataset \(Deprecated\)* - Use *Fact* instead \(see [Analytical Datasets \(Deprecated\)](../Modeling-Data-in-the-Data-Builder/analytical-datasets-deprecated-70dab71.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Storage
    
    </td>
    <td valign="top">
    
    \(read-only\) Displays the table storage. 

    For local tables created in a space with SAP HANA Cloud data lake storage, the value is "File".
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delta Capture
    
    </td>
    <td valign="top">
    
    \(read-only\) Track the delta changes that are made in the local table adding 2 delta capture columns: `Change Type` and `Change Date`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the deployment and error status of the object. 

    For more information, see [Saving and Deploying Objects](../saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    </table>
    
3.  Based on the *Semantic Usage* of your entity, review and modify its *Columns**Attributes*, and/or *Measures*:

    -   *Fact* - Review the lists of measures and attributes \(see [Create a Fact to Contain Measurable Data](../Modeling-Data-in-the-Data-Builder/create-a-fact-to-contain-measurable-data-30089bd.md)\).
    -   *Dimension* - Review the list of attributes \(see [Create a Dimension to Categorize Data](../Modeling-Data-in-the-Data-Builder/create-a-dimension-to-categorize-data-5aae0e9.md)\).
    -   *Hierarchy* - Define the parent and child columns \(see [Create an External Hierarchy for Drill-Down](../Modeling-Data-in-the-Data-Builder/create-an-external-hierarchy-for-drill-down-dbac7a8.md)\).
    -   *Hierarchy with Directory* - Define all the necessary attributes and settings \(see [Create a Hierarchy with Directory](../Modeling-Data-in-the-Data-Builder/create-a-hierarchy-with-directory-36c39ee.md)\).
    -   *Text* - Review the list of attributes \(see [Create a Text Entity for Attribute Translation](../Modeling-Data-in-the-Data-Builder/create-a-text-entity-for-attribute-translation-b25726d.md)\).
    -   *Relational Dataset* - Review the list of columns \(see [Columns](columns-8f0f40d.md)\).
    -   *Analytical Dataset \(Deprecated\)* - Use *Fact* instead \(see [Analytical Datasets \(Deprecated\)](../Modeling-Data-in-the-Data-Builder/analytical-datasets-deprecated-70dab71.md).

    > ### Caution:  
    > Once you've deployed the local table \(file\), if data exists, you can't update:
    > 
    > -   The technical name,
    > -   The data type,
    > -   The key column: you can't remove or add a new key column
    > -   Select additional *Not Null* option for an existing column.
    > -   The associations definition.
    > 
    > You can't delete an existing column that contains data, but you can add a new one.

    Columns can have the following properties:


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
    
    Key
    
    </td>
    <td valign="top">
    
    Select the checkbox to specify that the column is a primary key column. Key columns cannot be null. 

    > ### Note:  
    > You must select at least one column. After deployment, you can't add a new key column.


    
    </td>
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
    
    Data Type
    
    </td>
    <td valign="top">
    
    Select the type of data that the column will contain.

    > ### Note:  
    > A local table \(file\) does not support all data types. Only the supported data types are displayed. For more information, see [Data Types Supported By Local Tables \(File\)](data-types-supported-by-local-tables-file-2f39104.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Not Null
    
    </td>
    <td valign="top">
    
    Select this option to indicate that the column must contain a value. 

    > ### Note:  
    > This property is only displayed in the table editor.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Change Type
    
    </td>
    <td valign="top">
    
    This column will track the type of last change made to a record. 

    Note that deleting a record will not physically delete it, so that the changes can be propagated to the different objects that consume it in delta mode. It is however filtered out when accessing the local table \(using the Active Records Table\). The handling of the different change types is implemented internally by SAP Datasphere apps that consume the Delta Capture Table with no need for consideration in modeling. For more information on records deletion, see [Load or Delete Local Table Data](load-or-delete-local-table-data-870401f.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Change Date
    
    </td>
    <td valign="top">
    
    The column will track the last date and time of the last change to an individual record. Current UTC timestamp.
    
    </td>
    </tr>
    </table>
    
4.  Create associations to other entities if needed \(see [Create an Association to Define a Semantic Relationship Between Entities](../Modeling-Data-in-the-Data-Builder/create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md)\).
5.  *Business Purpose* - Provide a description, purpose, contacts, and tags to help other users understand your entity.
6.  *Partition Columns*- Define partitions.

    Partitions for a local table \(file\) must be based on columns \(and not on range of values as for local tables stored on SAP HANA database\).There are few data types which are not supported for partitioning. The dialog will propose only columns with supported data types. For more information, on data types supported, see [Data Types Supported By Local Tables \(File\)](data-types-supported-by-local-tables-file-2f39104.md).

    > ### Note:  
    > -   You can select several columns to partition your data but you must not select all columns.
    > -   You can’t change the partition definition after you have deployed the table if it contains data.

7.  *Dependent Objects*- If your entity is used as a source or a target \(for example, table with delta capture enabled\) or as association target for other entities, then they are listed here. For more information, see [Review the Objects That Depend on Your Table or View](../review-the-objects-that-depend-on-your-table-or-view-ecac5fd.md).
8.  Click <span class="FPA-icons-V3"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy it immediately.

    > ### Note:  
    > Deployment of local tables \(file\) can take longer than a deployment of a local table.

    For more information, see [Saving and Deploying Objects](../saving-and-deploying-objects-7c0b560.md).

9.  Once your local table \(file\) is deployed, you can consume it or share it.

