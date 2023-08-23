<!-- loio40ec77ec24f244279a81448969a7e769 -->

# Exposing a View For Consumption

When your view is ready, you can make its data available for consumption in SAP Analytics Cloud and other clients, tools, and apps.

There are two methods for exposing view data for consumption outside SAP Datasphere:

-   SAP Analytics Cloud \(and Microsoft Excel via an SAP add-in\) do not consume view data directly. Set the *Semantic Usage* of your view to *Fact* and then add it to an analytic model to expose it \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\). There is no need to enable the *Expose for Consumption* switch.
-   Other third-party BI clients, tools, and apps can consume data from views with any *Semantic Usage* via OData or ODBC if the *Expose for Consumption* switch is enabled.

For more information, see .

