<!-- loio81920e4d583f45fd8761c662d3c8abab -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Creating an SQL View

Create a view to query sources in a powerful SQL editor. You can choose between writing a standard SQL query using `SELECT` statements and operators such as `JOIN` and `UNION`, or use SQLScript to produce a table function. You can drag sources from the *Source Browser*, and specify measures and other aspects of your output structure in the side panel.



## Context

If you are not comfortable with SQL, you can still build a view in SAP Datasphere by using the Graphical View editor, which lets you compose SQL code using an intuitive graphical interface \(see [Creating a Graphical View](creating-a-graphical-view-27efb47.md)\).

> ### Note:  
> There are two methods for exposing view data for consumption outside SAP Datasphere:
> 
> -   SAP Analytics Cloud \(and Microsoft Excel via an SAP add-in\) do not consume view data directly. Set the *Semantic Usage* of your view to *Fact* and then add it to an analytic model to expose it \(see [Creating an Analytic Model](Modeling-Data-in-the-Data-Builder/creating-an-analytic-model-e5fbe9e.md)\). There is no need to enable the *Expose for Consumption* switch.
> -   Other third-party BI clients, tools, and apps can consume data from views with any *Semantic Usage* via OData or ODBC if the *Expose for Consumption* switch is enabled.
> 
> For more information, see [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users of SAP Datasphere with any of the standard roles can consume data exposed by spaces of which they are a member. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the DW Consumer role.") :arrow_upper_right:.



## Procedure

1.  In the side navigation area, click ![](Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *New SQL View* to open the editor.

2.  In the side panel, select the language that you want to use. You can choose between:

    -   *SQL \(Standard Query\)* - \[default\] Create a standard SQL query, based around `SELECT` statements \(see [SQL Reference](sql-reference-6a37cc5.md)\).
    -   *SQLScript \(Table Function\)* - Use SQLScript with support for `IF` statements, loops, and other more complex structures \(see [SQLScript Reference](sqlscript-reference-6c46c6a.md)\).

3.  Enter your code in the editor panel. You can:

    -   Access auto-complete suggestions for keywords and object names including source entities by typing.
    -   Drag sources from the *Source Browser* into the editor panel.

        > ### Note:  
        > If you add a source view containing input parameters, the source and its parameters will be added to your code and you will need to process each parameter \(see [Process Source Input Parameters in an SQL View](process-source-input-parameters-in-an-sql-view-58d8763.md)\)

    -   Add comments to document your code:

        -   Comment out a single line or the rest of a line with a double dash: `-- Your comment here`.
        -   Comment out multiple lines or part of a line with: `/* Your comment here */`.

        This example contains various forms of comments:

        ```
        /*  
            This is a multi-line comment to
            introduce this view 
        */
        
        SELECT "ID",
        	"Date",
        --	"Sales Person", comment out a line
        	"City", -- comment at end of line
        	"Net Sales"
        FROM /* mid-line comment */ "Sales"
        ```

    -   Format your SQL code by clicking *Format*.

        > ### Note:  
        > SQLScript cannot be formatted.

    -   Validate your code and update the display of your output structure in the side panel at any time by clicking <span class="FPA-icons"></span> \(Validate SQL and Preview Data\).

        SQL errors and warnings are shown in the *Errors* pane at the bottom of the editor. Problems with the output structure are shown on the *Validation Messages* button in the side panel header.

        > ### Note:  
        > If your SQLScript is complicated, SAP Datasphere may not be able to determine the output structure. In this case, you are requested to review the list of columns. Click the *Edit* button to add or delete buttons or change column names and data types.

    -   Preview the data being output by the view by clicking <span class="SAP-icons"></span> \(Show or hide data preview\)\(see [Viewing or Previewing Data in Data Builder Objects](viewing-or-previewing-data-in-data-builder-objects-b338e4a.md)\).

        Previewing a SQL view isn't possible if one of the view's objects is shared from another space and has an input parameter.

    -   Click <span class="SAP-icons"></span> \(Edit Custom CSN Annotations\) to open the *Edit Custom CSN Annotations* dialog: 
        -   Click <span class="FPA-icons"></span> \(Previous Annotation\) and <span class="FPA-icons"></span> \(Next Annotation\) to navigate from one custom CSN annotation to another.
        -   Enter changes for the custom CSN annotations in the code.
        -   Click <span class="FPA-icons"></span> \(Validate CSN expression\) to check if changes invalidate or not the CSN expression.

    -   View the objects that depend on an analyzed object \(its impacts\) and the objects on which the analyzed object depends \(its lineage\) by clicking <span class="FPA-icons"></span> \(Impact and Lineage Analysis\) \(see [Impact and Lineage Analysis](Creating-Finding-Sharing-Objects/impact-and-lineage-analysis-9da4892.md)\).

4.  Enter the following properties as appropriate in the side panel:


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
    
    Language


    
    </td>
    <td valign="top">
    
    Select the SQL language to use. 

    Choose from the following:

    -   *SQL \(Standard Query\)* - \[default\] Create a standard SQL query, based around `SELECT` statements \(see [SQL Reference](sql-reference-6a37cc5.md)\).
    -   *SQLScript \(Table Function\)* - Use SQLScript with support for `IF` statements, loops, and other more complex structures \(see [SQLScript Reference](sqlscript-reference-6c46c6a.md)\).


    
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
    
    Semantic Usage


    
    </td>
    <td valign="top">
    
    Select the way your entity should be used. 

    Choose from the following:

    -   *Fact* - Contains one or more measures and attributes. This is the principal type of object used by BI clients \(see [Creating a Fact](Modeling-Data-in-the-Data-Builder/creating-a-fact-30089bd.md)\).
    -   *Dimension* - Contains attributes containing master data like a product list or store directory, and supporting hierarchies \(see [Creating a Dimension](Modeling-Data-in-the-Data-Builder/creating-a-dimension-5aae0e9.md)\).
    -   *Hierarchy* - Contains attributes defining a parent-child hierarchy \(see [Creating an External Hierarchy](Modeling-Data-in-the-Data-Builder/creating-an-external-hierarchy-dbac7a8.md)\).
    -   *Text* - Contains attributes used to provide textual content in one or more languages \(see [Create a Text Entity for Attribute Translation](Modeling-Data-in-the-Data-Builder/create-a-text-entity-for-attribute-translation-b25726d.md)\).
    -   *Relational Dataset* - \[default\] Contains columns with no specific analytical purpose.
    -   *Analytical Dataset \(Deprecated\)* - Use *Fact* instead \(see [Analytical Datasets \(Deprecated\)](Modeling-Data-in-the-Data-Builder/analytical-datasets-deprecated-70dab71.md).


    
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
    > For more information, see [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users of SAP Datasphere with any of the standard roles can consume data exposed by spaces of which they are a member. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the DW Consumer role.") :arrow_upper_right:.


    
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
    
5.  Based on the *Semantic Usage* of your entity, review and modify its *Columns*, *Attributes*, and/or *Measures*:

    -   *Fact* - Review the lists of measures and attributes \(see [Creating a Fact](Modeling-Data-in-the-Data-Builder/creating-a-fact-30089bd.md)\).
    -   *Dimension* - Review the list of attributes \(see [Creating a Dimension](Modeling-Data-in-the-Data-Builder/creating-a-dimension-5aae0e9.md)\).
    -   *Hierarchy* - Define the parent and child columns \(see [Creating an External Hierarchy](Modeling-Data-in-the-Data-Builder/creating-an-external-hierarchy-dbac7a8.md)\).
    -   *Text* - Review the list of attributes \(see [Create a Text Entity for Attribute Translation](Modeling-Data-in-the-Data-Builder/create-a-text-entity-for-attribute-translation-b25726d.md)\).
    -   *Relational Dataset* - Review the list of columns \(see [Columns](Acquiring-and-Preparing-Data-in-the-Data-Builder/columns-8f0f40d.md)\).

6.  Complete or consult other sections as appropriate:

    -   *Input Parameters* - Create input parameters to require the user to enter a value for use in calculated column, filter, and aggregation nodes \(see [Create an Input Parameter](create-an-input-parameter-53fa99a.md)\).
    -   *Persistency* - Persist the view data to improve performance \(see [Persist View Data](persist-view-data-9bd12cf.md)\).
    -   *Associations* - Create associations to other entities \(see [Create an Association](create-an-association-66c6998.md)\).
    -   *Data Access Controls* - Add data access controls to apply row-based security and control access to individual rows based on various criteria \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:\).
    -   *Business Purpose* - Provide a description, purpose, contacts, and tags to help other users understand your entity.
    -   *Dependent Objects* - If your entity is used as a source or association target for other entities, then they are listed here \(see [Review the Objects That Depend on Your Table or View](Creating-Finding-Sharing-Objects/review-the-objects-that-depend-on-your-table-or-view-ecac5fd.md)\).

7.  Click <span class="FPA-icons"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons"></span> \(Deploy\) to save and deploy it immediately.

    For more information, see [Saving and Deploying Objects](Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).


