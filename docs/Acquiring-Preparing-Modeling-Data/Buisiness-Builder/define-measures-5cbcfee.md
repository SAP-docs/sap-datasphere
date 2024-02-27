<!-- loio5cbcfeed55be4bb6830511ca946edfde -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Measures

You can define measures for your consumption model.



## Context

A measure is a quantifiable value that refers to an aggregatable field of the underlying model.



<a name="loio5cbcfeed55be4bb6830511ca946edfde__steps_d2l_lnw_cmb"/>

## Procedure

1.  Go to the *Measures* tab.

2.  To define a measure, choose <span class="FPA-icons-V3"></span> *New measure*.

    To add multiple fact source measures, choose <span class="FPA-icons-V3"></span> *Add Measures*. Select your measures and choose *Apply*. To change details for a measure, choose <span class="FPA-icons-V3"></span> *Details*.

3.  Select a type of measure and define the properties. The properties depend on the type of measure. More information: [Measure Types](measure-types-f37eaaf.md)

4.  Beside the standard aggregation, you can define an exception aggregation. For more information, see [Aggregation and Exception Aggregation](aggregation-and-exception-aggregation-7696e25.md).

    The exception aggregation will be visible in stories in SAP Analyics Cloud, but not in the data preview.

5.  Give your measure a meaningful and business-ready name. This can contain a maximum of 120 characters/special characters.

6.  Decide wether your measure should be an *Auxiliary Measure*. An auxiliary measure can be used for further calculation upon within the given business entity, but is not exposed to the consumption model. For instance, general measures that are exposed via differently restricted derived measures might not be required in the consumption model itself.

7.  Save your entries.

8.  To duplicate measures, choose <span class="SAP-icons-V5"></span> *Duplicate existing measure*.


