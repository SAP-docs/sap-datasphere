<!-- loioe57633deb333431c8787f2f57b1cb08a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Join Operator

Insert a join operator to merge two data sets together using a join definition to match the records.



## Context

The join operator requires two inputs, and it generates a single output.

> ### Note:  
> The size limit for files being processed by the join operator is 10 GB.



<a name="loioe57633deb333431c8787f2f57b1cb08a__steps_obx_nvn_prb"/>

## Procedure

1.  Click the *Join* tool, drag it onto the diagram canvas, and release it where you want to create the join.

2.  Click and drag the port on the right of the first source node that you want to join and drop it onto the join operator.

    A flow is created between the source and the join operator.

3.  Repeat the action for the second source node to create its flow to the join operator.

4.  Click the join operator to display its properties in the side panel, and complete the properties in the *General* section:


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
    
    Provide a suitable name for your join as per your requirement.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Join Type*


    
    </td>
    <td valign="top">
    
    Choose the type of join. The joins that are currently supported are `INNER`, `LEFT_OUTER`, and `RIGHT_OUTER`.


    
    </td>
    </tr>
    </table>
    
5.  In the *Join Definition* section, click on <span class="FPA-icons"></span> \(Edit\) to modify the predefined join mappings.

    -   Click on <span class="FPA-icons"></span> \(Auto Map\) to automatically create a join that matches column names if possible.
    -   To manually create a new join mapping, drag and drop any left column onto any right column.
    -   To delete a join mapping, select it and click <span class="FPA-icons"></span>.
    -   To clear all mappings, click <span class="SAP-icons"></span> \(Remove all Mappings\).

6.  In the *Columns* section, specify the mapping of your columns:

    -   All unique columns from the input operators are displayed. Hover on a column and click <span class="FPA-icons"></span> to view its data type.
    -   You can reorder the columns by dragging and dropping.
    -   You can add any missing columns from input operators using <span class="FPA-icons"></span> \(Add Column\) and select the columns.
    -   Click <span class="FPA-icons"></span> \(Menu\) to rename, remove, or duplicate selected column.
    -   To remove multiple columns at once, press the [Ctrl\] key, click on each columns you want to select, and click <span class="FPA-icons"></span> \(Delete Columns\).
    -   To remove all columns, click *Select All* and choose <span class="FPA-icons"></span> \(Delete Columns\).

7.  In the *Advanced Properties* section, click on <span class="FPA-icons"></span> \(Edit\) to define the join optimization. By default, it is set to *Automatic*. Manual optimization should be done only when absolutely necessary.

    -   Select *Join Optimization* as *Manual*.
    -   For left and right joins, respectively;
        -   Choose *Cache* as *Yes* or *No*.
        -   Specify the *Rank* value within the range 0–100.


8.  To complete the definition of the join, create a flow from it to the next operator or the target table, as appropriate.


