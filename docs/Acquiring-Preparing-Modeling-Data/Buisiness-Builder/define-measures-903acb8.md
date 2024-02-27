<!-- loio903acb8d378d4984af8ad4f694d56529 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Measures

A measure is a quantifiable value that refers to an aggregatable field of the underlying model.



## Context

Measures can only be used in a consumption model if the business entity is used as a fact source.



## Procedure

1.  Go to the *Measures* tab.

2.  To define one measure, choose <span class="FPA-icons-V3"></span> *Add*.

    To define multiple measures: Choose <span class="FPA-icons-V3"></span> *Add Measures*. Select your measures and choose *Apply*. By default, these measure are of type *Aggregation*. To change details for the measure, choose <span class="FPA-icons-V3"></span> *Details*.

3.  Give your measure a meaningful and business-ready name. This can contain a maximum of 120 characters/special characters.

4.  Select a type of measure and define the properties. The properties depend on the type of measure. The following types are available: [Measure Types](measure-types-f37eaaf.md)

5.  For derived measures, you can define restrictions. In the restrictions editor, you can choose between the simple and the advanced mode. In the simple mode, you are guided by a wizard. In the advanced mode, you have more options and are able to create more complex crtiteria.

6.  For measures of type *Aggregation* set the aggregation type \(sum, average, count, max, min\).

7.  Beside the standard aggregation, you can define an exception aggregation. For more information, see [Aggregation and Exception Aggregation](aggregation-and-exception-aggregation-7696e25.md).

    The exception aggregation will be visible in stories in SAP Analyics Cloud, but not in the data preview.

8.  Decide whether your measure should have a currency or unit assigned. The unit or currency can have a constant value or can be derived from another field.

9.  Decide whether your measure should be an *Auxiliary Measure*. An auxiliary measure can be used for further calculation upon within the given business entity but is not exposed to the consumption model. For instance, general measures that are exposed via differently restricted derived measures might not be required in the consumption model itself.

10. You can choose if null values shall be treated as NULL or zero in the data preview and story consumption.

11. Save your entries.

12. To duplicate measures, choose <span class="SAP-icons-V5"></span> *Duplicate existing measure*.


