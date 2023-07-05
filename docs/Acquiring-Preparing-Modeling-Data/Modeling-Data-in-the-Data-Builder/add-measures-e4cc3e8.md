<!-- loioe4cc3e8d37d9457bab52e42da00ded9f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add Measures

Add measures to your analytic model.



## Context

Measures contain numerical values that you want to analyze. You can choose between fact source measures, calculated measures, and restricted measures.

There are different types of measures to choose from:

-   calculated measure: A calculated measure references other measures and allows the combination of measures with elementary arithmetic \(operations of addition, subtraction, multiplication, and division\), and also more complex functions like maximum/minimum, IF \(as function\), mathematical functions like round, and conversion functions like convert to decfloat.
-   restricted measure: A restricted measure refers to another measure and allows restrictions on available dimensions.
-   count distinct measure: A count distinct measure counts unique occurrences of attributes \(e.g. in case multiple rows contain the country "Germany", it is counted only once\).
-   Currency conversion measure: With a currency conversion measure, you can convert currencies.



## Procedure

1.  To add fact source measures, click on your fact source on the canvas to select measures in the properties panel on the right.

2.  You can create new measures by clicking the background of the canvas and choosing <span class="FPA-icons"></span> Add Measure in the properties panel. Choose the type of measure.

3.  For calculated measures, enter your expression in the formula editor.

    the expression field contains the formula to calculate the measure.

    > ### Example:  
    > To calculate the price, the expression could be `Amount / Quantity`.

4.  For restricted measures, proceed as follows:

    1.  Select the source measure.
    2.  Select the aggregation type.
    3.  Enter your expression in the formula editor. An atomic expression usually has the format`<dimension> <operator> <value> (e.g. Country = 'Germany').`

5.  For currency conversion measures, porceed as described here: [Create a Currency Conversion Measure](create-a-currency-conversion-measure-ec00efb.md).

6.  For count distinct measures, select the dimensions for which this measure shall be applied.

7.  For calculated measures, restricted measures, and fact source measures, you can define an exception aggregation.

8.  Decide whether your measure should be an *Auxiliary Measure*. An auxiliary measure can be used for further calculation but it will be hidden in the story in SAP Analytics Cloud.


