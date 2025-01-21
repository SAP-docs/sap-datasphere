<!-- loio328d28fa8e324f759ff87751efc3b89e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create an Aggregation in a Data Flow

Insert an aggregation operator to perform `SUM`, `AVG`, `MIN`, `MAX`, or `COUNT` calculations.



<a name="loio328d28fa8e324f759ff87751efc3b89e__steps_vkh_drt_rrb"/>

## Procedure

1.  Create a projection operator \(see [Create a Projection in a Data Flow](create-a-projection-in-a-data-flow-912f740.md)\) and remove all the columns from your dataset except those that you want to aggregate and those that you want to group the aggregations by.

2.  Click the *Aggregation* tool, drag it onto the diagram canvas, and release it where you want to create the aggregation.

3.  Click and drag the port on the right of the projection operator and drop it onto the aggregation operator.

    A flow is created between the projection and the aggregation operator.

4.  Click the aggregation operator to display its properties in the side panel, and complete the properties in the *General* section:


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
    
    Provide a suitable name for your aggregation as per your requirement.
    
    </td>
    </tr>
    </table>
    
5.  In the *Columns* section, review the output columns and set aggregations.

    Hover over a column and click:

    -   <span class="FPA-icons-V3"></span> \(Menu\)** \> *Change Aggregation* to change its aggregation. You can choose:

        -   `` \[no value\] - Default. Use as grouping column.
        -   `SUM` - \[numeric columns only\] Calculate the total value of all the rows.
        -   `AVG` - \[numeric columns only\] Calculate the average value of all the rows.
        -   `MIN` - \[numeric columns only\] Calculate the minimum value of all the rows.
        -   `MAX` - \[numeric columns only\] Calculate the maximum value of all the rows.
        -   `COUNT` - Calculate the number of distinct values.

        > ### Note:  
        > Any column that has the default, empty aggregation is used to group the aggregations by its unique values. If multiple columns are used to group, then their unique value combinations are used for grouping.

    -   <span class="FPA-icons-V3"></span> \(Menu\)** \> *Change Name* to change its name.
    -   <span class="FPA-icons-V3"></span> to view its data type.

6.  To complete the aggregation, create a flow from it to the next operator or the target table, as appropriate.


