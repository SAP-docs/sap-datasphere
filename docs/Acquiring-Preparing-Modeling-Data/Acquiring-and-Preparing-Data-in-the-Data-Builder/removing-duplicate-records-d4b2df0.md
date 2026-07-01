<!-- loiod4b2df06bb4a4dcc973413fc8ca7ee32 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Removing Duplicate Records

Remove duplicate records from datasets by defining sorting criteria and specifying which column combinations should be checked for duplicates. Use it to clean your data after adding new sources by removing redundant entries based on customizable deduplication rules.

After adding a new source, you might encounter duplicate records in your dataset. The *Remove Duplicate Records* operator allows you to efficiently remove these duplicates from your transformation flow:

1.  Select the flow source table to display the context menu and select <span class="SAP-icons-V5"></span> *Remove Duplicate Records*.
2.  Select the *Remove Duplicate Records* node to open its *Settings* panel. You can:
    1.  *Sort Records by*: Sorting records allows the user to decide which duplicate records to drop based on the sorting order.
        1.  Click the *Edit* button to open the *Sort Records by* dialog.
        2.  In the *Select Columns* section, choose the columns you want to use for sorting the records.
        3.  In the *Sort Order* section, specify whether the sort order should be *Ascending* or *Descending*.
        4.  In the *Null Value Position* section, determine whether null values should be positioned *First* or *Last* in the sorted order.
        5.  Click *Save* to apply your sorting settings. The selected columns and their sorting preferences will be displayed in the *Settings* panel under the *Sort Records* by section.

    2.  *Remove Duplicate Values*: Select the columns containing duplicate values for which you want to drop records. If you select two or more columns, records will only be dropped if the combination of values is duplicated.
        1.  Click the *Value Help* button to specify which columns contain the duplicate values.
        2.  Select the columns whose values will be checked for duplicates.
        3.  Click *Save* to apply your duplicate removal criteria. The selected columns will be displayed in the *Settings* panel under the *Remove Duplicate Values* section.



> ### Note:  
> For Delta runs, the *Remove Duplicate Records* node works only on delta records.

