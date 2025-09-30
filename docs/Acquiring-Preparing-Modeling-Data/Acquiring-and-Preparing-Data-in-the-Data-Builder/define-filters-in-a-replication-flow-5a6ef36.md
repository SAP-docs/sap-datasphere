<!-- loio5a6ef36765c54a6a950a6bd6c070501d -->

# Define Filters in a Replication Flow

Define filters to delimit the scope of your replication flow.



## Procedure

1.  Select the source object for which you want to define a filter.

2.  In the property panel, go to the *Projections* section and click*Add Projection*.

3.  On the *Filter* tab of the *Projections* dialog, select the column by which you want to filter from the list on the left.

    The key symbol next to a column name indicates a key field.

4.  Select the relevant filter condition and enter the desired values.

    Supported filters:

    -   *equal to*
    -   *less than*
    -   *less than* or *equal to*
    -   *greater than*
    -   *great than* or *equal to*
    -   *between*
    -   *not equal to*
    -   *not between*
    -   *exclude null values*
    -   *include null values*

    The options you can select depend on the replication objects you choose and their respective data types and connections. Here are the filters you can't select by connection and data types:


    <table>
    <tr>
    <th valign="top">

    Connections
    
    </th>
    <th valign="top">

    Filters and Data Types
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    SAP ABAP
    
    </td>
    <td valign="top">
    
    The boolean data type supports only *equal to* and *not equal to*. The other data types support all comparison operators.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP S4HANA On-Premise
    
    </td>
    <td valign="top">
    
    The boolean data type supports only *equal to* and *not equal to*. The other data types support all comparison operators.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Cloud Connections
    
    </td>
    <td valign="top">
    
    The boolean data type supports only *equal to* and *not equal to*. The other data types support all comparison operators.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP HANA \(external connection, accessible from the source system\)
    
    </td>
    <td valign="top">
    
    The binary data type supports only *equal to* and *not equal to*. The other data types support all comparison operators.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP HANA \(internal connection from SAP Datasphere app\)
    
    </td>
    <td valign="top">
    
    The binary data type supports only *equal to*. The other data types support all comparison operators.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Other Connections
    
    </td>
    <td valign="top">
    
    The string, boolean, and binary data types support only *equal to*. The other data types support all comparison operators.
    
    </td>
    </tr>
    </table>
    
5.  When you're done, choose *Add Expression*.

6.  Repeat steps 3 to 5 until you have defined all filters you need.

    -   More than one filter on different columns applies the AND operator.

    -   More than one filter on the same column applies the OR operator.

    -   The line at the bottom of the screen summarizes how all the filter expressions you defined work together.


    For example, filtering on the product ID 123 for the countries United States and Germany results in the following:

    \(PRODUCT\_ID = 123\) AND \(COUNTRY = 'US' OR COUNTRY = 'DE'\)

7.  Enter a name for your filter at the top of the screen, then click *OK*.


