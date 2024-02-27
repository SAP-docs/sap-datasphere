<!-- loio775e0ab758e54c58af5a240294d234f2 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create an SQL View Transform

Create an SQL view transform to combine and transform data in a powerful SQL editor. You can choose between writing a standard SQL query using `SELECT` statements and operators such as `JOIN` and `UNION`, or use SQLScript to produce a table function. You can drag sources from the *Repository*, and easily view the columns defined for your output structure in the side panel.



## Context

If you are not comfortable with SQL, you can still build a view by using the *Graphical View Editor*, which lets you compose SQL code using an intuitive graphical interface. For more information, see [Create a Graphical View Transform](create-a-graphical-view-transform-c65e37c.md).



## Procedure

1.  On the *New Transformation Flow* screen, click the *View Transform* node.

2.  Create a new *SQL View Transform* for your transformation flow by clicking the *SQL View Transform* button. The system displays the *SQL View Editor*.

3.  In the side panel, select the language that you want to use. You can choose between:

    -   *SQL \(Standard Query\)* - \[default\] Create a standard SQL query, based around `SELECT` statements \(see [SQL Reference](../sql-reference-6a37cc5.md)\).
    -   *SQLScript \(Table Function\)* - Use SQLScript with support for `IF` statements, loops, and other more complex structures \(see [SQLScript Reference](../sqlscript-reference-6c46c6a.md)\).

    > ### Note:  
    > SAP Datasphere supports a subset of the SQL functions supported by SAP HANA Cloud. For more information, see [SQL Functions Reference](../sql-functions-reference-6d624a1.md).

4.  Enter your code in the *SQL View Editor*. You can:

    -   Access auto-complete suggestions for keywords and object names including source tables by typing.

    -   Drag source tables from the *Repository* to the *SQL View Editor*.

        > ### Note:  
        > If the delta capture setting is enabled for a source table, the columns *Change Date* and *Change Type* are automatically mapped to these columns in the target table. Mapping these columns \(or a calculated column that contains the content of these columns\) to any other target column is not permitted. For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).

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

        > ### Note:  
        > If you add a new column to a table, but do not deploy the table, the system will display an error message if you validate SQL code that references that column.

        SQL errors and warnings are shown in the *Errors* pane at the bottom of the editor. Problems with the output structure are shown on the *Validation Messages* button in the side panel header.

        > ### Note:  
        > If your SQLScript is complicated, SAP Datasphere may not be able to determine the output structure. In this case, you are requested to review the list of columns. Click the *Edit* button to add or delete buttons or change column names and data types.

    -   Preview the data being output by the view by clicking <span class="SAP-icons-V5"></span> \(Show or hide data preview\)\(see [Viewing or Previewing Data in Data Builder Objects](../viewing-or-previewing-data-in-data-builder-objects-b338e4a.md)\).

        > ### Note:  
        > It is not possible to preview data if you are using SQLScript.


5.  Review the list of columns \(see [Columns](columns-8f0f40d.md)\).

6.  Click the *Back* button to save your work and return to the *Transformation Flow Editor*. You can then add or create a target table for the transformation flow. For more information, see [Add or Create a Target Table](add-or-create-a-target-table-0950746.md).


