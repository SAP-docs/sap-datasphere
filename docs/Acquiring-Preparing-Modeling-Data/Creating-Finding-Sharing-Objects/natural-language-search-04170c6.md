<!-- loio04170c64c1004fc58d7f235aea0e4970 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Natural Language Search

If natural language search is enabled on your tenant \(and you have the appropriate role\), the search field will propose example natural language strings that are appropriate to your current filter context. Select an example string or enter your own and SAP Datasphere will interpret it and filter your results appropriately.



<a name="loio04170c64c1004fc58d7f235aea0e4970__section_pdb_kbv_sdc"/>

## Prerequisites

To use natural language search, it must be enabled in your tenant \(see [Enable SAP Business AI for SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/1b3fe45f38df4db1a9cda97a5a7bcdaf.html "SAP Business AI is a fully managed service by SAP that allows you to integrate artificial intelligence (AI) models in different business solutions. SAP Business AI provides a simple and easy-to-use API with various endpoints that you can use in your solution for different tasks such as text generation, summarization, language translation, creative content development.") :arrow_upper_right:\) and you must have both a global role and a scoped role:

-   A global role that grants you the following privilege:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Data Warehouse AI Consumption* \(`----E---`\) - To use SAP Business AI features.

-   A scoped role that grants you access to the space or spaces to search in with the following privilege:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Spaces Files* \(`-R------`\) - To access objects in a space.


The *DW AI Consumer* global role and the *DW Modeler* scoped role template, applied together for example, grant these privileges \(see [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right: and [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right:\).



<a name="loio04170c64c1004fc58d7f235aea0e4970__section_ahd_jbv_sdc"/>

## Using Natural Language Search

Entering a natural language search string allows you to quickly filter your list of objects without looking for specific filter settings.

Natural language search is available in:

-   The *Repository Explorer* - See [Repository Explorer](repository-explorer-f8ce0b4.md).
-   The *Data Builder* start page - See [Acquiring Data](../Acquiring-and-Preparing-Data-in-the-Data-Builder/acquiring-data-1f15a29.md).
-   The *Source Browser* - See [Using the Source Browser](../using-the-source-browser-7d2b21d.md).

> ### Note:  
> Natural language search is supported in English only, but may provide useable results in other languages.

You can, at any time, click the <span class="SAP-icons-V5"></span> \(Show AI-Generated Filter Conditions\) to verify how SAP Datasphere has interpreted your phrase.

> ### Note:  
> The use of natural language is not automatic and depends upon the string entered:
> 
> -   One word - Natural language search is not used.
> -   Two words - Natural language search is used if the standard search returns no results.
> -   Three or more words - Natural language search is always used.

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

-   `show me all tables`
    -   Returns both local tables and remote tables.

-   `all non-facts`
    -   Returns all views, local tables, and remote tables that have a semantic usage other than *Fact*.




</td>
</tr>
<tr>
<td valign="top">

`and`, `or`, and `not` combinations

</td>
<td valign="top">

-   `semantic usage fact and status pending`
    -   Returns objects that meet both conditions.

-   `semantic usage fact or status pending`
    -   Returns objects that meet either condition.

-   `not not deployed`
    -   Returns objects with any status except *Not Deployed*.




</td>
</tr>
<tr>
<td valign="top">

Columns, attributes, measures, dimensions, or other contents

</td>
<td valign="top">

-   `Tables with a measure called sales id` 
    -   Returns all views containing such a measure.

-   `Analytic models with a dimension called country id` 
    -   Returns all analytic models containing such a dimension.

-   `Views with a data access control` 
    -   Returns all views that are associated with one or more data access controls.


You can search for tables, views, analytic models and *Business Builder* objects based on the presence of any \(or for names of\) the following types of contents:

-   Columns, measures, attributes, or dimensions
-   Input parameters \(views\) or variables \(analytic models\)
-   Data access controls
-   Associations
-   Filters \(presence in analytic models only\)

> ### Note:  
> Analytic models with design-time errors cannot be found via their contents.



</td>
</tr>
<tr>
<td valign="top">

Date and time ranges

</td>
<td valign="top">

-   `all objects created in the last week`
    -   Returns all objects created in the last seven days up to and including today.

-   `all objects deployed last week`
    -   Returns all objects deployed in the previous week.

-   `all objects modified in the last 6 hours`
    -   Returns all objects modified in the last six hours up to now.




</td>
</tr>
<tr>
<td valign="top">

Spaces or folders criteria

</td>
<td valign="top">

-   `Facts in Sales`
    -   Where `Sales` can be a space or a folder.




</td>
</tr>
<tr>
<td valign="top">

Business and technical name criteria

</td>
<td valign="top">

-   `all views called sales`
-   `all views beginning sales`
-   `all views with a technical name ending in sales that are deployed and released`



</td>
</tr>
<tr>
<td valign="top">

Ordering

</td>
<td valign="top">

-   `Views most recently deployed first`
    -   Returns views ordered by *Deployment Date*.




</td>
</tr>
</table>

> ### Note:  
> You cannot search for objects based on their associations with other objects.

