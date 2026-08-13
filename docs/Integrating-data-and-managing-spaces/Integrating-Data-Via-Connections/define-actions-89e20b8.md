<!-- loio89e20b89462a4603a3a524091d255528 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Actions

Actions define how SAP Datasphere retrieves data from a resource and transforms the API response into entities. An action specifies the resource to call, any request parameter values, the response schema to use, the records to ingest, and the keys that define entity relationships.



## Context

Actions are defined at the resource level, and each resource can have multiple actions. An action represents a specific data extraction configuration for a resource. Different actions can use different request parameter values, response schemas, records locators, and entity definitions while referencing the same resource. The entity definitions that are part of the object relational mapping are derived from the nested json response schema by defining json attributes as keys \(see step 2. in the below procedure description\).

When creating a connection based on the custom connection type, you can select which actions you want to offer as source containers to replication flows. When selecting an action from the connection as source container in a replication flow, its entities will be added as replication objects. The target objects will be generated automatically based on the entities once you select the SAP Datasphere object store \(HDL\_FILES\) as target connection in the replication flow.



## Procedure

1.  To add an action, in the *Actions* section of the custom connection type dialog click <span class="FPA-icons-V3"></span> \(Add another entity\).

2.  Under *Details*, enter the following information:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Business Name*
    
    </td>
    <td valign="top">
    
    Enter a descriptive name to help users identify the object. This name can be changed at any time.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Technical Name*
    
    </td>
    <td valign="top">
    
    Displays the name used in scripts and code, synchronized by default with the *Business Name*.

    The technical name can only contain alphanumeric characters and underscores \(\_\). It cannot start or end with underscore \(\_\). The name must be unique within the space.

    > ### Note:  
    > The system generates target object \(table\) names in a replication flow using the format <code><i class="varname">&lt;custom_connection_technical_name&gt;</i>.<i class="varname">&lt;action_technical_name&gt;</i>.<i class="varname">&lt;entity_name&gt;</i></code>. The maximum total length is 100 characters: 15 for connection, 45 for action, and 40 for entity. If a component name exceeds its character limit, the system truncates it. This truncation can create duplicate target object names, causing your replication flow deployment to fail.
    > 
    > You cannot rename the target object or map to an existing target object. To avoid duplicates, choose your connection, action, and entity names carefully.

    > ### Note:  
    > Once the object is saved, the technical name can no longer be modified.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description*
    
    </td>
    <td valign="top">
    
    Provide more information to help users understand the object.
    
    </td>
    </tr>
    </table>
    
3.  Under *Resources*, select the resource you want to associate the action to. In the drop down you can see all the resources you have previously defined in the *Resources* screen.

    Once you have associated an action to a resource, the resource becomes protected from deletion and editing.

4.  Under *Request Parameters*, you can define the values for the request parameters you defined in the *Resources* screen.

    Request parameter values can include dynamic placeholders such as `${lastRunTime:<format>}` and `${now:<format>}`. For more information, see [Use Dynamic Placeholders in Request Parameter Values](use-dynamic-placeholders-in-request-parameter-values-1e05f83.md).

5.  Under *Schemas*, you need to define the response schema for the action, including the records locator and entity keys.


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Schema*
    
    </td>
    <td valign="top">
    
    Select one of the response schemas defined for this resource from the drop down. The response schema defines the structure of the returned data and determines how the data is interpreted and ingested.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Records Locator*
    
    </td>
    <td valign="top">
    
    Choose the response schema attribute that represents the records locator, which is the array of objects within the schema that contains the records to be ingested. The records locator identifies the array of objects in the API response that contains the records to be ingested. It determines the root dataset from which entities are derived for the action.

    -   If the schema root is an array of objects, you must set the root as the records locator.
    -   If the schema root is an object with just one array at the parent level, you must set the array as the records locator.
    -   If the schema root is an object with multiple arrays at the parent level, you can set any parent-level array as a records locator.
    -   If the schema root is an object, you can also choose a nested array as a records locator, as long as the array is nested only within object properties and is not nested within another array of objects.
    -   If the schema root is an object and there are no arrays present, the schema is not compatible with batch ingestion and you cannot select a records locator. You cannot use such JSON schemas to replicate data into SAP Datasphere.

    > ### Note:  
    > You can only set array attributes of type object array as records locators. Arrays of string, number, integer or Boolean attributes are not supported as records locators.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Keys*
    
    </td>
    <td valign="top">
    
    Set a key within the response schema. To do so, select the three dots to the right of a schema attribute name and select *Set Key*.

    Keys identify the attributes that uniquely distinguish records within an entity.SAP Datasphere uses these keys to create primary keys and establish foreign key relationships between entities derived from the action's response schema.

    Once you set a key, a corresponding entity is derived based on that key definition, and the entity appears on the right.

    -   Entities are generated for an action based on the selected response schema and records locator. Each action has its own scoped set of entities, derived directly from the API response structure.
    -   There is no concept of linking entities across actions or resources. Entities exist only within the context of the specific action they are defined in.
    -   Entities are related using explicit foreign key relationships only. A child entity must include a direct reference to the parent’s primary key. Inferred associations or many-to-many relationships are not supported.


    
    </td>
    </tr>
    </table>
    

