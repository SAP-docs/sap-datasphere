<!-- loio6d624a1956234d818d0bfdc77cbd0e09 -->

# SQL Functions Reference

SAP Datasphere supports a subset of the SQL functions supported by SAP HANA Cloud.



This topic contains the following sections:

-   [Array Functions](sql-functions-reference-6d624a1.md#loio6d624a1956234d818d0bfdc77cbd0e09__section_array_functions)
-   [Data Type Conversion Functions](sql-functions-reference-6d624a1.md#loio6d624a1956234d818d0bfdc77cbd0e09__section_datatype_functions)
-   [Datetime Functions](sql-functions-reference-6d624a1.md#loio6d624a1956234d818d0bfdc77cbd0e09__section_datetime_functions)
-   [Fulltext Functions](sql-functions-reference-6d624a1.md#loio6d624a1956234d818d0bfdc77cbd0e09__section_fulltext_functions)
-   [Miscellaneous Functions](sql-functions-reference-6d624a1.md#loio6d624a1956234d818d0bfdc77cbd0e09__section_misc_functions)
-   [Numeric Functions](sql-functions-reference-6d624a1.md#loio6d624a1956234d818d0bfdc77cbd0e09__section_numeric_functions)
-   [Security Functions](sql-functions-reference-6d624a1.md#loio6d624a1956234d818d0bfdc77cbd0e09__section_security_functions)
-   [String Functions](sql-functions-reference-6d624a1.md#loio6d624a1956234d818d0bfdc77cbd0e09__section_string_functions)
-   [Example: Converting Currency Values with CONVERT\_CURRENCY](sql-functions-reference-6d624a1.md#loio6d624a1956234d818d0bfdc77cbd0e09__section_example_currency)

> ### Note:  
> SAP Datasphere does not support SAP HANA Cloud "window functions" \(see [Window Functions and the Window Specification](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/20a353327519101495dfd0a87060a0d3.html)\).



<a name="loio6d624a1956234d818d0bfdc77cbd0e09__section_array_functions"/>

## Array Functions

SAP Datasphere supports the following array functions:

-   `SUBARRAY`
-   `TRIM_ARRAY`

For detailed documentation of these functions, see [Array Functions](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/e32b3b4076244f63825091adeaba6299.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.



<a name="loio6d624a1956234d818d0bfdc77cbd0e09__section_datatype_functions"/>

## Data Type Conversion Functions

SAP Datasphere supports the following data type conversion functions:

-   `CAST`
-   `TO_BIGINT`
-   `TO_BINARY`
-   `TO_BLOB`
-   `TO_BOOLEAN`
-   `TO_CLOB`
-   `TO_DATE`
-   `TO_DATS`
-   `TO_DECIMAL (DECFLOAT)`
-   `TO_DOUBLE (DOUBLE)`
-   `TO_FIXEDCHAR`
-   `TO_INT (INT)`
-   `TO_INTEGER (INT)`
-   `TO_NCLOB`
-   `TO_NVARCHAR`
-   `TO_REAL (FLOAT)`
-   `TO_SECONDDATE`
-   `TO_SMALLDECIMAL`
-   `TO_SMALLINT`
-   `TO_TIME`
-   `TO_TIMESTAMP`
-   `TO_TINYINT`
-   `TO_VARBINARY`
-   `TO_VARCHAR`

For detailed documentation of these functions, see [Data Type Conversion Functions](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/209ddefe75191014ac249bf78ba2a1e9.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.



<a name="loio6d624a1956234d818d0bfdc77cbd0e09__section_datetime_functions"/>

## Datetime Functions

SAP Datasphere supports the following datetime functions:

-   `ADD_DAYS`
-   `ADD_MONTHS`
-   `ADD_MONTHS_LAST`
-   `ADD_NANO100`
-   `ADD_SECONDS`
-   `ADD_WORKDAYS`
-   `ADD_YEARS`
-   `CURRENT_DATE`
-   `CURRENT_DATE()`
-   `CURRENT_TIME`
-   `CURRENT_TIME()`
-   `CURRENT_TIMESTAMP`
-   `CURRENT_TIMESTAMP()`
-   `DAYNAME`
-   `DAYOFMONTH`
-   `DAYOFYEAR`
-   `DAYS_BETWEEN`
-   `HOUR`
-   `ISOWEEK`
-   `LAST_DAY`
-   `LOCALTOUTC`
-   `MINUTE`
-   `MONTH`
-   `MONTHNAME`
-   `MONTHS_BETWEEN`
-   `NEXT_DAY`
-   `NOW`
-   `QUARTER`
-   `SECOND`
-   `SECONDS_BETWEEN`
-   `UTCTOLOCAL`
-   `WEEK`
-   `WEEKDAY`
-   `WORKDAYS_BETWEEN`
-   `YEAR`
-   `YEARS_BETWEEN`

For detailed documentation of these functions, see [Datetime Functions](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/209f228975191014baed94f1b69693ae.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.



<a name="loio6d624a1956234d818d0bfdc77cbd0e09__section_fulltext_functions"/>

## Fulltext Functions

SAP Datasphere supports the following fulltext function:

-   `SCORE`

For detailed documentation of this function, see [SCORE Function](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/20e6f8e97519101489a0cd3c29991e72.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.



<a name="loio6d624a1956234d818d0bfdc77cbd0e09__section_misc_functions"/>

## Miscellaneous Functions

SAP Datasphere supports the following miscellaneous functions:

-   `COALESCE`
-   `CONVERT_CURRENCY` - See [Example: Converting Currency Values with CONVERT\_CURRENCY](sql-functions-reference-6d624a1.md#loio6d624a1956234d818d0bfdc77cbd0e09__section_example_currency)
-   `CONVERT_UNIT`
-   `GREATEST (MAX)`
-   `HASH_SHA256`
-   `IFNULL`
-   `LEAST (MIN)`
-   `SESSION_CONTEXT`
-   `SESSION_USER`
-   `SYSUUID`
-   `WIDTH_BUCKET`
-   `XMLEXTRACT`
-   `XMLEXTRACTVALUE`

For detailed documentation of these functions, see [Miscellaneous Functions](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/20a465cd75191014abacf163b404e930.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.



<a name="loio6d624a1956234d818d0bfdc77cbd0e09__section_numeric_functions"/>

## Numeric Functions

SAP Datasphere supports the following numeric functions:

-   `ABS`
-   `ACOS`
-   `ASIN`
-   `ATAN`
-   `ATAN2`
-   `BITAND`
-   `BITCOUNT`
-   `BITNOT`
-   `BITOR`
-   `BITXOR`
-   `CEIL`
-   `COS`
-   `COSH`
-   `COT`
-   `EXP`
-   `FLOOR`
-   `LN (LOG)`
-   `LOG (LOG10)`
-   `MOD (%)`
-   `NDIV0`
-   `POWER (**)`
-   `RAND`
-   `ROUND`
-   `SIGN`
-   `SIN`
-   `SINH`
-   `SQRT`
-   `TAN`
-   `TANH`
-   `UMINUS`

For detailed documentation of these functions, see [Numeric Functions](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/20a190b975191014b769eafa93453d3a.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.



<a name="loio6d624a1956234d818d0bfdc77cbd0e09__section_security_functions"/>

## Security Functions

SAP Datasphere supports the following security functions:

-   `ESCAPE_DOUBLE_QUOTES`
-   `ESCAPE_SINGLE_QUOTES`
-   `IS_SQL_INJECTION_SAFE`

For detailed documentation of these functions, see [Security Functions](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/287e6e06fd69494488d71863c3e49285.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.



<a name="loio6d624a1956234d818d0bfdc77cbd0e09__section_string_functions"/>

## String Functions

SAP Datasphere supports the following string functions:

-   `ABAP_ALPHANUM`
-   `ABAP_LOWER`
-   `ABAP_NUMC`
-   `ABAP_UPPER`
-   `ASCII`
-   `BINTOHEX`
-   `BINTOSTR`
-   `CHAR`
-   `CONCAT`
-   `HEXTOBIN`
-   `LCASE`
-   `LEFT`
-   `LENGTH`
-   `LOCATE`
-   `LOWER`
-   `LPAD`
-   `LTRIM`
-   `NCHAR`
-   `REPLACE`
-   `REPLACE_REGEXPR`
-   `RIGHT`
-   `RPAD`
-   `RTRIM`
-   `SOUNDEX`
-   `STRTOBIN`
-   `SUBSTR_AFTER`
-   `SUBSTR_BEFORE`
-   `SUBSTRING`
-   `UCASE`
-   `UNICODE`
-   `UPPER`
-   `XMLTABLE`

For detailed documentation, see [String Functions](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/20a24d4b75191014afc5ac3b997d3ce2.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.



<a name="loio6d624a1956234d818d0bfdc77cbd0e09__section_example_currency"/>

## Example: Converting Currency Values with `CONVERT_CURRENCY`

When using the `CONVERT_CURRENCY` function you must, as a minimum, complete the following parameters:

-   `AMOUNT` - Specify the column containing the currency value to be converted
-   `CLIENT` - Specify the three character string identifying the tenant in your SAP system
-   `SOURCE_UNIT` - Specify the column containing the source currency or enter the source currency code
-   `TARGET_UNIT` - Specify the column containing the target currency or enter the target currency code
-   `REFERENCE_DATE` - Specify the date to use when obtaining the conversion rate
-   `SCHEMA` - Specify the space name.

In our example, which is in a space named `SALES`, we are converting the value in the `Sale_Amount` column from Euros to US Dollars using the conversion rate from 30 September 2021:

```
CONVERT_CURRENCY(
    "AMOUNT" => "Sale_Amount",
"SOURCE_UNIT" => 'EUR',
"TARGET_UNIT" => 'USD',
"SCHEMA" => 'SALES',
"REFERENCE_DATE" => '2021-09-30',
"CLIENT" => '000'
)
```

For full documentation of this function, see [CONVERT\_CURRENCY](https://help.sap.com/viewer/7c78579ce9b14a669c1f3295b0d8ca16/Cloud/en-US/d22d746ed2951014bb7fb0114ffdaf96.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.

