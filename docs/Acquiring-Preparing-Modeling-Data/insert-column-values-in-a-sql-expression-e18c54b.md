<!-- loioe18c54b4128f47538dfd40875c448bf9 -->

# Insert Column Values in a SQL Expression

When entering SQL in an *Expression* field, you may need to provide values from one or more columns. Enter a column name followed by an operator to enable the *Insert Values* button, which lets you browse and select values from that column and insert them in your expression.

For example, you could enter `ProductID IN` and then click *Insert Values* to select multiple product IDs to complete your expression.

1.  Enter a column name followed by an operator in your *Expression* field to enable the *Insert Values* button.

    The following operators are supported:

    -   `=`, `>`, `<`, `>=`, `<=`, `!=`, `LIKE`- Insert a single value.
    -   `BETWEEN` - Insert two values.
    -   `IN` - Insert any number of values.

    You can insert values of the data types string, integer, boolean, date, and time. The data types binary and UUID aren't supported.

2.  Click *Insert Values* to open the *Insert Values* dialog, which lists the values available in the column at this point in the construction of your view.

    You can search for a value or page through the values. When you select a value, it is added to the *Selected Values* list. If necessary, you can search and select and then enter a new value to search on to add further values to the *Selected Values* list.

3.  Select the value or values you want to insert and then click *Insert*.

    The values are inserted into the expression.

    > ### Note:  
    > Manual formatting may be required after inserting values.

    If you have inserted values to make a valid expression and then want to modify your values, you must edit your expression to make it invalid. For example by removing the closing bracket from `Column3 IN (2, 5, 6, 9)` to give `Column3 IN (2, 5, 6, 9`, and then click *Insert Values* again.


