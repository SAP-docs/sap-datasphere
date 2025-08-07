<!-- loio1aff2ba3ef3d423b89ed378fe72ec1b7 -->

# Converting Currency and Unit Values

As you bring data together from various sources, you will encounter values in different currencies and units. These values will need to be converted and harmonized to allow accurate and meaningful comparisons. SAP Datasphere uses the standard SAP `TCUR*` and `T006*` tables and SAP HANA functions to perform these conversions.

This topic contains the following sections:

-   [Converting Currency Values](converting-currency-and-unit-values-1aff2ba.md#loio1aff2ba3ef3d423b89ed378fe72ec1b7__section_currency)
-   [Converting Unit Values](converting-currency-and-unit-values-1aff2ba.md#loio1aff2ba3ef3d423b89ed378fe72ec1b7__section_unit)



<a name="loio1aff2ba3ef3d423b89ed378fe72ec1b7__section_currency"/>

## Converting Currency Values

To prepare for currency conversion, use the wizard to import or create the necessary `TCUR*` objects in your space \(see [Enabling Currency Conversion with TCUR\* Tables and Views](enabling-currency-conversion-with-tcur-tables-and-views-b462239.md)\).

> ### Note:  
> If the `TCUR*` tables have been shared to your space, you must still use the *Currency Conversion Views* dialog to create local `TCUR*` views, before you can do currency conversion.

Once the `TCUR*` views are available in your space, you can use them to do currency conversion in:

-   Graphical views - see [Create a Currency Conversion Column in a Graphical View](../create-a-currency-conversion-column-in-a-graphical-view-6e3d8be.md).
-   SQL views - see [Example: Converting Currency Values with CONVERT\_CURRENCY](../sql-functions-reference-6d624a1.md#loio6d624a1956234d818d0bfdc77cbd0e09__section_example_currency).
-   Analytic models - see [Create a Conversion Measure for Currencies](create-a-conversion-measure-for-currencies-ec00efb.md).
-   Business Builder objects - see [Use Currency Conversion](../Buisiness-Builder/use-currency-conversion-1ba4554.md).

You should always identify columns containing currency values and codes with the following semantic types:

-   *Amount with Currency* - for the measure containing the values.
-   *Currency Code* - for the attribute containing the codes.

For more information, see [Specify Semantic Types for Measures and Attributes](specify-semantic-types-for-measures-and-attributes-f7272c0.md).



<a name="loio1aff2ba3ef3d423b89ed378fe72ec1b7__section_unit"/>

## Converting Unit Values

To prepare for unit conversion, you must import the `T006` and `T006D` tables to your space from your SAP system \(or have these tables shared to your space from another space\).

> ### Note:  
> If `T006` and `T006D` are shared to your space, you must wrap each table in a view before it can be used for unit conversion in SAP Analytics Cloud.

Once the `T006*` views are available in your space, you can use them to do currency conversion in:

-   Graphical views - see [Create a Unit Conversion Column in a Graphical View](../create-a-unit-conversion-column-in-a-graphical-view-23bc94f.md).
-   SQL views - use the `CONVERT_UNIT` function.
-   Analytic models - see [Create a Conversion Measure for Units](create-a-conversion-measure-for-units-965ce56.md).

You should always identify columns containing unit values and codes with the following semantic types:

-   *Quantity with Unit* - for the measure containing the values.
-   *Unit of Measure* - for the attribute containing the codes.

For more information, see [Specify Semantic Types for Measures and Attributes](specify-semantic-types-for-measures-and-attributes-f7272c0.md).

