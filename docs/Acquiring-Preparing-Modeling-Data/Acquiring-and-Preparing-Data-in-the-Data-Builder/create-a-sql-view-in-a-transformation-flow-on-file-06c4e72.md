<!-- loio06c4e72bcbee46568be499c77a3a0d00 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a SQL View in a Transformation Flow on File

Create an SQL view transform to combine and transform data in a powerful SQL editor. You can choose between writing a standard SQL query using `SELECT` statements and operators such as `JOIN` and `UNION`. You can drag sources from the *Repository*, and easily view the columns defined for your output structure in the side panel.



## Context

If you are not comfortable with SQL, you can still build a view transform by using the *Graphical View Editor*, which lets you compose SQL code using an intuitive graphical interface. For more information, see [Create a Graphical View in a Transformation Flow](../create-a-graphical-view-in-a-transformation-flow-c65e37c.md).

You cannot save and deploy the view transform \(the secondary editor\) separately from the transformation flow \(the primary editor\). To exit the view transform editor, click the <span class="FPA-icons-V3"></span> \(Navigate Back\) button in the editor toolbar.



## Procedure

1.  On the *New Transformation Flow* screen, click the *View Transform* node.

2.  Create a new *SQL View Transform* for your transformation flow by clicking the *SQL View Transform* button. The system displays the *SQL View Editor*.

    The only language available is *SQL \(Apache Spark SQL\)*. See [SQL \(Apache Spark SQL\) Syntax Support in Transformation Flow Operators](sql-apache-spark-sql-syntax-support-in-transformation-flow-opera-3de7a48.md).

3.  Enter your code in the *SQL View Editor*. You can:

    -   Access auto-complete suggestions for keywords and object names including source tables by typing.

    -   Drag source objects to the *SQL View Editor*.

        > ### Note:  
        > If the delta capture setting is enabled for a source table, the columns *Change Date* and *Change Type* are automatically mapped to these columns in the target table. Mapping these columns \(or a calculated column that contains the content of these columns\) to any other target column is not permitted. For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).

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
        									
        									SELECT `ID`,
        									`Date`,
        									--	`Sales Person`, comment out a line
        									`City`, -- comment at end of line
        									`Net Sales`
        									FROM /* mid-line comment */ `Sales`
        ```

    -   Format your SQL code by clicking *Format*.
    -   Validate your code and update the display of your output structure in the side panel at any time by clicking <span class="FPA-icons-V3"></span> \(Validate\).

        > ### Note:  
        > If you add a new column to a table, but do not deploy the table, the system will display an error message if you validate SQL code that references that column.

        SQL errors and warnings are shown in the *Errors* pane at the bottom of the editor. Problems with the output structure are shown on the *Validation Messages* button in the side panel header.

        > ### Note:  
        > -   Use backquotes to escape spaces or reserved keywords in column names. You can also leave identifiers unquoted if they don't contain spaces or reserved keywords. Double quotes are not supported.
        > -   If your code is complicated, SAP Datasphere may not be able to determine the output structure. In this case, you are requested to review the list of columns. Click the *Edit* button to add or delete buttons or change column names and data types.


4.  Review the list of columns \(see [Columns](columns-8f0f40d.md)\).

5.  Click the <span class="FPA-icons-V3"></span> \(Navigate Back\) button to save your work and return to the *Transformation Flow Editor*. You can then add or create a target table for the transformation flow. For more information, see [Create or Add a Target Table to a Transformation Flow](../create-or-add-a-target-table-to-a-transformation-flow-0950746.md).


