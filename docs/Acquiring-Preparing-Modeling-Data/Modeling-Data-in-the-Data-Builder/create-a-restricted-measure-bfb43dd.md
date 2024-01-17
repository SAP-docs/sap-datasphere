<!-- loiobfb43ddc98bc4162bc4196faf3e5d8c6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Restricted Measure

With a restricted measure, you can restrict available dimensions.



## Procedure

1.  You are in the editor of your analytic model. You can createa new currency conversion measure by clicking the background of the canvas and choosing <span class="FPA-icons"></span> Add Measure in the properties panel. Choose *Restricted Measure*.

2.  Select the source measure.

3.  Enter your expression in the formula editor. An atomic expression usually has the format`<dimension> <operator> <value> (e.g. Country = 'Germany').`

4.  You can define an exception aggreagtion. The exception aggregation determines how a measure is aggregated with regard to one or more dimensions. A dimension is needed for exception aggregation in order to define the granularity with which the aggregation rule is applied.

    Exception aggregation is supported for restricted measures on fact sources. You can use the exception aggregation to calculate the stock for a given time. You can also define no restrictions for the restricted measure, and just use it for the exception aggregation.

    For more information, see [Aggregation and Exception Aggregation](aggregation-and-exception-aggregation-88ca394.md).

5.  You can enable constant selection for the restricted measure. You can choose to set it for all dimensions or just for selected dimensions. A measure with constant selection will not be impacted by filters or drill-downs on the constant dimensions.

    Enabling constant selection is useful for comparing a single value with several different values. For example, you could create a restricted measure for sales in 2022, and then compare sales in 2022 with sales for all other years in the same table.

    See also the blog post [Restricted Measures with Constant Selection in SAP Analytics Cloud](https://blogs.sap.com/2021/02/02/feature-highlight-restricted-measures-with-constant-selection-in-sap-analytics-cloud/) \(published February 2, 2021\) for examples.


