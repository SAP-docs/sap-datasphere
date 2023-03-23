<!-- loioe0a38047eb9d4849bd71308d7b5e4af5 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Union Operator

Insert a union operator to combine two data sets that share the same schema definition.



<a name="loioe0a38047eb9d4849bd71308d7b5e4af5__steps_onk_qd4_rrb"/>

## Procedure

1.  Click the *Union* tool, drag it onto the diagram canvas, and release it where you want to create the union.

2.  Click and drag the port on the right of the first source node that you want to join and drop it onto the union operator.

    A flow is created between the source and the union operator.

3.  Repeat the action for the second source node to create its flow to the union operator.

4.  Click the union operator to display its properties in the side panel, and complete the properties in the *General* section:


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

    Provide a suitable name for your union operator as per your requirement.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Union All*


    
    </td>
    <td valign="top">

    Toggle this button to include/exclude the duplicate records from the input operators. For example, if *Union All* is disabled, all the duplicate records are removed from the final result.


    
    </td>
    </tr>
    </table>
    
5.  In the *Mappings* section, review the predefined union mappings.

    -   Click on *All*, *Mapped*, or *Unmapped* to show the union columns of your choice.
    -   Drag a column from source and drop onto the required union column to create or modify the mapping.
    -   To delete mappings, select one or more existing mappings and click <span class="FPA-icons"></span>.

    You can click <span class="FPA-icons"></span> \(Settings\)to manually add or delete source columns as output columns of the union, and select the required action.


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

    *Add All Source Columns as Output Columns*


    
    </td>
    <td valign="top">

    Add all columns in the left list to the right list \(if they are not already present\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Add Selected Source Columns as Output Columns*


    
    </td>
    <td valign="top">

    Add columns selected in the left list to the right list \(if they are not already present\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Delete Selected Output Columns*


    
    </td>
    <td valign="top">

    Delete any columns selected in the right list so that they are no longer union output columns.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    *Delete All Output Columns*


    
    </td>
    <td valign="top">

    Delete all columns in the right list so that they are no longer union output columns.


    
    </td>
    </tr>
    </table>
    
6.  In the *Columns* section, specify the columns.

    -   All columns from the first input operator are displayed. Hover on a column and click <span class="FPA-icons"></span> to see its data type.

    -   You can reorder the columns by dragging and dropping.
    -   Click <span class="FPA-icons"></span> \(Menu\) to rename or remove selected column.
    -   To remove multiple columns at once, press the [Ctrl\] key, click on each columns you want to select, and click <span class="FPA-icons"></span> \(Delete Columns\).

7.  To complete the union, create a flow from it to the next operator or the target table, as appropriate.


