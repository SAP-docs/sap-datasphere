<!-- loioea382a4ecb004cdd8edceebb63c7645b -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Natural Language Search

If natural language search is enabled on your tenant \(and you have the appropriate role\), the search field will propose example natural language strings that are appropriate to your current filter context. Select an example string or enter your own and SAP Datasphere will interpret it and filter your results accordingly.



## Prerequisites

To use natural language search in the *Data Products* collection, it must be enabled in your tenant \(see [Enable SAP Business AI for SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/1b3fe45f38df4db1a9cda97a5a7bcdaf.html "SAP Business AI is a fully managed service by SAP that allows you to integrate artificial intelligence (AI) models in different business solutions. SAP Business AI provides a simple and easy-to-use API with various endpoints that you can use in your solution for different tasks such as text generation, summarization, language translation, creative content development.") :arrow_upper_right:\) and you must also have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse AI Consumption* \(`–--–E--`\) - To use SAP Business AI features.

A combination of the *Catalog Administrator* global role, the *DW AI consumer* global role, and the *DW Viewer* role template \(used directly as a global role\) applied together, for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



## Using Natural Language Search

Entering a natural language search string allows you to quickly find data products without looking for specific filter settings. Natural language search is only available for the *Data Products* collection.

> ### Note:  
> Natural language search is supported in English only, but may provide useable results in other languages.

To use the natural language search, select the *Data Products* collection, and enter a request. The use of natural language is not automatic and depends on the string entered:

-   One word - Natural language search is not used.
-   Two words - Natural language search is used if the standard search returns no results.
-   Three or more words - Natural language search is always used.

You can, at any time, click the <span class="SAP-icons-V5"></span> \(Show AI-Generated Filter Conditions\) to verify how SAP Datasphere interpreted the search phrase you entered.

You can enter requests that contain:


<table>
<tr>
<th valign="top">

Request Feature

</th>
<th valign="top">

Examples

</th>
</tr>
<tr>
<td valign="top">

Conceptual grouping

</td>
<td valign="top">

-   `show me data products with supply chain datasets`
    -   Returns all data products that are related to the supply chain line of business




</td>
</tr>
<tr>
<td valign="top">

`and`, `or`, and `not` combinations

</td>
<td valign="top">

-   `industry agriculture and release status active`
    -   Returns all data products that meet both conditions

-   `industry agriculture or release status active`
    -   Returns all data products that meet either condition

-   `not industry agriculture`
    -   Returns all data products that are in any industry except **agriculture** 




</td>
</tr>
<tr>
<td valign="top">

Data product and source properties or other filter categories

</td>
<td valign="top">

-   `data products named Sales with deployment region US East (NYC)`
    -   Returns all data products with "Sales" in their name and have US East \(NYC\) deployment region


You can search text in the filter categories and these contents:

-   Name

-   Description

-   Formation ID

-   Related Entity Business Name

-   Related Entity Container Path

-   Related Entity Business Name


For a list of data product filter categories, see [Filter Category Details](filter-category-details-3b5725b.md).

</td>
</tr>
</table>

