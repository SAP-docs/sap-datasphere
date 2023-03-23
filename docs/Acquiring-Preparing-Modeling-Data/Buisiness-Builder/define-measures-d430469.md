<!-- loiod430469a36ba4d5fa2fc90ee8cf7b944 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Measures

You can define measures for your fact model.



## Context

A measure is a quantifiable value that refers to an aggregatable field of the model. Business metrics such as profits and sales are common measures.



<a name="loiod430469a36ba4d5fa2fc90ee8cf7b944__steps_xvf_n5j_j4b"/>

## Procedure

1.  Go to the *Measures* tab.

2.  To define one measure, choose <span class="FPA-icons"></span> *New Measure*.

    To define multiple measures: Choose <span class="FPA-icons"></span> *Add Fact Source Measures*. Select your measures and choose *Apply*. To change details for the measure, choose <span class="FPA-icons"></span> *Details*.

3.  Give your measure a meaningful and business-ready name. This can contain a maximum of 120 characters/special characters.

4.  Select a type of measure and define the properties. The properties depend on the type of measure. The following types are available: [Measure Types](measure-types-f37eaaf.md)

5.  Beside the standard aggregation, you can define an exception aggregation. For more information, see [Aggregation and Exception Aggregation](aggregation-and-exception-aggregation-7696e25.md).

    The exception aggregation will be visible in stories in SAP Analyics Cloud, but not in the data preview.

6.  For derived measures, you can define restrictions. In the restrictions editor, you can choose between the simple and the advanced mode. In the simple mode, you are guided by a wizard. In the advanced mode, you have more options and are able to create more complex crtiteria.

7.  Decide whether your measure should have a currency or unit assigned. The unit or currency can have a constant value or can be derived from another field.

8.  Decide whether your measure should be an *Auxiliary Measure*. An auxiliary measure can be used for further calculation upon within the given business entity but is not exposed to the consumption model. For instance, general measures that are exposed via differently restricted derived measures might not be required in the consumption model itself.

9.  Save your entries.

10. To duplicate measures, choose <span class="SAP-icons"></span> *Duplicate existing measure*.


