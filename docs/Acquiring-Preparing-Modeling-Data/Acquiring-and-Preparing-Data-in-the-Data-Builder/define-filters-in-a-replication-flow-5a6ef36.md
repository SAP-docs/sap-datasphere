<!-- loio5a6ef36765c54a6a950a6bd6c070501d -->

# Define Filters in a Replication Flow

Define filters to delimit the scope of your replication flow.



## Procedure

1.  Select the source object for which you want to define a filter.

2.  Choose*Add Projection*.

3.  On the *Filter* tab of the *Projections* dialog, select the column by which you want to filter from the list on the left.

    The key symbol next to a column name indicates a key field.

4.  Select the relevant filter condition and enter the desired values.

    Supported filters:

    -   *Less Than*
    -   *Greater Than*
    -   *Equal To*
    -   *Great Than* and *Equal To*
    -   *Less Than* and *Equal To*
    -   *Between*
    -   *Include Null Values*

    The options you can select depend on the replication objects you choose and their respective data types and connections:

    -   Boolean data type can only support *Equal To* for SAP ABAP ODP and SAP S/4HANA Connections.
    -   Binary data type can only support *Equal To* for SAP HANA \(internal and external\) connections.

5.  When you're done, choose *Add Expression*.

6.  Repeat steps 3 to 5 until you have defined all filters you need.

    -   More than one filter on different columns applies the AND operator.

    -   More than one filter on the same column applies the OR operator.

    -   The line at the bottom of the screen summarizes how all the filter expressions you defined work together.


    For example, filtering on the product ID 123 for the countries United States and Germany results in the following:

    \(PRODUCT\_ID = 123\) AND \(COUNTRY = 'US' OR COUNTRY = 'DE'\)

7.  Enter a name for your filter at the top of the screen, then click *OK*.


