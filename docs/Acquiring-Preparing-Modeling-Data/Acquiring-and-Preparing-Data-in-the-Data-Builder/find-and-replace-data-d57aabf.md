<!-- loiod57aabf6e59a434aad5f1d14d2d4004c -->

# Find and Replace Data

You can find and replace data in cells during data preparation.

Select one or more cells in a column, click in the *Create Transform* bar, select *Replace*, and complete the formula as follows:

```
Replace (<scope>) in [<Column>] matching "<value>" with "<value>" <...>
```

Where:

-   *<scope\>*: Choose the scope of the find/replace action::
    -   `cell` - Cells in the column matching *<value\>* 
    -   `all values` - All cells in the column.
    -   `content` - Strings in any cell in the column matching *<value\>*
    -   `null` - Cells containing null values.

-   <code>matching "<i class="varname">&lt;value&gt;</i>"</code> - Specify the string to find.
-   <code>with "<i class="varname">&lt;value&gt;</i>"</code> - Specify the string to replace with.
-   `...` - \[optional\] Choose `where` to specify a where clause:
    -   \[*<Column\>*\] - Specify the column to search for the where condition.
    -   <code>matches "<i class="varname">&lt;value&gt;</i>"</code> - Enter a value to match.


