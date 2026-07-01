<!-- loio89cf2943253c4b02b8012ae58ec68f29 -->

# Creating an Incremental Aggregation on a Target Table in a Transformation Flow on File

Incremental aggregation on target tables in transformation flows for efficiently maintaining aggregated results during incremental data loads. Use it to apply aggregation functions \(SUM, COUNT, MIN, MAX, AVG, LAST\) to numerical columns when delta capture is enabled on the source table.

Add incremental aggregations to the target table. It is useful for handling incremental data loads and maintaining aggregated results efficiently:

1.  Click the target node to display its properties in the side panel. In the *Incremental Aggregation* section, click *Edit Aggregation*.
2.  In the *Incremental Aggregation* dialog are listed all aggregations with numerical data types. You can define the following aggregation types:


    <table>
    <tr>
    <th valign="top">

    Type
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    LAST \(default\)
    
    </td>
    <td valign="top">
    
    Retains the most recent value for the column based on the latest operations applied to the row. When a row is updated, the previous value is replaced with the new value. Columns with non-numerical data types \(such as text or dates\) can only use the LAST aggregation type.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SUM
    
    </td>
    <td valign="top">
    
    Calculates the cumulative total of all numerical values in the column. When new data is added incrementally, the new values are added to the existing sum. Useful for tracking totals such as sales amounts or quantities.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    COUNT
    
    </td>
    <td valign="top">
    
    Counts the number of non-null values in the column. Null values are excluded from the count calculations. When new rows are added, the count increments accordingly. Useful for tracking the number of valid records or transactions.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    MIN
    
    </td>
    <td valign="top">
    
    Identifies and retains the minimum \(smallest\) value in the column across all rows. When used in a transformation flow, an intermediate persistent table file is created to handle these operations within its capacity unit. See [Monitoring Capacity Unit Consumption](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/ba3d05baac854171914c09d64bed7202.html "Monitor the number of capacity units consumed each month to track usage patterns and plan resource allocation.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    MAX
    
    </td>
    <td valign="top">
    
    Identifies and retains the maximum \(largest\) value in the column across all rows. When used in a transformation flow, an intermediate persistent table file is created to handle these operations within its capacity unit. See [Monitoring Capacity Unit Consumption](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/ba3d05baac854171914c09d64bed7202.html "Monitor the number of capacity units consumed each month to track usage patterns and plan resource allocation.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    COUNT\*
    
    </td>
    <td valign="top">
    
    Counts all values in the column, including null values. Unlike COUNT, this type provides a total row count. Useful for understanding data volume or detecting missing values when combined with COUNT comparisons.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    AVG
    
    </td>
    <td valign="top">
    
    Calculates the average \(mean\) of all numerical values in the column. When used in a transformation flow, an intermediate persistent table file is created to handle these operations within its capacity unit. Note that incremental average calculations require careful management to maintain accuracy with delta updates. See [Monitoring Capacity Unit Consumption](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/ba3d05baac854171914c09d64bed7202.html "Monitor the number of capacity units consumed each month to track usage patterns and plan resource allocation.") :arrow_upper_right:.
    
    </td>
    </tr>
    </table>
    
3.  Click *Save*. You can see the updated columns in the *Incremental Aggregations* section.

> ### Note:  
> -   Incremental aggregations:
>     -   They are supported only when *Delta Capture* is enabled on the source table. They are not supported when the source is a shared local table from a SAP HANA Space having *Delta Capture* enabled.
>     -   Using a target table that employs AVG, MAX, or MIN in one transformation as the target table in another transformation using any of these functions could lead to data inconsistencies.
>     -   If incremental aggregation is enabled, the input DataFrame for the Python script will include the previous versions of the data for updates.
> 
> -   In the case the row is deleted on the source delta table, the row will be available in the target table and the aggregated values are then set to 0.

