<!-- loio33dfe253bb4c416a9168471ca132adf8 -->

# Extract Text to a New Column

You can extract data from a text column to a new column during data preparation.

Select a column, click in the *Create Transform* bar, select *Extract*, and complete the formula as follows:

```
Extract [<unit>]from [<column name>][<location>] [<occurrence>] ["<value>"] [<include/exclude>]
```

Where:

-   *<unit\>* - Choose what to extract:
    -   `word` \[default\] - Extract text and stop at the nearest space.
    -   `everything` - Extract all text without regard to spaces.

-   *<location\>* - Choose where to find the unit to extract in relation to a string:
    -   `before` - Find the unit before a string.
    -   `after` - \[default\] Find the unit after a string.
    -   `between` - Find the unit between two strings.
    -   `containing` - Find the unit inside a string. For example, if your target is `ship`, both `ship` and `shipping` will be extracted.
    -   `equal to` - Extracts the specific target value if it exists in the cell.

-   *<occurrence\>* - Choose which occurrence of the value to search around:
    -   `first` - The first occurrence of the string.
    -   `last` - The last occurrence.
    -   `occurrence` - Specify a particular occurrence by entering a number \(1-10\).


For example:

-   To extract the first number from all cells in `MyColumn`, specify:

    ```
    Extract before first "" from [ MyColumn ]
    ```

    To extract all text between parenthesis from all cells in `MyColumn`, specify:

    ```
    Extract everything between "(" and ")" from [ MyColumn ]
    ```


