<!-- loiod7d56284bb5148c887ac4054689bfbca -->

# Consuming Data Exposed by SAP Datasphere

All users of SAP Datasphere with any of the standard roles can consume data exposed by spaces of which they are a member. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the *DW Consumer* role.

This topic contains the following sections:

-   [Exposing Data from SAP Datasphere](consuming-data-exposed-by-sap-datasphere-d7d5628.md#loiod7d56284bb5148c887ac4054689bfbca__section_consume_exposed_data)
-   [Consume Data in SAP Analytics Cloud](consuming-data-exposed-by-sap-datasphere-d7d5628.md#loiod7d56284bb5148c887ac4054689bfbca__section_sac)
-   [Consume Data in Microsoft Excel](consuming-data-exposed-by-sap-datasphere-d7d5628.md#loiod7d56284bb5148c887ac4054689bfbca__section_excel)
-   [Consume Data in Other Clients, Tools, and Apps](consuming-data-exposed-by-sap-datasphere-d7d5628.md#loiod7d56284bb5148c887ac4054689bfbca__section_bi_clients)
-   [Consume Data via an OData Service](consuming-data-exposed-by-sap-datasphere-d7d5628.md#loiod7d56284bb5148c887ac4054689bfbca__section_odata)



<a name="loiod7d56284bb5148c887ac4054689bfbca__section_consume_exposed_data"/>

## Exposing Data from SAP Datasphere

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

Analytic models

Exposed: Automatically

See [Creating an Analytic Model](../Modeling-Data-in-the-Data-Builder/creating-an-analytic-model-e5fbe9e.md).



</td>
<td valign="top">

Live Connection



</td>
<td valign="top">

Live Connection



</td>
<td valign="top">

\-



</td>
</tr>
<tr>
<td valign="top">

Perspectives

Exposed: Automatically

See [Define Perspectives](../Buisiness-Builder/define-perspectives-ce26fd3.md).



</td>
<td valign="top">

Live Connection



</td>
<td valign="top">

Live Connection



</td>
<td valign="top">

Open SQL



</td>
</tr>
<tr>
<td valign="top">

Views

Exposed: When the *Expose for Consumption* switch is enabled

See [Exposing a View For Consumption](../Modeling-Data-in-the-Data-Builder/exposing-a-view-for-consumption-40ec77e.md).



</td>
<td valign="top">

Live Connection\* / ODATA



</td>
<td valign="top">

Live Connection\*



</td>
<td valign="top">

Open SQL / ODATA



</td>
</tr>
</table>

\* Only views with a semantic usage of *Analytical Dataset* can be consumed by SAP Analytics Cloud and Microsoft Excel via live connection.

> ### Note:  
> Before exposing data for consumption, you should consider applying row-level security via data access controls \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:\).



<a name="loiod7d56284bb5148c887ac4054689bfbca__section_sac"/>

## Consume Data in SAP Analytics Cloud

You can create a live connection from SAP Analytics Cloud to SAP Datasphere and consume data exposed as analytic models, perspectives, and views to create stories and analytic applications.

![](images/Consumption_-_SAC_-_Live_Connection_3508362.png)

You must:

-   Be a SAP Datasphere user with any of the standard roles. If you do not need to connect to SAP Datasphere itself, and only consume data, then an administrator can grant you the *DW Consumer* role \(see [Standard Application Roles](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles.") :arrow_upper_right:\).

    If data access controls have been applied, then the data you can consume will be filtered based on your user id \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:\).

-   Be a member of the SAP Datasphere space exposing the data \(see [Assign Members to Your Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/9d59fe511ae644d98384897443054c16.html "As a Space Administrator, you can assign users as members of your space.") :arrow_upper_right:\).
-   Have access to an SAP Analytics Cloud tenant and have the role *BI Content Creator* or another role providing equivalent privileges.
-   Create or have access to an SAP Analytics Cloud live data connection to your SAP Datasphere tenant \(see [Live Data Connections to SAP Datasphere](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/ad4281e2875949f0b4d45d1072ff4c38.html) in the *SAP Analytics Cloud* documentation\).

For more information, see [Consume Data in SAP Analytics Cloud via a Live Connection](consume-data-in-sap-analytics-cloud-via-a-live-connection-a2c5486.md).

SAP Analytics Cloud can also consume SAP Datasphere via an OData service \(see [Consume Data in SAP Analytics Cloud via an ODATA Service](consume-data-in-sap-analytics-cloud-via-an-odata-service-9de2c66.md)\).



<a name="loiod7d56284bb5148c887ac4054689bfbca__section_excel"/>

## Consume Data in Microsoft Excel

You can create a live connection from SAP Analytics Cloud to SAP Datasphere and consume data exposed as analytic models, perspectives, and views in Microsoft Excel, via the SAP Analytics Cloud add-in for Microsoft Office.

![](images/Consumption_-_Excel_-_Live_Connection_fb0d22e.png)

You must:

-   Install the add-in \(see [Deploying the Add-In](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD_OFFICE/2b73edbc8f8f4189a36bc7a2e038185c/6a191aeefd5c464aa2adc4e1a69d4523.html) in the *SAP Analytics Cloud, Add-In for Microsoft Office* documentation.
-   Be a SAP Datasphere user with any of the standard roles. If you do not need to connect to SAP Datasphere itself, and only consume data, then an administrator can grant you the *DW Consumer* role \(see [Standard Application Roles](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles.") :arrow_upper_right:\).

    If data access controls have been applied, then the data you can consume will be filtered based on your user id \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:\).

-   Be a member of the SAP Datasphere space exposing the data \(see [Assign Members to Your Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/9d59fe511ae644d98384897443054c16.html "As a Space Administrator, you can assign users as members of your space.") :arrow_upper_right:\).
-   Have access to an SAP Analytics Cloud tenant and have the role *BI Content Creator* or another role providing equivalent privileges.
-   Create or have access to an SAP Analytics Cloud live data connection to your SAP Datasphere tenant \(see [Live Data Connections to SAP Datasphere](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/ad4281e2875949f0b4d45d1072ff4c38.html) in the *SAP Analytics Cloud* documentation\).

For more information, see [Consume Data in Microsoft Excel via an SAP Add-In](consume-data-in-microsoft-excel-via-an-sap-add-in-ef6e226.md).



<a name="loiod7d56284bb5148c887ac4054689bfbca__section_bi_clients"/>

## Consume Data in Other Clients, Tools, and Apps

You can consume data exposed from SAP Datasphere clients, tools, and apps via an OData service or via a database user/Open SQL schema \(see [Consume Data in Power BI and Other Third-Party Clients, Tools, and Apps](consume-data-in-power-bi-and-other-third-party-clients-tools-and-apps-add771a.md)\).



<a name="loiod7d56284bb5148c887ac4054689bfbca__section_odata"/>

## Consume Data via an OData Service

You can connect to the OData API and consume data exposed as views in SAP Analytics Cloud and other clients, tools, and apps that are capable of accessing an OData service and authenticating via an OAuth client.

![](images/Consumption_-_OData_9431afe.png)

You must:

-   Be a SAP Datasphere user with any of the standard roles. If you do not need to connect to SAP Datasphere itself, and only consume data, then an administrator can grant you the *DW Consumer* role \(see [Standard Application Roles](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles.") :arrow_upper_right:\).

    If data access controls have been applied, then the data you can consume will be filtered based on your user id \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:\).

-   Be a member of the SAP Datasphere space exposing the data \(see [Assign Members to Your Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/9d59fe511ae644d98384897443054c16.html "As a Space Administrator, you can assign users as members of your space.") :arrow_upper_right:\).
-   Obtain the following parameters for an OAuth client defined in your SAP Datasphere tenant:
    -   Client ID
    -   Secret
    -   Token URL
    -   Authorization URL


For more information, see [Consume Data via an OData Service](consume-data-via-an-odata-service-7a45360.md).

