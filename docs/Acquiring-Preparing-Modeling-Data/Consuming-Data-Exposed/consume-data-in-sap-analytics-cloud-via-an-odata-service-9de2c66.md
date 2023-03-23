<!-- loio9de2c660fd3b4db2b89ad25e584e8857 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Consume Data in SAP Analytics Cloud via an ODATA Service

You can create an import data connection in SAP Analytics Cloud to consume data from a view exposed via the SAP Datasphere OData API, and consume it in an SAP Analytics Cloud model or directly in a story.

This topic contains the following sections:

-   [Create an SAP Analytics Cloud OData Services Connection to an SAP Datasphere View](consume-data-in-sap-analytics-cloud-via-an-odata-service-9de2c66.md#loio9de2c660fd3b4db2b89ad25e584e8857__section_create_odata_connection)
-   [Create a Model from Your Connection](consume-data-in-sap-analytics-cloud-via-an-odata-service-9de2c66.md#loio9de2c660fd3b4db2b89ad25e584e8857__section_odata_in_model)
-   [Consume Your Connection Directly in a Story](consume-data-in-sap-analytics-cloud-via-an-odata-service-9de2c66.md#loio9de2c660fd3b4db2b89ad25e584e8857__section_odata_in_story)



<a name="loio9de2c660fd3b4db2b89ad25e584e8857__section_create_odata_connection"/>

## Create an SAP Analytics Cloud OData Services Connection to an SAP Datasphere View

You can create an OData services connection in SAP Analytics Cloud to load \(replicate\) data from an SAP Datasphere view to SAP Analytics Cloud.

You must:

-   Be a SAP Datasphere user with any of the standard roles. If you do not need to connect to SAP Datasphere itself, and only consume data, then an administrator can grant you the *DW Consumer* role \(see [Standard Application Roles](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles.") :arrow_upper_right:\).

    If data access controls have been applied, then the data you can consume will be filtered based on your user id \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:\).

-   Obtain the following parameters for an OAuth client defined in your SAP Datasphere tenant:
    -   Client ID
    -   Secret
    -   Token URL
    -   Authorization URL

-   Have access to an SAP Analytics Cloud tenant and have the role *BI Content Creator* or another role providing equivalent privileges.

1.  Navigate to your SAP Analytics Cloud tenant.

    > ### Note:  
    > If an administrator has configured a connection to an SAP Analytics Cloud tenant \(and you are assigned one or more BI roles\), you can use the <span class="SAP-icons"></span> \(*Product Switch*\) in the top-right corner of the screen to navigate.

2.  In the side navigation area, click <span class="FPA-icons"></span>. 
3.  Click *Add Connection*, select *OData Services* to open the *New OData Services Connection* dialog, and complete the fields as follows:


    <table>
    <tr>
    <th valign="top">

    Parameter


    
    </th>
    <th valign="top">

    Value


    
    </th>
    </tr>
    <tr>
    <td valign="top">

    Connection Name


    
    </td>
    <td valign="top">

    Enter an appropriate name for your connection.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Data Service URL


    
    </td>
    <td valign="top">

    Enter the full URL to your SAP Datasphere view in the following format:

    ```
    https://<tenant_url>.cloud.sap/dwaas-core/odata/v4/consumption/relational/<Space_ID>/<view>
    ```

    .


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Authentication Type


    
    </td>
    <td valign="top">

    Select *OAuth 2.0 Authorization Code*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    OAuth Client ID

    Secret

    Token URL

    Authorization URL


    
    </td>
    <td valign="top">

    Enter the values for your SAP Datasphere OAuth client.


    
    </td>
    </tr>
    </table>
    
4.  Click *Create* to create the connection.



<a name="loio9de2c660fd3b4db2b89ad25e584e8857__section_odata_in_model"/>

## Create a Model from Your Connection

You can use your OData Services connection to load your view's data into an SAP Analytics Cloud model for use by one or more stories:

1.  In the side navigation area, click *Modeler*.
2.  Click the *From a Data Source* tile and then select *OData Services*.
3.  In the *Create Model from OData Services* dialog, select your connection in the list and click *Next*.

    Follow the usual steps in the *New Query for OData Services* dialog \(see [Building a Query](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/a8435da6970041d2beb3299cdcff7026.html?locale=en-US&q=%22new%20query%20for%20odata%20services%22#building-a-query) in the *SAP Analytics Cloud* documentation.




<a name="loio9de2c660fd3b4db2b89ad25e584e8857__section_odata_in_story"/>

## Consume Your Connection Directly in a Story

You can use your OData Services connection to load your view's data directly into an SAP Analytics Cloud story without passing by a model:

1.  In the side navigation area, click *Stories*.
2.  Click the *Responsive* or *Canvas* tile, select *Optimized Design Experience*, and then click *Create*.
3.  Click *Add New Data*, select *Data From a Data Source*, and then select *OData Services*.
4.  In the *Create Dataset from OData Services* dialog, select your connection in the list and click *Next*.

    Follow the usual steps in the *New Query for OData Services* dialog \(see [Building a Query](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/a8435da6970041d2beb3299cdcff7026.html?locale=en-US&q=%22new%20query%20for%20odata%20services%22#building-a-query) in the *SAP Analytics Cloud* documentation.


