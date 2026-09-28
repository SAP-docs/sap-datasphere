<!-- loio9c582ca295164a538cb61b7e7beb6719 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Custom Connection Type

Create a custom connection type to allow users assigned to a SAP Datasphere file space to connect to external REST APIs and load JSON-based data into the SAP Datasphere object store using replication flows.

> ### Note:  
> Custom connection types to connect to REST APIs are not available by default in SAP Datasphere tenants. To enable custom connection types in your tenant, see SAP note [3696110](https://me.sap.com/notes/3696110).

This topic contains the following sections:

-   [Prerequisites](creating-a-custom-connection-type-9c582ca.md#loio9c582ca295164a538cb61b7e7beb6719__prerequisites)
-   [Context](creating-a-custom-connection-type-9c582ca.md#loio9c582ca295164a538cb61b7e7beb6719__context)
-   [REST API Requirements](creating-a-custom-connection-type-9c582ca.md#loio9c582ca295164a538cb61b7e7beb6719__REST_API_requirements)
-   [Procedure](creating-a-custom-connection-type-9c582ca.md#loio9c582ca295164a538cb61b7e7beb6719__procedure)
-   [Results](creating-a-custom-connection-type-9c582ca.md#loio9c582ca295164a538cb61b7e7beb6719__results)

> ### Note:  
> This feature is only available for file spaces \(spaces with a storage type of *SAP HANA Data Lake Files*\).



<a name="loio9c582ca295164a538cb61b7e7beb6719__prerequisites"/>

## Prerequisites

To create, edit, and delete custom connection types, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`CRUD----`\) - To create, edit, or delete custom connection types.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Space Administrator* and *DW Integrator* role templates, for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio9c582ca295164a538cb61b7e7beb6719__context"/>

## Context

Your landscape likely includes multiple applications from different vendors, each producing its own datasets. These datasets often remain siloed, making it hard to unify and use them for analytics, AI, or other consumption scenarios. Custom connection types allow you to bridge this gap, acting as a blueprint for connecting SAP Datasphere to external REST APIs. This capability lets you ingest data from external systems into SAP Datasphere, and allows you to define reusable connection types for consistent integration patterns.

When you create a custom connection type, you abstract external API resources into reusable artifacts. These artifacts allow SAP Datasphere to invoke the relevant API endpoints and transform JSON responses into structured entities.

When creating a custom connection type, you define:

-   **Resources**: The API endpoints you want to consume.
-   **Actions**: The configurations that define how data is retrieved from a resource and transformed into entities that can be consumed by replication flows.
-   **Schemas**: The structure of the API response.

The tables derived from the schema for use in SAP Datasphere are referred to as *Entities*.

Before you start, keep these principles in mind:

-   Multiple response schemas per resource are supported.
-   Entities exist only within the context of an action. There is no global entity model.
-   Foreign key relationships must be explicitly defined. There are no inferred associations \(see [Define Actions](define-actions-89e20b8.md) \).
-   Resource settings \(pagination, API rate limits, retry codes\) apply at the resource level.
-   When consuming an action, all entities defined for that action are included.
-   You can enable format and allowed-value validation for schema attributes of type string.

Once the connection type is created, you can use it to create connection instances by providing credentials and endpoint URLs. These connections then feed data into replication flows.

> ### Caution:  
> Custom connection types are completely decoupled from any connection instances you create from them. If you edit and save a custom connection type after you have created connections from it, these changes don't affect the existing connections. You can also delete a custom connection type even if connections exist that were created from it. These connections continue to work even after you delete the custom connection type.
> 
> If you need the changes made to a custom connection type to be reflected in a connection, the necessary steps and considerations are described in [Edit a Custom Connection Type](edit-a-custom-connection-type-80d8b8a.md).



<a name="loio9c582ca295164a538cb61b7e7beb6719__REST_API_requirements"/>

## REST API Requirements

For an external REST API to be compatible with a custom connection type, the following requirements must be met:

-   **Base URL**: The API must expose a reachable HTTPS base URL \(for example, `https://api.example.com`\).
-   **Response format**: All API responses must return JSON. Non-JSON formats such as XML, CSV, and binary are not supported.
-   **Records locators**: The response must contain records in a predictable, consistent location that can be expressed as a path \(for example, `$.orders` or `$.results`\). This location must be of type object array. This is the records locator you specify when defining an action. If records are scattered or structured inconsistently across responses, the API cannot be consumed.
-   **Response schema**: The response structure must be consistent and expressible as a schema. APIs with fully dynamic response schemas where the structure changes per response are not supported.
-   **Pagination**: The API must use one of the supported pagination methods: Page, Offset, Next URL, or Cursor. APIs without pagination or with proprietary pagination mechanisms are not supported.
-   **Entity keys**: SAP Datasphere uses object-relational mapping during action definition to derive flat entities from the \(potentially\) nested response schema. During object relational mapping, you set key attributes to establish primary keys and parent-child relationships between entities. Each nested object array within the records locator object array in the response schema that you intend to map to an entity must contain at least one attribute that uniquely identifies its elements.

    For more information, see [Define Actions](define-actions-89e20b8.md).

-   APIs that require interactive or browser-based authentication are not supported. The supported authentication methods are basic, mTLS, oAuth2, and custom.



<a name="loio9c582ca295164a538cb61b7e7beb6719__procedure"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Connections*\) and select a space if necessary.
2.  On the *Custom Connection Types* tab, click <span class="FPA-icons-V3"></span> \(Add Connection Type\) ** to open the custom connection type creation wizard.
3.  In the *Details* section under *Details*, enter the following information:


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
    
4.  In the *Details* section under *Authentication*, select the authentication types that can be used when sending requests to the connection type's endpoints. When creating a connection from this connection type, you will be required to select an authentication type and provide the relevant information.


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
    
    *Basic*
    
    </td>
    <td valign="top">
    
    When creating a connection from this connection type, you need to authenticate with a username and password.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *mTLS*
    
    </td>
    <td valign="top">
    
    When creating a connection from this connection type, you need to provide an mTLS certificate and RSA private key for authentication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *oAuth2*
    
    </td>
    <td valign="top">
    
    Generates OAuth2.0 fields in the connection for authenticating according to the OAuth 2.0 protocol. Enable the flow or flows you wish to support for this application.

    The following two OAuth flows are supported:

    -   authorization code

    -   client credentials \(supported in body and header\)


    When creating a connection from this connection type, you need to provide the relevant OAuth information and credentials for authentication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Custom*
    
    </td>
    <td valign="top">
    
    When creating a connection from this connection type, you will be required to enter the parameter values required for authentication by the target application.

    > ### Caution:  
    > Custom authentication, especially using query parameters, is not recommended, as these parameter values can be exposed in external system logs.


    
    </td>
    </tr>
    </table>
    
5.  In the *Resources* section, define one or more resources for your custom connection type, which represent the API endpoints you want to consume \(see [Define Resources](define-resources-f22b258.md)\).
6.  In the *Resources Settings* section, for each resource defined in step 5, define settings such as pagination, rate limits, and retryable status codes \(see [Define Resource Settings](define-resource-settings-0e2f033.md)\).
7.  In the *Actions* section, for each resource defined in step 5, define one ore more actions \(see [Define Actions](define-actions-89e20b8.md)\). Actions specify how data is extracted from a resource, including the records to ingest and how the API response is mapped into entities for use in SAP Datasphere.
8.  In the *Overview* section, review the connection type's resources, resource settings, and actions. If required, you can navigate back to the *Resources*, *Resource Settings* and *Actions* sections to modify their configuration.
9.  Click *Create* to create the connection type.

    > ### Note:  
    > Validation is not supported for custom connection types.




<a name="loio9c582ca295164a538cb61b7e7beb6719__results"/>

## Results

Once the connection type is created, you can create a connection based on it. For more information, see [Create a Connection from a Custom Connection Type](create-a-connection-from-a-custom-connection-type-d0653d3.md).

If you need to modify the custom connection type, you can do so as described in [Edit a Custom Connection Type](edit-a-custom-connection-type-80d8b8a.md).

