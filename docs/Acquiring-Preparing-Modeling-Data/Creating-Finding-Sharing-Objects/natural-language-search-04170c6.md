<!-- loio04170c64c1004fc58d7f235aea0e4970 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Natural Language Search

If natural language search is enabled on your tenant \(and you have the appropriate role\), the search field will propose example natural language strings that are appropriate to your current filter context. Select an example string or enter your own and SAP Datasphere will interpret it and filter your results appropriately.



<a name="loio04170c64c1004fc58d7f235aea0e4970__section_pdb_kbv_sdc"/>

## Prerequisites

To use natural language search, it must be enabled in your tenant \(see [Enable SAP Business AI for SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/1b3fe45f38df4db1a9cda97a5a7bcdaf.html "SAP Business AI is a fully managed service by SAP that allows you to integrate artificial intelligence (AI) models in different business solutions. SAP Business AI provides a simple and easy-to-use API with various endpoints that you can use in your solution for different tasks such as text generation, summarization, language translation, creative content development.") :arrow_upper_right:\) and you must have both a global role and a scoped role:

-   A global role that grants you the following privilege:
    -   *Data Warehouse AI Consumption* \(`----E---`\) - To use SAP Business AI features.

-   A scoped role that grants you access to the space or spaces to search in with the following privilege:
    -   *Spaces Files* \(`-R------`\) - To access objects in a space.


The *DW AI Consumer* global role and the *DW Modeler* scoped role template, applied together for example, grant these privileges \(see [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right: and [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right:\).

Natural language search is available in:

-   The *Repository Explorer* - See [Repository Explorer](repository-explorer-f8ce0b4.md).
-   The *Data Builder* start page - See [Acquiring Data in the Data Builder](../Acquiring-and-Preparing-Data-in-the-Data-Builder/acquiring-data-in-the-data-builder-1f15a29.md).
-   The *Source Browser* - See [Using the Source Browser](../using-the-source-browser-7d2b21d.md).

> ### Note:  
> Natural language search is supported in English only, but may provide useable results in other languages.



<a name="loio04170c64c1004fc58d7f235aea0e4970__section_ahd_jbv_sdc"/>

## Using Natural Language Search

Entering a natural language search string allows you to quickly filter your list of objects without looking for specific filter settings.

You can, at any time, click the <span class="SAP-icons-V5"></span> \(Show AI-Generated Filter Conditions\) to verify how SAP Datasphere has interpreted your phrase.

> ### Note:  
> The use of natural language is not automatic and depends upon the string entered:
> 
> -   One word - Natural language search is not used.
> -   Two words - Natural language search is used if the standard search returns no results.
> -   Three or more words - Natural language search is always used.

You can enter requests that:

-   Return conceptual groups covering :
    -   `show me all tables`
        -   Returns both local tables and remote tables.

    -   `all non-facts`
        -   Returns all views, local tables, and remote tables that have a semantic usage other than *Fact*.


-   Contain and, or, and not combinations:
    -   `semantic usage fact and status pending`
        -   Returns objects that meet both conditions.

    -   `semantic usage fact or status pending`
        -   Returns objects that meet either condition.

    -   `not not deployed`
        -   Returns objects with a status which is not *Not Deployed*.


-   Date and time ranges:
    -   `all objects created in the last week`
        -   Returns all objects created in the last seven days up to and including today.

    -   `all objects deployed last week`
        -   Returns all objects deployed in the previous week.

    -   `all objects modified in the last 6 hours`
        -   Returns all objects modified in the last six hours up to now.


-   Search in spaces or folders as appropriate:
    -   `Facts in Sales`
        -   Where `Sales` can be a space or a folder.


-   Search both business and technical names or constrain your search as necessary:
    -   `all views called sales`
    -   `all views beginning sales`
    -   `all views with a technical name ending in sales that are deployed and released`

-   Include ordering:
    -   `Views most recently deployed first`
        -   Returns views ordered by *Deployment Date*.



> ### Note:  
> You cannot search for objects based on columns they contain or their associations with other objects.

