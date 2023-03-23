<!-- loio2c7948fdd1a14105a27d0c03af82a56b -->

# Define Mapping

Create mappings to specify how the source data is to be changed on its way into the target.



## Procedure

1.  Select the source object for which you want to define mapping.

2.  Choose *Add Projection*.

3.  Go to the *Mapping* tab of the *Projections* dialog and enter a name for your mapping.

4.  Enter your mapping. You have the following options:

    -   Change the name of a target column: By default, the system uses the name of the corresponding source column as the target column name. To change this, overwrite the default name with the name you want to use.

    -   Change the data type: To change the data type, select the relevant one from the dropdown list of data types. Where applicable, you can make further changes. For data type 'string', for example, you can change the length.

    -   Change the source mapping: Choose the relevant entry from the dropdown list of source columns.

    -   Edit the target content: Mark *Edit* for the relevant row and enter the content you want to see. All fields of the target column are then automatically filled with the content you enter here.

        > ### Note:  
        > The *Primary Key* column is for information purposes. You cannot change whether a column is part of the primary key or not.

    -   Add a new column: Choose *Add* and enter the necessary values for the new column.

    -   Remove a column: Select the relevant column and choose *Remove*.

        > ### Note:  
        > It is not possible to remove primary key columns or to map a key column in the source to multiple non-key columns in the target.

    -   Change the column sequence: Select the column that you want to move to a different place and use the *Up* and *Down* buttons.
    -   Restore default settings: To discard any changes and restore the default mapping settings, choose *Auto-Map*.

        > ### Caution:  
        > If you choose *Auto-Map*, the system overwrites **all** mapping changes you made for this object with the default values.



