<!-- loio8b15a70e6d3a4f2499f2fb24e82c53f0 -->

# Split a Column

You can split a text column on a delimiter character during data preparation.

Select a column, click in the *Create Transform* bar, select *Split*, and complete the formula as follows:

```
Split [<column>] on "<string>" repeat "<number>"
```

Where:

-   *<string\>* - \[required\] Enter a string to trigger the split.
-   *<number\>* - \[default="1"\] Enter the number of times the split can be applied \(and hence the number of additional columns to create\).

