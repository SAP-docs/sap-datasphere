<!-- loio40ec77ec24f244279a81448969a7e769 -->

# Exposing a View For Consumption

When your view is ready, you can make its data available for consumption in SAP Analytics Cloud and other clients, tools, and apps.

There are two methods for exposing view data for consumption outside SAP Datasphere:

-   SAP Analytics Cloud \(and Microsoft Excel via an SAP add-in\) prefer to consume view data via an analytic model \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\). Set the *Semantic Usage* of your view to *Analytical Dataset* and then add it to an analytic model to expose it. There is no need to enable the *Expose for Consumption* switch. Alternatively, you can consume data from a view with a *Semantic Usage* of *Analytical Dataset* directly if the *Expose for Consumption* switch is enabled.
-   Other third-party BI clients, tools, and apps can consume data from views with any *Semantic Usage* via OData or ODBC if the *Expose for Consumption* switch is enabled.

For more information, see [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users of SAP Datasphere with any of the standard roles can consume data exposed by spaces of which they are a member. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the DW Consumer role.") :arrow_upper_right:.

