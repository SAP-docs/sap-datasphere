<!-- loio3f0d747224bd4660a999c3e35817e73f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Apply Data Transforms

You can perform data preparation transformations to modify the list of columns to be created, to delete rows, and to modify data in cells before creating your table.

> ### Note:  
> For many transformations, you can hover over the menu item to see a preview of the effect of the transformation. To confirm the transformation, press [Enter\] or click the checkmark in the *Create Transform* bar.



<a name="loio3f0d747224bd4660a999c3e35817e73f__section_dwm_4vb_z4b"/>

## Modify Columns

Modify the columns to be created in any of the following ways:

-   Delete columns - Select one or more columns and click <span class="FPA-icons"></span> \(Menu\)** \> *Delete Column*.
-   Duplicate a column - Select a column and click <span class="FPA-icons"></span> \(Menu\)** \> *Duplicate Column*.
-   Concatenate two or more text columns together - Select a column, click in the *Create Transform* bar, select *Concatenate*, and complete the formula \(see [Concatenate Columns](concatenate-columns-819b01b.md)\).
-   Split a text column on a delimiter character - Select a column, click in the *Create Transform* bar, select *Split*, and complete the formula \(see [Split a Column](split-a-column-8b15a70.md)\).
-   Extract text to a new column - Select a column, click in the *Create Transform* bar, select *Extract*, and complete the formula \(see [Extract Text to a New Column](extract-text-to-a-new-column-33dfe25.md)\).
-   Change the case of a text column - Select a column, click in the *Create Transform* bar, select *Change*, and complete the formula \(see [Change the Case of a Text Column](change-the-case-of-a-text-column-b7e2102.md)\).



<a name="loio3f0d747224bd4660a999c3e35817e73f__section_ysh_5vb_z4b"/>

## Delete Rows

Reduce the amount of data to be imported by deleting rows in either of the following ways:

-   Select one or more values in a column and:
    -   Click <span class="FPA-icons"></span> \(Menu\)** \> *Delete Selected Rows* to delete all rows where the column contains values in your selection.
    -   Click <span class="FPA-icons"></span> \(Menu\)** \> *Keep Selected Rows* to delete all rows where the column contains values not in your selection.

-   Click in the *Create Transform* bar, select *Filter*, and complete the formula \([Filter and Delete Rows](filter-and-delete-rows-d32f91f.md)\).



<a name="loio3f0d747224bd4660a999c3e35817e73f__section_ed3_5vb_z4b"/>

## Modify Cell Data

-   Replace data in cells - Select one or more cells in a column containing the values you want to modify, and:
    -   Click <span class="FPA-icons"></span> \(Transform\) and select one of the proposed replacements.
    -   Click in the *Create Transform* bar, select *Replace*, and complete the formula \(see [Find and Replace Data](find-and-replace-data-d57aabf.md)\).




<a name="loio3f0d747224bd4660a999c3e35817e73f__section_ip5_2wb_z4b"/>

## Undo and Redo Transformations

You can undo and redo transformations with the <span class="FPA-icons"></span> \(Undo\) and <span class="FPA-icons"></span> Redo buttons on the toolbar or in the *Transform Log*.

You can review the history of your transformations in the *Transform Log*. Hover over a specific transformation to highlight the impacted column. To roll back a change, click <span class="SAP-icons"></span> \(Undo\) to delete the entry.

> ### Note:  
> You can undo a transformation even out of sequential order if it displays an <span class="SAP-icons"></span> \(Undo\) button. If the button is not available, then other transformations depend on this transformation, and these must be deleted before you can undo it.

