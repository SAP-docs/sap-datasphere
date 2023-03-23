<!-- loiod32f91fdf46643ba9a1d913d8e398686 -->

# Filter and Delete Rows

You can filter data and delete any rows that match \(or do not match\) the criteria during data preparation.

Select one or more cells in a column, click in the *Create Transform* bar, select *Filter*, and complete the formula as follows:

```
Filter values in [<Column>] ][<criterion>] "<values>"
```

Where:

-   *<criterion\>* - Choose the criterion type on which to filter and delete rows:
    -   `matching` - Matching any of the specified *<values\>*
    -   `not matching` - \[default\] Not matching any of the specified *<values\>*
    -   `between` - \[numeric columns\] Between the *<from\>* and *<to\>* values
    -   `matching null` - Containing null values
    -   `not matching null` - Containing any non-null *<values\>*.

-   *<values\>* - Enter the strings to match against, using commas to separate multiple values.

