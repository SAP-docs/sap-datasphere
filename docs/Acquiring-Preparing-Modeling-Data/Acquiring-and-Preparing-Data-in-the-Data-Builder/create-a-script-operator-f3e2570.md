<!-- loiof3e2570966ac4036b552ebd998274af1 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Script Operator

Insert a script operator to transform incoming data with a Python script and output structured data to the next operator.



## Context

The script operator receives the data from a previous operator. You can provide transformation logic as a body of the `transform` function in the Script property of the operator. Incoming data is fed into the `data` parameter of the `transform` function and the result from this function is returned to the output.

The script operator allows data manipulation and vector operations by providing support for **NumPy** and **Pandas** modules. Non-I/O objects and functions of **NumPy** and **Pandas** can be used with aliases `np` and `pd`, respectively, without any requirements to explicitly import them.

The incoming `data` parameter in the `transform` function is of type Pandas DataFrame. The input table is converted into a DataFrame and fed into transform function as data parameter. You are expected to provide scripts for the intended transformation of the incoming DataFrame and also return a valid DataFrame from transform function. It is important that the returning DataFrame from the transform function has the same column names, types and order as the specified table for the output. Otherwise, execution of the data flow results in failure.

> ### Restriction:  
> In a data flow, the script operator may receive the incoming table in multiple batches of rows, depending on the size of the table. This means that the `transform` function is called multiple times, for each batch of rows, and that its `data` parameter contains only the rows for data given batch.
> 
> Hence, the operations that require the complete table within the `data` parameter are not possible. For example, removing duplicates.



<a name="loiof3e2570966ac4036b552ebd998274af1__steps_umw_gdk_srb"/>

## Procedure

1.  Click the *Script* tool, drag it onto the diagram canvas, and release it where you want to create the script operator.

2.  Click and drag the port on the right of the source node that you want to join and drop it onto the script operator.

    A flow is created between the source and the script operator.

3.  Click the script operator to display its properties in the side panel, and complete the properties in the *General* section:


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
    
    Label


    
    </td>
    <td valign="top">
    
    Provide a suitable name for the operator.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Code Language


    
    </td>
    <td valign="top">
    
    \[read-only\] The supported language is Python.


    
    </td>
    </tr>
    </table>
    
4.  In the *Script* section, enter your Python script to transform the incoming data and produce an output schema.

    For information about Python support in the script operator, see [Script Operator Python Reference](script-operator-python-reference-73e8ba1.md).

5.  In the *Columns* section, manually specify the columns that will be output by your script.

    By default, all the input columns are displayed. You can:

    -   Hover on a column and click <span class="FPA-icons"></span> to see its data type.
    -   Reorder the columns by dragging and dropping.
    -   Add any missing columns from input operators using <span class="FPA-icons"></span> \(Add Column\) and select the columns.
    -   Create new columns using <span class="FPA-icons"></span> \(Create New Column\) and provide a name and data type for the column. The new columns are easily identified in the the *Script* node *Columns* section with the <span class="FPA-icons"></span> \(New Column\) icon.
    -   Remove multiple columns at once, [ctrl\] + [click\]  to select the columns and choose <span class="FPA-icons"></span> \(Delete Columns\) .
    -   To remove all columns, click *Select All* and choose <span class="FPA-icons"></span> \(Delete Columns\) .

6.  To complete the script operator, create a flow from it to the next operator or the target table, as appropriate.


