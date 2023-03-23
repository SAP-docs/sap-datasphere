<!-- loio912f74056c3f4647821731a84680fc3a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Projection Operator

Insert a projection operator to add, remove, reorder, or rename columns.



<a name="loio912f74056c3f4647821731a84680fc3a__steps_sj1_c44_rrb"/>

## Procedure

1.  Click the *Projection* tool, drag it onto the diagram canvas, and release it where you want to create the projection.

2.  Click and drag the port on the right of the source node that you want to join and drop it onto the projection operator.

    A flow is created between the source and the projection operator.

3.  Click the projection operator to display its properties in the side panel, and complete the properties in the *General* section:


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

    *Label*


    
    </td>
    <td valign="top">

    Provide a suitable name for your projection as per your requirement.


    
    </td>
    </tr>
    </table>
    
4.  In the *Columns* section, specify the mapping of your columns.

    -   Hover on a column and click <span class="FPA-icons"></span> to view its data type.
    -   You can reorder the columns by dragging and dropping.
    -   You can add any missing columns from input operator using <span class="FPA-icons"></span> \(Add Column\) and select the columns. You can also add calculated column. See [Create a Calculated Column in a Projection Operator](create-a-calculated-column-in-a-projection-operator-73116a5.md) for more information.
    -   Click <span class="FPA-icons"></span> \(Menu\) to rename, remove, or duplicate a selected column.
    -   You can edit the name, data type, and expression of a column by choosing <span class="FPA-icons"></span> option.
    -   To remove multiple columns at once, press the [Ctrl\] key, click on each columns you want to select, and click <span class="FPA-icons"></span> \(Delete Columns\).
    -   To remove all columns, click *Select All* and choose <span class="FPA-icons"></span> \(Delete Columns\).

5.  \(Optional\) In the *Filter* section, define filters.

    In the *Expression* field, enter the required expression. You can build your expression by choosing from the *Functions*, *Columns*, and *Operators*.

    For more information, see [Function Reference for Data Transformation Language](https://help.sap.com/viewer/fd995896a5f841c696d2b6825d39f755/Cloud/en-US).

    > ### Note:  
    > To validate your expression so that you can find any issues with it and fix them, click the *Validate* button.
    > 
    > -   In the expression, you must enclose a column name within double quotations and a constant string value within single quotations.

6.  To complete the projection, create a flow from it to the next operator or the target table, as appropriate.


