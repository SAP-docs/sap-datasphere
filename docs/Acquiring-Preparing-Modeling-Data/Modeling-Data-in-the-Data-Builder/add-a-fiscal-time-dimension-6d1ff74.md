<!-- loio6d1ff7426b6342d7892697407bded26f -->

# Add a Fiscal Time Dimension

You can add a fiscal time dimension to an analytic model so that you can use fiscal period in your finance domain.



## Context

When you add a fiscal time dimension to an analytic model, a standard variable of sub type *Fiscal Variant* is created for this dimension. The variable can then be handled like any other variable. Its data type is derived from the fiscal variance column from the fiscal time dimension. To learn more about fiscal time dimensions in the Data Builder, see [Create a Fiscal Time Dimension](create-a-fiscal-time-dimension-24248ab.md).

> ### Example:  
> A fiscal time dimension organizes and categorizes time periods according to a company's fiscal calendar \(also known as a financial year\) rather than the standard calendar. For example, your fiscal time dimension could be the fiscal year, and you set the variable to the previous fiscal year to see the results for the previous fiscal year.



## Procedure

1.  When you select your source, and your source has a fiscal time dimension associated, you can copy this dimension to your new analytic model. A standard variable of sub type *Fiscal Variant* is created for this dimension. The variable can then be handled like any other variable. Its data type is derived from the fiscal variance column from the fiscal time dimension.

    > ### Note:  
    > An analytic model can contain only one fiscal variant variable.

2.  In the properties panel, go to the details of the variable and enter a default value. The variable needs a default value, because it is always hidden in the data preview.

3.  In the data preview, the data will be filtered by the fiscal variant when you drill down by the fiscal dimension.


