<!-- loio81920e4d583f45fd8761c662d3c8abab -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Creating an SQL View

Create a view to query sources in a powerful SQL editor. You can choose between writing a standard SQL query using `SELECT` statements and operators such as `JOIN` and `UNION`, or use SQLScript to produce a table function. You can drag sources from the *Source Browser*, and specify measures and other aspects of your output structure in the side panel.



## Context

In this example, a view is created in which:

-   Various columns are selected from the `Sales` and `Products` entities and given aliases via the `AS` keyword.
-   A new, calculated column, `Unit_Price` is created using the `ROUND()` function.
-   The `FROM` clause defines an `INNER JOIN` between the entities on their `Product_ID` columns.
-   The `WHERE` clause filters the results by the `Product_Line`, which must be `Electronics`.
-   The `ORDER BY` clause orders the results by the value of `Gross_Sales` in descending order.

```
SELECT
  "Sales"."Date" AS "Date",
  "Products"."Product_ID" AS "Product_ID",
  "Products"."Line" AS "Product_Line",
  "Products"."Category" AS "Product_Category",
  "Products"."Product" AS "Product",
  ROUND("Sales"."Gross_Sales" / "Sales"."Quantity", 2) AS "Unit_Price",
  "Sales"."Gross_Sales" AS "Gross_Sales"
FROM ("Sales" INNER JOIN "Products" ON "Sales"."Product_ID" = "Products"."Product_ID")
WHERE "Products"."Product_Line" = "Electronics"
ORDER BY "Gross_Sales" DESC
```

> ### Note:  
> -   If you define an alias in your `SELECT` statement, then you must use the alias \(rather than the source name\) consistently in all clauses in the statement.
> -   The `TOP` keyword is not supported in SAP Datasphere, but you can use the `LIMIT` keyword instead, at the end of your `ORDER BY` clause:
> 
>     ```
>     ORDER BY "Gross_Sales" DESC LIMIT 5
>     ```

If you are not comfortable with SQL, you can still build a view in SAP Datasphere by using the Graphical View editor, which lets you compose SQL code using an intuitive graphical interface \(see [Creating a Graphical View](creating-a-graphical-view-27efb47.md)\).

> ### Note:  
> There are two methods for exposing view data for consumption outside SAP Datasphere:
> 
> -   SAP Analytics Cloud \(and Microsoft Excel via an SAP add-in\) do not consume view data directly. Set the *Semantic Usage* of your view to *Fact* and then add it to an analytic model to expose it \(see [Creating an Analytic Model](Modeling-Data-in-the-Data-Builder/creating-an-analytic-model-e5fbe9e.md)\). There is no need to enable the *Expose for Consumption* switch.
> -   Other third-party BI clients, tools, and apps can consume data from views with any *Semantic Usage* via OData or ODBC if the *Expose for Consumption* switch is enabled.
> 
> For more information, see [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users with any of the standard roles can consume data exposed by spaces they are assigned to. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted a consumer role.") :arrow_upper_right:.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New SQL View* to open the editor.

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

    -   Validate your code and update the display of your output structure in the side panel at any time by clicking <span class="FPA-icons-V3"></span> \(Validate SQL and Preview Data\).

        SQL errors and warnings are shown in the *Errors* pane at the bottom of the editor. Problems with the output structure are shown on the *Validation Messages* button in the side panel header.

        > ### Note:  
        > If your SQLScript is complicated, SAP Datasphere may not be able to determine the output structure. In this case, you are requested to review the list of columns. Click the *Edit* button to add or delete buttons or change column names and data types.

    -   Preview the data being output by the view by clicking <span class="SAP-icons-V5"></span> \(Show or hide data preview\)\(see [Viewing Object Data](viewing-object-data-b338e4a.md)\).

        You cannot view data in an SQL view if any of its sources is shared from another space and has an input parameter.


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
    
    Release State
    
    </td>
    <td valign="top">
    
    Specifies whether the object is released, providing modelers and consumers with confidence that it will remain available in its current form for the foreseeable future. 

    For more information, see [Releasing Stable Views for Consumption](releasing-stable-views-for-consumption-5b99e9b.md).
    
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
    
    Select the way your entity should be used for data modeling purposes. 

    Choose from the following:

    -   *Fact* - Contains one or more measures and attributes. A fact typically has associations pointing to one or more dimensions and is consumed by analytic models \(see [Create a Fact to Contain Measurable Data](Modeling-Data-in-the-Data-Builder/create-a-fact-to-contain-measurable-data-30089bd.md)\).
    -   *Dimension* - Contains attributes containing master data like a product list or store directory, and supporting hierarchies \(see [Create a Dimension to Categorize Data](Modeling-Data-in-the-Data-Builder/create-a-dimension-to-categorize-data-5aae0e9.md)\).
    -   *Hierarchy* - Contains attributes defining a parent-child hierarchy \(see [Create an External Hierarchy for Drill-Down](Modeling-Data-in-the-Data-Builder/create-an-external-hierarchy-for-drill-down-dbac7a8.md)\).
    -   *Hierarchy with Directory* - Contains one or more parent-child hierarchies \(see [Create a Hierarchy with Directory](Modeling-Data-in-the-Data-Builder/create-a-hierarchy-with-directory-36c39ee.md)\).
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
    
    Enable this option to make the view available for consumption outside SAP Datasphere via OData or ODBC/JDBC. 

    This option is not required if you want to expose your data through an analytic model \(see [Creating an Analytic Model](Modeling-Data-in-the-Data-Builder/creating-an-analytic-model-e5fbe9e.md)\). For an overview about making your data accessible outside SAP Datasphere, see [Exposing Data For Consumption](Modeling-Data-in-the-Data-Builder/exposing-data-for-consumption-40ec77e.md).
    
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

    For more information, see [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Deployed On
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the date and time of the last deployment.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Data Validation Status
    
    </td>
    <td valign="top">
    
    Displays the status of the last data validation.

    Click the button to open the *Data Validation* panel \(see [Validating View Data](validating-view-data-ed4063d.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Validated On
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the date and time of the last data validation.
    
    </td>
    </tr>
    </table>
    
5.  Based on the *Semantic Usage* of your entity, review and modify its *Columns*, *Attributes*, and/or *Measures*:

    -   *Fact* - Review the lists of measures and attributes \(see [Create a Fact to Contain Measurable Data](Modeling-Data-in-the-Data-Builder/create-a-fact-to-contain-measurable-data-30089bd.md)\).
    -   *Dimension* - Review the list of attributes \(see [Create a Dimension to Categorize Data](Modeling-Data-in-the-Data-Builder/create-a-dimension-to-categorize-data-5aae0e9.md)\).
    -   *Hierarchy* - Define the parent and child columns \(see [Create an External Hierarchy for Drill-Down](Modeling-Data-in-the-Data-Builder/create-an-external-hierarchy-for-drill-down-dbac7a8.md)\).
    -   *Hierarchy with Directory* - Define all the necessary attributes and settings \(see [Create a Hierarchy with Directory](Modeling-Data-in-the-Data-Builder/create-a-hierarchy-with-directory-36c39ee.md)\).
    -   *Text* - Review the list of attributes \(see [Create a Text Entity for Attribute Translation](Modeling-Data-in-the-Data-Builder/create-a-text-entity-for-attribute-translation-b25726d.md)\).
    -   *Relational Dataset* - Review the list of columns \(see [Columns](Acquiring-and-Preparing-Data-in-the-Data-Builder/columns-8f0f40d.md)\).
    -   *Analytical Dataset \(Deprecated\)* - Use *Fact* instead \(see [Analytical Datasets \(Deprecated\)](Modeling-Data-in-the-Data-Builder/analytical-datasets-deprecated-70dab71.md).

6.  Complete or consult other sections as appropriate:

    -   *Input Parameters* - Create input parameters to require the user to enter a value for use in calculated column, filter, and aggregation nodes \(see [Create an Input Parameter in a Graphical View](create-an-input-parameter-in-a-graphical-view-53fa99a.md)\).
    -   *Data Persistence* - Persist the view data to improve performance \(see [Persist Data in a Graphical or SQL View](persist-data-in-a-graphical-or-sql-view-9bd12cf.md)\).
    -   *Associations* - Create associations to other entities \(see [Create an Association to Define a Semantic Relationship Between Entities](Modeling-Data-in-the-Data-Builder/create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md)\).
    -   *Data Access Controls* - Add data access controls to apply row-based security and control access to individual rows based on various criteria \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:\).
    -   *Business Purpose* - Provide a description, purpose, contacts, and tags to help other users understand your entity.
    -   *Dependent Objects* - If your entity is used as a source or association target for other entities, then they are listed here \(see [Review the Objects That Depend on Your Table or View](review-the-objects-that-depend-on-your-table-or-view-ecac5fd.md)\).

7.  Click <span class="FPA-icons-V3"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy it immediately.

    For more information, see [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md).

8.  The tools in the editor toolbar help you work with your object throughout its lifecycle:


    <table>
    <tr>
    <th valign="top">

    Tool
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Save\)
    
    </td>
    <td valign="top">
    
    Save your changes to the design-time repository. You can use *Save As* to create a copy of the object. 

    See [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Deploy\)
    
    </td>
    <td valign="top">
    
    Deploy your changes to make them available in the run-time environment.

    See [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Share\)
    
    </td>
    <td valign="top">
    
    Share the object to other spaces. 

    See [Sharing Entities and Task Chains to Other Spaces](Creating-Finding-Sharing-Objects/sharing-entities-and-task-chains-to-other-spaces-64b318f.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Source Browser\)
    
    </td>
    <td valign="top">
    
    Show the *Source Browser* panel to drag sources into the editor. 

    See [Using the Source Browser](using-the-source-browser-7d2b21d.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Preview Data\)
    
    </td>
    <td valign="top">
    
    Open the *Data Preview* panel to preview the data output by the view. 

    See [Viewing Object Data](viewing-object-data-b338e4a.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Export\)
    
    </td>
    <td valign="top">
    
    Export the object to a CSN/JSON file. 

    See [Exporting Objects to a CSN/JSON File](Creating-Finding-Sharing-Objects/exporting-objects-to-a-csn-json-file-3916101.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Edit Custom CSN Annotations\)
    
    </td>
    <td valign="top">
    
    Work with custom CSN annotations that are not otherwise supported by the interface. 

    See [Edit Custom CSN Annotations in a View or Table](edit-custom-csn-annotations-in-a-view-or-table-820d013.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Impact and Lineage Analysis\)
    
    </td>
    <td valign="top">
    
    Open the *Impact and Lineage Analysis* graph for the object. 

    See [Impact and Lineage Analysis](impact-and-lineage-analysis-9da4892.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-TNT-V3"></span> \(Generate OData Request\)
    
    </td>
    <td valign="top">
    
    Open the *Generate OData Request* dialog to prepare access to the OData API. 

    See [Consume Data via the OData API](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/7a453609c8694b029493e7d87e0de60a.html "You can connect to the OData API and consume data exposed as views or analytic models in SAP Analytics Cloud and other clients, tools, and apps that are capable of accessing an OData service and authenticating via an OAuth client.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Details
    
    </td>
    <td valign="top">
    
    Toggles the display of the *Properties* panel.
    
    </td>
    </tr>
    </table>
    

