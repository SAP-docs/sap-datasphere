<!-- loioec00efb338f3421a87dab4006d7ce6c8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Currency Conversion Measure

With a currency conversion measure, you can convert currencies.



<a name="loioec00efb338f3421a87dab4006d7ce6c8__prereq_nqr_5rf_mxb"/>

## Prerequisites

The tables and view containing currencies and exchange rates `SAP.CURRENCY.TABLE.TCUR*` are available in the current space.

You can create these tables in the *Data Builder* \(see [Enabling Currency Conversion with TCUR\* Tables and Views](../Creating-Finding-Sharing-Objects/enabling-currency-conversion-with-tcur-tables-and-views-b462239.md)\).



## Procedure

1.  You are in the editor of your analytic model. You can create a new currency conversion measure by clicking the background of the canvas and choosing <span class="FPA-icons-V3"></span> Add Measure in the properties panel. Choose *Currency Conversion Measure*.

2.  Select the source measure. The source measure has to be a fact source and has to refer to a measure in the underlying fact with semantic type *Amount with Currency*. The measure in the fact has to have an assigned currency field.

3.  Define the target currency.

    The target currency can be specified as:

    -   a constant value

    -   a reference to a dimension that is mapped to an attribute of the fact with semantic type *Currency Code*.

    -   a variable. For more information, see [Use Variables for Currency Conversion](use-variables-for-currency-conversion-0379a7c.md).

4.  Define the reference date.

    The reference date can be:

    -   the current date
    -   a constant value, with a fixed date

    -   a reference to a dimension with data type *Date*
    -   a variable. For more information, see [Use Variables for Currency Conversion](use-variables-for-currency-conversion-0379a7c.md).

5.  Select the exchange rate type to be used on the conversion.

    The target currency can be specified as:

    -   a constant value

    -   a reference to a dimension that is mapped to an attribute of the fact

    -   a variable. For more information, see [Use Variables for Currency Conversion](use-variables-for-currency-conversion-0379a7c.md).

6.  Select the client. The currency conversion tables have a client field, which you can enter here.

7.  Select the error handling method. This defines how the system reacts when a value cannot be converted. Possible values are:

    -   Set to null

    -   Fail on error

    -   Keep unconverted



