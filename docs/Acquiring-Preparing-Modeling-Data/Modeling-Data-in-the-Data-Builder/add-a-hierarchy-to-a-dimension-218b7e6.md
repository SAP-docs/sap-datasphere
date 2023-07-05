<!-- loio218b7e6bd60846dda2f03b789b389cb0 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add a Hierarchy to a Dimension

Add a hierarchy to your dimension to support drill-down and drill-up in BI clients.



## Context

You can specify the following types of hierarchy:

-   Parent-Child - the hierarchy is recursive, may have any number of levels, and is defined by specifying a parent column and a child column within the dimension. For example, a departmental hierarchy could be modeled with the `Parent Department ID` and `Department ID` columns.
-   Level-Based - the hierarchy is non-recursive, has a fixed number of levels, and is defined by specifying two or more level columns within the dimension. For example, a time hierarchy could be modeled with the: `Year`, `Quarter`, `Month`, `Week`, and `Day` columns.
-   External Hierarchy - the parent-child hierarchy information is contained in a seperate entity, which needs to be associated with the dimension.

> ### Note:  
> You can create more than one hierarchy for a dimension, but they must all be of the same type \(internal and external Parent-Child hierarchies can be mixed\).

The following hierarchy features are not supported:

-   Multiple parents
-   Unassigned members
-   Cycle handling



<a name="loio218b7e6bd60846dda2f03b789b389cb0__steps_j1v_nzx_t4b"/>

## Procedure

1.  Open your dimension and click <span class="FPA-icons"></span> \(Hierarchies\) to open the *Hierarchies* dialog.

    > ### Note:  
    > For tables, the editor for hierarchies is in the menu bar on top of the canvas. For views and entity-relationship models, it is on the properties panel.

2.  Click <span class="FPA-icons"></span> \(Add\)and then select:

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
        
                \[parent-child hierarchies\] Click <span class="FPA-icons"></span> \(Add\) to add a new parent-child hierarchy. Select the parent and child columns that represent the hierarchy. You can set as many as necessary. The results of these hierarchies can be compounded.

        > ### Example:  
        > You have a `CostArea` and `CostCenter` attributes with the following pairs of parent-child hierarchies:
        > 
        > 
        > <table>
        > <tr>
        > <th valign="top">
        > 
        > ParentCostArea
        > 
        > 
        > 
        > </th>
        > <th valign="top">
        > 
        > CostArea
        > 
        > 
        > 
        > </th>
        > </tr>
        > <tr>
        > <td valign="top">
        > 
        > B
        > 
        > 
        > 
        > </td>
        > <td valign="top">
        > 
        > C
        > 
        > 
        > 
        > </td>
        > </tr>
        > <tr>
        > <td valign="top">
        > 
        > A
        > 
        > 
        > 
        > </td>
        > <td valign="top">
        > 
        > B
        > 
        > 
        > 
        > </td>
        > </tr>
        > <tr>
        > <td valign="top">
        > 
        > NULL
        > 
        > 
        > 
        > </td>
        > <td valign="top">
        > 
        > A
        > 
        > 
        > 
        > </td>
        > </tr>
        > </table>
        > 
        > In the `CostArea` parent-child hierarchy:
        > 
        > -   A is parent to B.
        > -   B is child to A and parent to C.
        > -   C is child to B.
        > 
        > 
        > <table>
        > <tr>
        > <th valign="top">
        > 
        > ParentCostCenter
        > 
        > 
        > 
        > </th>
        > <th valign="top">
        > 
        > CostCenter
        > 
        > 
        > 
        > </th>
        > </tr>
        > <tr>
        > <td valign="top">
        > 
        > 2
        > 
        > 
        > 
        > </td>
        > <td valign="top">
        > 
        > 3
        > 
        > 
        > 
        > </td>
        > </tr>
        > <tr>
        > <td valign="top">
        > 
        > 1
        > 
        > 
        > 
        > </td>
        > <td valign="top">
        > 
        > 2
        > 
        > 
        > 
        > </td>
        > </tr>
        > <tr>
        > <td valign="top">
        > 
        > NULL
        > 
        > 
        > 
        > </td>
        > <td valign="top">
        > 
        > 1
        > 
        > 
        > 
        > </td>
        > </tr>
        > </table>
        > 
        > In the `CostCenter` parent-child hierarchy:
        > 
        > -   1 is parent to 2.
        > -   2 is child to 1 and parent to 3.
        > -   3 is child to 2.
        > 
        > Compounding these two hierarchies will create the following compounded parent-child hierarchy, with the hierarchical structure of the two initial dimensions taken into consideration:
        > 
        > 
        > <table>
        > <tr>
        > <td valign="top">
        > 
        >   
        >  NULL  
        >     --\> A/1  
        >        --\> B/2  
        >           --\> C/3  
        >    
        >     --\> A/2  
        >        --\> B/3  
        >    
        >     --\> B/1  
        >        --\> C/2  
        >    
        >     --\> C/1  
        >    
        >     --\>A/3   
        >  
        > 
        > 
        > 
        > </td>
        > </tr>
        > </table>


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
                Levels


        
        </td>
        <td valign="top">
        
                \[level-based hierarchies\] Click <span class="FPA-icons"></span> \(Add\) to add a level and select the column containing values for the highest level of your hierarchy. Click <span class="FPA-icons"></span> \(Add\) again to add the next level down. Keep adding levels until you reach the lowest level of your hierarchy.

        For example, in a `Products` dimension, you may add three levels containing the columns `Product Line`, `Product Category`, and `Product`.


        
        </td>
        </tr>
        </table>
        
    -   *External Hierarchy* - To open the External Hierarchy dialog:

        1.  Select the external hierarchy and click *OK* to show the mapping editor.
        2.  Drag the key column of your dimension and drop it on the child column of the hierarchy to map them.

            > ### Note:  
            > The child attribute must be a key column..

        3.  Click *Add* to add the external hierarchy and return to the Hierarchies dialog.

        > ### Note:  
        > Alternatively, you can add an external hierarchy in the *Associations* section of the dimension property sheet. Click <span class="FPA-icons"></span> \(Create Association\) and select *Hierarchy Association*. Drag and drop the key attribute of your dimension on the child column of the hierarchy to map them.


3.  Click *Close* to close the dialog and return to your dimension.


