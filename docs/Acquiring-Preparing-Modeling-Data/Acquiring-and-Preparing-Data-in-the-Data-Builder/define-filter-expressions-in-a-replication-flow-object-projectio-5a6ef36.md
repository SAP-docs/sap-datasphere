<!-- loio5a6ef36765c54a6a950a6bd6c070501d -->

# Define Filter Expressions in a Replication Flow Object Projection

By specifying filter expressions for column values, you can replicate only the records that meet the filter conditions, reducing the amount of data transferred and the overall cost of replication.



## Procedure

1.  Select the source object for which you want to define a filter.

2.  In the property panel, go to the *Projections* section and click*Add Projection*.

3.  On the *Filter* tab of the *Projections* dialog, select the column by which you want to filter from the list on the left.

    The key symbol next to a column name indicates a key field.

4.  Select the relevant filter condition from among the following:

    -   *equal to* / *not equal to*

        > ### Note:  
        > -   For connections of type SAP ABAP, SAP S/4HANA On-Premise, and Cloud Storage Providers, the boolean data type supports only these operators.
        > -   For SAP HANA connections, the binary data type supports only *these operators,* while for SAP Datasphere connections, the binary data type supports only *equal to*
        > -   For other connections, the string, boolean, and binary data types only support *equal to*.

    -   *greater than* / *less than*
    -   *include null values* / *exclude null values*

        > ### Note:  
        > For SAP ECC and SAP BW connections, these operators are not supported.

    -   *between* / *not between*
    -   *greater than or equal to* / *less than or equal to*

5.  Enter the value to compare against, then choose *Add Expression*.

6.  You can add as many filter expressions as needed.

    -   If you define more than one filter expression for the same column, they are combined with OR operators for records to be replicated.

    -   If you define filter expressions on different columns, they are combined with AND operators for records to be replicated.

        The *Filter Expression* field at the bottom left shows how all filter expressions defined on all of the columns will work together.


    For example, if you specify product ID = 123 AND country = United States AND country = DE then these expressions will combine as follows:

    `(PRODUCT_ID = 123) AND (COUNTRY = 'US' OR COUNTRY = 'DE')`

7.  Enter a name for your filter at the top of the screen, then click *OK*.


