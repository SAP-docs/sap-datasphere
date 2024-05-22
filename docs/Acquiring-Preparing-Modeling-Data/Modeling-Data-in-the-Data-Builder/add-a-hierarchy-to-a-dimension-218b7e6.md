<!-- loio218b7e6bd60846dda2f03b789b389cb0 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add a Hierarchy to a Dimension

Add a hierarchy to your dimension to support drill-down and drill-up in BI clients.



## Context

You can specify the following types of hierarchy:

-   Parent-Child - the hierarchy is recursive, may have any number of levels, and is defined by specifying a parent column and a child column within the dimension. For example, a departmental hierarchy could be modeled with the `Parent Department ID` and `Department ID` columns.
-   Level-Based - the hierarchy is non-recursive, has a fixed number of levels, and is defined by specifying two or more level columns within the dimension. For example, a time hierarchy could be modeled with the: `Year`, `Quarter`, `Month`, `Week`, and `Day` columns.
-   External Hierarchy - the parent-child hierarchy information is contained in a seperate entity, which needs to be associated with the dimension \(see [Creating an External Hierarchy](creating-an-external-hierarchy-dbac7a8.md)\).

> ### Note:  
> You can create more than one hierarchy for a dimension, but they must all be of the same type \(internal and external Parent-Child hierarchies can be mixed\).

The following hierarchy features are not supported:

-   Multiple parents
-   Unassigned members
-   Cycle handling



<a name="loio218b7e6bd60846dda2f03b789b389cb0__steps_j1v_nzx_t4b"/>

## Procedure

1.  Open your dimension and click <span class="FPA-icons-V3"></span> \(Hierarchies\) to open the *Hierarchies* dialog.

    > ### Note:  
    > For tables, the editor for hierarchies is in the menu bar on top of the canvas. For views and entity-relationship models, it is on the properties panel.

2.  Click <span class="FPA-icons-V3"></span> \(Add\)and then select:

    -   *Parent-Child Hierarchy* or *Level-Based Hierarchy* - To create a new hierarchy inside the dimension. Complete the following properties as appropriate:


        <table>
        <tr>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Business Name
        
        </td>
        <td valign="top">
        
        Enter a descriptive name to help users identify the object. This name can be changed at any time.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Technical Name
        
        </td>
        <td valign="top">
        
        Displays the name used in scripts and code, synchronized by default with the *Business Name*.

        To override the default technical name, enter a new one in the field. Technical names can contain only alphanumeric characters and underscores.

        > ### Note:  
        > Once the object is saved, the technical name can no longer be modified.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Parent Column / Child Column
        
        </td>
        <td valign="top">
        
        \[parent-child hierarchies\] Select the parent and child columns that represent the hierarchy. The child column must be a key column and the parent and child columns must have the same data type.

        If your dimension has more than one key column, then you should click <span class="FPA-icons-V3"></span> \(Add\) to add an additional line for each key column.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Levels
        
        </td>
        <td valign="top">
        
        \[level-based hierarchies\] Click <span class="FPA-icons-V3"></span> \(Add\) to add a level and select the column containing values for the highest level of your hierarchy. Click <span class="FPA-icons-V3"></span> \(Add\) again to add the next level down. Keep adding levels until you reach the lowest level of your hierarchy.

        For example, in a `Products` dimension, you may add three levels containing the columns `Product Line`, `Product Category`, and `Product`.

        > ### Note:  
        > Level-based hierarchies are not supported for dimensions with more than one key column.


        
        </td>
        </tr>
        </table>
        
    -   *External Hierarchy* - To open the External Hierarchy dialog:

        1.  Select the external hierarchy and click *OK* to show the mapping editor.
        2.  Drag the key column of your dimension and drop it on the child column of the hierarchy to map them.

            > ### Note:  
            > The child attribute must be a key column.

        3.  Click *Add* to add the external hierarchy and return to the *Hierarchies* dialog.

        > ### Note:  
        > Alternatively, you can add an external hierarchy in the *Associations* section of the dimension property sheet. Click <span class="FPA-icons-V3"></span> \(Create Association\) and select *Hierarchy Association*. Drag and drop the key attribute of your dimension on the child column of the hierarchy to map them.


3.  Click *Close* to close the dialog and return to your dimension.


