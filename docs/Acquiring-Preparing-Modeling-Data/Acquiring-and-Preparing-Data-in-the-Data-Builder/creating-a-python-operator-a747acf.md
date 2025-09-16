<!-- loioa747acf9d96b450da4b802b80e05a896 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Python Operator

Insert a Python operator to transform incoming data with a Python script and output structured data to the next operator.

In a transformation flow in a file space, the *Python* operator receives the data from a previous operator. You can provide transformation logic as a body of the `transform` function in the *Script* property of the operator. Incoming data is fed into the `data` parameter of the `transform` function and the result from this function is returned to the output.

The *Python* operator allows data manipulation and vector operations by providing support for `builtins` \(version 3.11\), `NumPy` \(version 1.26.4\), and `Pandas` \(version 2.2.2\) modules. Non-I/O objects and functions of `NumPy` and `Pandas` can be used with aliases `np` and `pd`, respectively, without any requirements to explicitly import them.

The incoming `data` parameter in the `transform` function is of type Pandas DataFrame. The input table is converted into a DataFrame and fed into transform function as data parameter. You are expected to provide scripts for the intended transformation of the incoming DataFrame and also return a valid DataFrame from transform function. It is important that the returning DataFrame from the transform function has the same column names, types and order as the specified table for the output. Otherwise, execution of the data flow results in failure.

> ### Caution:  
> When using *Python* operators with delta loads, duplicate records with different change types may appear in delta batches, especially during row-level actions. This issue may be due to a rollback action performed on the source delta table in *Spark* runtime or because the incremental aggregation is enabled.

1.  Drag and drop an object onto the source operator or select the *View Transform* to display its context menu, and click <span class="SAP-icons-TNT-V3"></span> Python operator to create the *Python* operator.
2.  Click the *Python* operator to display its properties in the side panel.
3.  In the *General* section, under *Input Mode*, select your operator processing settings:
    -   *System-Managed*: \[default\] The operator uses `mapInPandas` for parallel batch-wise processing. To ensure efficient and accurate data transformation, avoid performing global aggregation, grouping, or similar operations inside the Python code, as these require full dataset context. Instead, either use the *View Transform* operator for aggregation and grouping, or split the transformation flow to isolate operations requiring global context.
    -   *User-Defined Batches*: The operator uses `applyInPandas`. Defining batches based on specific column values enables more control over data processing. You can organize and analyze data more efficiently by grouping related records together. Batches should contain similar numbers of records to help avoid out of memory issues. To define batches, click <span class="SAP-icons-V5"></span> Batch Columns and select one to three batch columns.

4.  In the *Script* section, enter your Python script to transform the incoming data and produce an output schema.

    For information about Python support in the *Python* operator, see [Python Operator Reference](python-operator-reference-950d558.md).

    > ### Caution:  
    > Changes cannot be propagated between the *Python* script and output column. Manually update both to match to prevent errors. For example, if you add a new column in the *Script* field, you have to manually enter the same column in the *Columns* section to prevent errors.

5.  In the *Columns* section, manually specify the columns that will be output by your Python operator.

    > ### Note:  
    > By default, all the source columns are displayed. You can:
    > 
    > -   Hover on a column and click <span class="FPA-icons-V3"></span> to see its data type.
    > -   Reorder the columns by dragging and dropping.
    > -   Add any missing columns from a source or a target operator using <span class="FPA-icons-V3"></span> \(Add Column\) and select the columns.
    > -   Create new columns using <span class="FPA-icons-V3"></span> \(Create New Column\) and provide a name and data type for the column. The new columns are easily identified in the the *Python* operator *Columns* section with the <span class="FPA-icons-V3"></span> \(New Column\) icon.
    > -   Remove multiple columns at once, [ctrl\] + [click\]  to select the columns and choose <span class="FPA-icons-V3"></span> \(Delete Columns\) .
    > -   To remove all columns, click *Select All* and choose <span class="FPA-icons-V3"></span> \(Delete Columns\) .


