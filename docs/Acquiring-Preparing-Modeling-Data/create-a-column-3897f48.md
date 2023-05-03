<!-- loio3897f480b9404e6f82de9bba410f17c0 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create a Column

Add a *Calculated Columns* node to create new columns and define calculations in them.



## Procedure

1.  Select an object in order to display its context tools, and click <span class="FPA-icons"></span> Calculated Columns.

    ![](images/Create_Column_Gif_0560169.gif)

    A calculated column node is created, its symbol is selected, and its properties are displayed in the side panel.

2.  Click <span class="FPA-icons"></span> \(Add New Calculated Column\) to create a new column.

    The new column properties are displayed in the side panel.

3.  Enter a *Business Name* and a *Technical Name* for the column, and specify its *Data Type*.

4.  Enter a SQL expression into the *Expression* field. You can use the following items in your SQL expression:

    -   *Insert Values* - Click to open the *Insert Value* dialog:

        > ### Note:  
        > -   The button is enabled when, in the *Expression* field, a column name is followed by the operator `=`, `>`, `<`, `!=`, `IN`, `BETWEEN`, or `LIKE`. Values from the selected column are listed in the *Insert Value* dialog.
        > 
        > -   You can insert values of the data types string, interger, boolean, date, and time. The data types binary and UUID aren't supported.

        Select available value\(s\) and click *Insert* to add them to your expression.

    -   *Functions* - Browse, select a category, or filter available functions \(see [SQL Functions Reference](sql-functions-reference-6d624a1.md)\). Click a function name to see its syntax or click elsewhere in its token to add it to your expression.
    -   *Columns* - Browse or filter available columns. Click a column name to see its properties or click elsewhere in its token to add it to your expression.
    -   *Parameters* - Browse or filter available input parameters \(see [Create an Input Parameter](create-an-input-parameter-53fa99a.md)\). Click a parameter name to see its properties or click elsewhere in its token to add it to your expression.
    -   *Other* - Browse available operators, predicates, and case expressions, and click one to add it to your expression \(see [SQL Reference](sql-reference-6a37cc5.md)\).

    For example, if you want to calculate the price of a product minus a 15% discount, enter ***Price\*0.85***.

    When working on a large expression, click <span class="FPA-icons"></span> \(Enter Full Screen\) to expand the expression editor.

5.  Click *Validate* to check if your expression is semantically correct, and fix any errors signaled. You can reference columns by name as well as HANA functions, operators, predicates, and case expressions. When you are satisfied, click the breadcrumbs at the top of the side panel to drill back up to the calculated column node properties.

6.  The list displays all the columns output by the node. You can:

    -   Filter the list with the *Search* box \(or by clicking <span class="FPA-icons"></span> Hide Unmodified Columns\) and reorder it.
    -   Modify the expression output by any column by clicking on the chevron on the right of its token.
    -   Delete a column that has been created in the node by clicking <span class="FPA-icons"></span> Delete Selected Calculated Column.

7.  Click <span class="FPA-icons"></span> \(Preview Data\) to open the *Data Preview* panel and review the data output by this node. For more information, see [Viewing or Previewing Data in Data Builder Objects](viewing-or-previewing-data-in-data-builder-objects-b338e4a.md).


