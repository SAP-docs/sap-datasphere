<!-- loioaac37d08ef4344828e79a1fa105f9d15 -->

# Converting Local Table Data Types from a HANA Space to a File Space

Convert HANA local table data types to data types supported by Apache Spark runtime when sharing tables to file space for use in transformation flows.



## Context

When sharing HANA local tables to file space for consumption in a transformation flow, certain HANA data types are not supported in Apache Spark runtime. Except for the `TIME` data type, all other unsupported types can be cast to equivalent Aparche Spark-compatible types. Casting to correct types helps to prevent transformation failure.



## Procedure

1.  In the transformation flow *View Transform*, create a calculated column for unsupported data types.

2.  Use the appropriate `CAST` SQL function to convert to recommended types:


    <table>
    <tr>
    <th valign="top">

    HANA Data Type
    
    </th>
    <th valign="top">

    Recommended Apache Spark Type
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    DECIMALFLOAT
    
    </td>
    <td valign="top">
    
    DECIMAL
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SMALLDECIMAL
    
    </td>
    <td valign="top">
    
    DECIMAL
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ST\_GEOMETRY
    
    </td>
    <td valign="top">
    
    VARCHAR
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ST\_POINT
    
    </td>
    <td valign="top">
    
    VARCHAR
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    TIME
    
    </td>
    <td valign="top">
    
    Not supported in Apache Spark. Consider converting to TIMESTAMP in the source table before sharing.
    
    </td>
    </tr>
    </table>
    
3.  Map the calculated columns to your target.


