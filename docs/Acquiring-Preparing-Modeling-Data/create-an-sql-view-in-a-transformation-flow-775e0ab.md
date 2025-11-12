<!-- loio775e0ab758e54c58af5a240294d234f2 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create an SQL View in a Transformation Flow

Create an SQL view transform to combine and transform data in a powerful SQL editor. You can choose between writing a standard SQL query using `SELECT` statements and operators such as `JOIN` and `UNION`, or use SQLScript to produce a table function. You can drag sources from the *Repository*, and easily view the columns defined for your output structure in the side panel.



## Context

If you are not comfortable with SQL, you can still build a view transform by using the *Graphical View Editor*, which lets you compose SQL code using an intuitive graphical interface. For more information, see [Create a Graphical View in a Transformation Flow](create-a-graphical-view-in-a-transformation-flow-c65e37c.md).

When working in a view transform, you are using an editor similar to the standard view editors with the following modifications:

-   View transforms do not support creating input parameters or adding data access controls, and the output node does not contain any information except for the list of columns passed to the target node.
-   If you add an entity containing input parameters as a source to a view transform, then you must set a value for each input parameter.

    > ### Note:  
    > If you add a remote table shared from an SAP BW bridge space and configured to load delta changes as a source:
    > 
    > -   It is no longer possible to preview the data being output by the view transform.
    > -   The system adds the following read-only input parameters to the view transform:
    >     -   REQTSN\_LOW - When loading delta changes, the value of this input parameter is the watermark. When loading all active records, the value of this input parameter is the minimum timestamp. For more information, see [Watermarks](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/890897f00a4944c7a6f90d3816a8d4c6.html "When you run a transformation flow that loads delta changes to a target table, the system uses a watermark (a timestamp) to track the data that has been transferred.") :arrow_upper_right:.
    >     -   REQTSN\_HIGH - The value of this input parameter is the maximum timestamp.
    >     -   EXTRACTION\_MODE - The value of this input parameter is DELTA\_AI to indicate the loading of delta changes from the remote table.

-   You cannot save and deploy the view transform \(the secondary editor\) separately from the transformation flow \(the primary editor\). To exit the view transform editor, click the <span class="FPA-icons-V3"></span> \(Navigate Back\) button in the editor toolbar.



## Procedure

1.  On the *New Transformation Flow* screen, click the *View Transform* node.

2.  Create a new *SQL View Transform* for your transformation flow by clicking the *SQL View Transform* button. The system displays the *SQL View Editor*.

3.  In the side panel, select the language that you want to use. You can choose between:

    -   *SQL \(Standard Query\)* - \[default\] Create a standard SQL query, based around `SELECT` statements \(see [SQL Reference](sql-reference-6a37cc5.md)\).
    -   *SQLScript \(Table Function\)* - Use SQLScript with support for `IF` statements, loops, and other more complex structures \(see [SQLScript Reference](sqlscript-reference-6c46c6a.md)\).

    > ### Note:  
    > SAP Datasphere supports a subset of the SQL functions supported by SAP HANA Cloud. For more information, see [SQL Functions Reference](sql-functions-reference-6d624a1.md).

    > ### Note:  
    > If you use an SQL view transform to load delta changes from a remote table located in an SAP BW bridge space, the language must be *SQL \(Standard Query\)*. *SQLScript \(Table Function\)* is not supported.

4.  Enter your code in the *SQL View Editor*. You can:

    -   Access auto-complete suggestions for keywords and object names including source tables by typing.

    -   Drag source objects to the *SQL View Editor*.

        > ### Note:  
        > If you add a source view that has input parameters, the source and its parameters will be added to your code and you will need to enter a value to resolve each parameter.

        > ### Note:  
        > If the delta capture setting is enabled for a source table, the columns *Change Date* and *Change Type* are automatically mapped to these columns in the target table. Mapping these columns \(or a calculated column that contains the content of these columns\) to any other target column is not permitted. For more information, see [Capturing Delta Changes in Your Local Table](Acquiring-and-Preparing-Data-in-the-Data-Builder/capturing-delta-changes-in-your-local-table-154bdff.md).

        > ### Note:  
        > The *Change Type* column does not support null values. Ensure that no null values are written to the *Change Type* column of the target table.

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
        > -   Tables, columns, and aliases cannot be found if double quotes are missing from the `SELECT` function.
        > -   If your SQLScript is complicated, SAP Datasphere may not be able to determine the output structure. In this case, you are requested to review the list of columns. Click the *Edit* button to add or delete buttons or change column names and data types.

    -   View the data being output by the deployed view by clicking <span class="SAP-icons-V5"></span> \(Data Viewer\). For more information, see [Viewing Object Data](viewing-object-data-b338e4a.md).

        > ### Note:  
        > It is possible to preview data when using SQLScript \(Table Function\), except when the transformation flow is undeployed or has unsaved changes.


5.  Review the list of columns \(see [Columns](Acquiring-and-Preparing-Data-in-the-Data-Builder/columns-8f0f40d.md)\).

6.  Click the <span class="FPA-icons-V3"></span> \(Navigate Back\) button to save your work and return to the *Transformation Flow Editor*. You can then add or create a target table for the transformation flow. For more information, see [Create or Add a Target Table to a Transformation Flow](create-or-add-a-target-table-to-a-transformation-flow-0950746.md).


