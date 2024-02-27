<!-- loio27efb479c4814252964d3fbc6ca2dfc3 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Creating a Graphical View

Create a view to query sources in an intuitive graphical interface. You can drag and drop sources from the *Source Browser*, join them as appropriate, add other operators to remove or create columns and filter or aggregate data, and specify measures and other aspects of your output structure in the output node.



## Context

If you are comfortable writing SQL code or want to use SQL Script to create your view, you can use the SQL View editor \(see [Creating an SQL View](creating-an-sql-view-81920e4.md)\).

> ### Note:  
> There are two methods for exposing view data for consumption outside SAP Datasphere:
> 
> -   SAP Analytics Cloud \(and Microsoft Excel via an SAP add-in\) do not consume view data directly. Set the *Semantic Usage* of your view to *Fact* and then add it to an analytic model to expose it \(see [Creating an Analytic Model](Modeling-Data-in-the-Data-Builder/creating-an-analytic-model-e5fbe9e.md)\). There is no need to enable the *Expose for Consumption* switch.
> -   Other third-party BI clients, tools, and apps can consume data from views with any *Semantic Usage* via OData or ODBC if the *Expose for Consumption* switch is enabled.
> 
> For more information, see [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users of with any of the standard roles can consume data exposed by spaces they are assigned to. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the DW Consumer role.") :arrow_upper_right:.



## Procedure

1.  In the side navigation area, click ![](Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *New Graphical View* to open the editor.

2.  Drag a first source from the *Source Browser* and drop it into the diagram.

    The source is added to the diagram along with an output node, initially entitiled `View 1`, which represents the final output structure of the view.

    For more information, see [Add a Source](add-a-source-1eee180.md).

    If your source has an iput parameter, the *Map Input Parameter* dialog appears. You can either set a value for each parameter or map to an input parameter in the view. If you choose to set a value, you can either enter a value manually or, if your input parameter has a predefined default value, get access to a list of predefined values with the *Value Help Dialog*. Only the first 10 records are shown by default. You can see more by using the *Search* bar or clicking *More*.

    For more information, see [Create an Input Parameter](create-an-input-parameter-53fa99a.md).

3.  Optional. Drag additional sources from the *Source Browser* and drop them on your source to create a join or union.

    For more information, see [Create a Join](create-a-join-947d6d8.md) and [Create a Union](create-a-union-5c3d354.md).

4.  Click a node in the diagram to display tools for creating operators and performing other actions:

    > ### Note:  
    > You can only create one each of the *Filter*, *Projection*, *Calculated Columns*, and *Aggregation* operators per source or join in your diagram. Operators can be created in any order.


    <table>
    <tr>
    <th valign="top">

    Tools
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Filter\)
    
    </td>
    <td valign="top">
    
    Add a *Filter* node to filter your data with an SQL expression. For more information, see [Filter Data](filter-data-6f6fa18.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Rename/Exclude Columns\)
    
    </td>
    <td valign="top">
    
    Add a *Projection* node to rename, reorder, or exclude columns. For more information, see [Reorder, Rename, and Exclude Columns](reorder-rename-and-exclude-columns-b846d0d.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Calculated Columns\)
    
    </td>
    <td valign="top">
    
    Add a *Calculated Columns* node to create new columns and define calculations in them. For more information, see [Create a Column](create-a-column-3897f48.md) or [SAP HANA SQL and System Views Reference](https://help.sap.com/viewer/7c78579ce9b14a669c1f3295b0d8ca16/Cloud/en-US/20a61f29751910149f99f0300dd95cd9.html).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Aggregation\)
    
    </td>
    <td valign="top">
    
    Add an *Aggregation* node to perform `SUM`, `COUNT`, `MIN`, and `MAX` calculations. For more information, see [Aggregate Data](aggregate-data-7733250.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Join Suggestion\)
    
    </td>
    <td valign="top">
    
    Create a join from a list of *Related Entities* that is populated based on the presence of associations between the current source and other artifacts.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Preview Data\)
    
    </td>
    <td valign="top">
    
    Preview the data output by the selected diagram node in the *Data Preview* panel \(see [Viewing or Previewing Data in Data Builder Objects](viewing-or-previewing-data-in-data-builder-objects-b338e4a.md)\).

    > ### Note:  
    > Users with the *DW Viewer* role cannot preview data if the *Expose for Consumption* switch is disabled and, if the switch is enabled, can only preview data in the output node. For more information, see [Roles and Privileges by App and Feature](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/2d8b7d04dcae402f911d119437ce0a74.html "Review the standard roles and the privileges needed to access apps, tools, and other features of SAP Datasphere.") :arrow_upper_right:.

    You can preview the SQL generated for the node by clicking the *Preview SQL* button in the panel or by clicking <span class="FPA-icons-V3"></span> Export and selecting *Preview SQL*. Click *Copy* to copy the SQL code for pasting into the SQL View editor or elsewhere.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Impact and Lineage Analysis\)
    
    </td>
    <td valign="top">
    
    Open the Impact and Lineage Analysis diagram. This diagram enables you to understand the lineage and impacts of the selected object. 

    \(see [Impact and Lineage Analysis](Creating-Finding-Sharing-Objects/impact-and-lineage-analysis-9da4892.md).\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Open in New Tab\)
    
    </td>
    <td valign="top">
    
    Open the object in its own editor in a new tab.
    
    </td>
    </tr>
    </table>
    
5.  Click the output node to show the view's properties in the side panel. Enter the following properties as appropriate:


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

    -   *Fact* - Contains one or more measures and attributes. This is the principal type of object used by BI clients \(see [Creating a Fact](Modeling-Data-in-the-Data-Builder/creating-a-fact-30089bd.md)\).
    -   *Dimension* - Contains attributes containing master data like a product list or store directory, and supporting hierarchies \(see [Creating a Dimension](Modeling-Data-in-the-Data-Builder/creating-a-dimension-5aae0e9.md)\).
    -   *Hierarchy* - Contains attributes defining a parent-child hierarchy \(see [Creating an External Hierarchy](Modeling-Data-in-the-Data-Builder/creating-an-external-hierarchy-dbac7a8.md)\).
    -   *Hierarchy with Directory* - Contains one or more parent-child hierarchies \(see [Creating a Hierarchy with Directory](Modeling-Data-in-the-Data-Builder/creating-a-hierarchy-with-directory-36c39ee.md)\).
    -   *Text* - Contains attributes used to provide textual content in one or more languages \(see [Create a Text Entity for Attribute Translation](Modeling-Data-in-the-Data-Builder/create-a-text-entity-for-attribute-translation-b25726d.md)\).
    -   *Relational Dataset* - \[default\] Contains columns with no specific analytical purpose.
    -   *Analytical Dataset \(Deprecated\)*Hierarchy - Use *Fact* instead \(see [Analytical Datasets \(Deprecated\)](Modeling-Data-in-the-Data-Builder/analytical-datasets-deprecated-70dab71.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Expose for Consumption
    
    </td>
    <td valign="top">
    
    Enable this option to make the view available for consumption outside SAP Datasphere via OData or ODBC. 

    > ### Note:  
    > There are two methods for exposing view data for consumption outside SAP Datasphere:
    > 
    > -   SAP Analytics Cloud \(and Microsoft Excel via an SAP add-in\) do not consume view data directly. Set the *Semantic Usage* of your view to *Fact* and then add it to an analytic model to expose it \(see [Creating an Analytic Model](Modeling-Data-in-the-Data-Builder/creating-an-analytic-model-e5fbe9e.md)\). There is no need to enable the *Expose for Consumption* switch.
    > -   Other third-party BI clients, tools, and apps can consume data from views with any *Semantic Usage* via OData or ODBC if the *Expose for Consumption* switch is enabled.
    > 
    > For more information, see [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users of with any of the standard roles can consume data exposed by spaces they are assigned to. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the DW Consumer role.") :arrow_upper_right:.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Run in Analytical Mode
    
    </td>
    <td valign="top">
    
    Enable this option to send the `USE_OLAP_PLAN` hint to the SQL optimizer. 

    This may improve view performance, particularly if a union is performed. It is only available if *Expose for Consumption* is enabled.

    For more information, see [HINT Details](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/4ba9edce1f2347a0b9fcda99879c17a1.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the deployment and error status of the object. 

    For more information, see [Saving and Deploying Objects](Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    </table>
    
6.  Based on the *Semantic Usage* of your entity, review and modify its *Columns*, *Attributes*, and/or *Measures*:

    -   *Fact* - Review the lists of measures and attributes \(see [Creating a Fact](Modeling-Data-in-the-Data-Builder/creating-a-fact-30089bd.md)\).
    -   *Dimension* - Review the list of attributes \(see [Creating a Dimension](Modeling-Data-in-the-Data-Builder/creating-a-dimension-5aae0e9.md)\).
    -   *Hierarchy* - Define the parent and child columns \(see [Creating an External Hierarchy](Modeling-Data-in-the-Data-Builder/creating-an-external-hierarchy-dbac7a8.md)\).
    -   *Hierarchy with Directory* - Define all the necessary attributes and settings \(see [Creating a Hierarchy with Directory](Modeling-Data-in-the-Data-Builder/creating-a-hierarchy-with-directory-36c39ee.md)\).
    -   *Text* - Review the list of attributes \(see [Create a Text Entity for Attribute Translation](Modeling-Data-in-the-Data-Builder/create-a-text-entity-for-attribute-translation-b25726d.md)\).
    -   *Relational Dataset* - Review the list of columns \(see [Columns](Acquiring-and-Preparing-Data-in-the-Data-Builder/columns-8f0f40d.md)\).

7.  Complete or consult other sections as appropriate:

    -   *Input Parameters* - Create input parameters to require the user to enter a value for use in calculated column, filter, and aggregation nodes \(see [Create an Input Parameter](create-an-input-parameter-53fa99a.md)\).
    -   *Data Persistence* - Persist the view data to improve performance \(see [Persist View Data](persist-view-data-9bd12cf.md)\).
    -   *Associations* - Create associations to other entities \(see [Create an Association](create-an-association-66c6998.md)\).
    -   *Data Access Controls* - Add data access controls to apply row-based security and control access to individual rows based on various criteria \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:\).
    -   *Business Purpose* - Provide a description, purpose, contacts, and tags to help other users understand your entity.
    -   *Dependent Objects* - If your entity is used as a source or association target for other entities, then they are listed here \(see [Review the Objects That Depend on Your Table or View](Creating-Finding-Sharing-Objects/review-the-objects-that-depend-on-your-table-or-view-ecac5fd.md)\).

8.  Click <span class="FPA-icons-V3"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy it immediately.

    For more information, see [Saving and Deploying Objects](Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).

9.  \[optional\] Click <span class="SAP-icons-V5"></span> \(Edit Custom CSN Annotations\) to open the *Edit Custom CSN Annotations* dialog. For more information, see [Edit a Custom CSN Annotation](edit-a-custom-csn-annotation-820d013.md) 

10. Click <span class="FPA-icons-V3"></span> \(Impact and Lineage Analysis\) in the toolbar to understand the lineage and impacts of the output \(see [Impact and Lineage Analysis](Creating-Finding-Sharing-Objects/impact-and-lineage-analysis-9da4892.md)\).


