<!-- loio40ec77ec24f244279a81448969a7e769 -->

# Exposing Data For Consumption

Data can only be accessed outside of your SAP Datasphere space if it is exposed for consumption.

Data can be exposed as analytic models, perspectives, and views, which are accessible to clients, tools, and apps as follows:


<table>
<tr>
<th valign="top">

Object

</th>
<th valign="top">

SAP Analytics Cloud

</th>
<th valign="top">

Microsoft Excel

</th>
<th valign="top">

Other Clients, Tools, and Apps

</th>
</tr>
<tr>
<td valign="top">

Analytic models \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\)

Exposed: Automatically

</td>
<td valign="top">

Live Connection

</td>
<td valign="top">

Live Connection \(via an SAP Add-In\)

</td>
<td valign="top">

OData

</td>
</tr>
<tr>
<td valign="top">

Perspectives \(see [Define Perspectives](../Buisiness-Builder/define-perspectives-ce26fd3.md)\)

Exposed: Automatically

</td>
<td valign="top">

Live Connection

</td>
<td valign="top">

Live Connection \(via an SAP Add-In\)

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

Views\* \(see [Exposing Data For Consumption](exposing-data-for-consumption-40ec77e.md)\)

Exposed: When the *Expose for Consumption* switch is enabled

</td>
<td valign="top">

OData\*\*

</td>
<td valign="top">

\-

</td>
<td valign="top">

OData

ODBC/JDBC

</td>
</tr>
<tr>
<td valign="top">

For more information, see:

</td>
<td valign="top">

-   [Consume Data in SAP Analytics Cloud via a Live Connection](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/a2c5486c03174620be9de3c8c769ce54.html "You can create a live connection from SAP Analytics Cloud to SAP Datasphere and consume data exposed as analytic models and perspectives to create stories and analytic applications.") :arrow_upper_right:
-   [Integrate with SAP Analytics Cloud for Planning](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/f589cdea41674badaecfa1bf02571b6f.html "SAP Datasphere integrates with SAP Analytics Cloud to act as a data source for loading actuals or external data into a planning model, and can also persist your planning data and combine it with live actuals or other data as appropriate.") :arrow_upper_right:



</td>
<td valign="top">

-   [Consume Data in Microsoft Excel via an SAP Add-In](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/ef6e226fc32e48a5b3655fdb1102c0d5.html "You can create a live connection from SAP Analytics Cloud to SAP Datasphere and consume data exposed as analytic models and perspectives in Microsoft Excel, via the SAP Analytics Cloud, add-in for Microsoft Excel.") :arrow_upper_right:



</td>
<td valign="top">

-   [Consume Data in Power BI and Other Clients, Tools, and Apps via an OData Service](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/add771abf6f54c9d8de4c7e470a0e6f0.html "You can consume data exposed as views in Microsoft Power BI and other third-party clients, tools, and apps via the OData API. You can connect Power BI to SAP Datasphere via an OData service by way of a custom connector or a blank query and consume views that are exposed for consumption.") :arrow_upper_right:
-   [Consume Data in Power BI and Other Clients, Tools, and Apps via ODBC/JDBC](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/4db6f5a329af44509ae422ad707877b2.html "You can consume data exposed as views in Microsoft Power BI and other third-party clients, tools, and apps via an Open SQL schema and ODBC/JDBC.") :arrow_upper_right:



</td>
</tr>
</table>

\* The workflow of consuming views with a semantic usage of *Analytical Dataset* in SAP Analytics Cloud and Microsoft Excel via live connection is now deprecated. We recommend that you migrate your analytical datasets to the new *Fact* semantic usage and expose your view data via analytic models \(see [Analytical Datasets \(Deprecated\)](analytical-datasets-deprecated-70dab71.md)\).

\*\* SAP Analytics Cloud primarily uses the consumption of view data via OData for planning \(see [Integrate with SAP Analytics Cloud for Planning](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/f589cdea41674badaecfa1bf02571b6f.html "SAP Datasphere integrates with SAP Analytics Cloud to act as a data source for loading actuals or external data into a planning model, and can also persist your planning data and combine it with live actuals or other data as appropriate.") :arrow_upper_right:\).

> ### Note:  
> Before exposing data for consumption, you should consider applying row-level security via data access controls \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:\).

