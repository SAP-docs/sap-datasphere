<!-- loio0379a7c741134bcca303a8002b5d46c5 -->

# Use Variables for Currency Conversion

For currency conversion measures, you can define variables for the target currency, the reference date, and the exchange rate type.



## Procedure

1.  In the definition of the currency conversion measure, when defining the target currency, the reference date, and the exchange rate type, you can select *Variable* as type.

2.  You can then select an existing variable or create a new variable.

3.  To create a new variable, select *Create new Source Variable*. The new variable is added to the variable section of the currency conversion measure.

4.  Edit the properties of the new variable: choose how the variable should be filled:

    -   *Manual Input*
    -   *Derive Value*


5.  If you want to derive the value, you need to

    1.  Define a lookup entity \(a view\)
    2.  Select the column from which the value is to be derived.
    3.  Map the parameter of the lookup entity. If it has no input parameter, you can set a constant value or create a variable.


