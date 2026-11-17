<!-- loiocc0fad818e9b4d409c43969195d3fd82 -->

# Rest API Custom Connection Sources for Replication Flows

You can use REST API connections as sources in replication flows to replicate data into local table file spaces, using SAP Datasphere \(HDL\_Files\) as the target. The REST API acts as a data source similar to other connections. When you select an action from the connection, the system retrieves data records from the API response and creates corresponding replication objects.



## Prerequisites

-   Make sure you have created a REST API connection in *Connection Management* and that it is available in your space. For more information, see:
    -   [Create a Connection from a Custom Connection Type](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/d0653d37167a49679d0a3e909547a674.html "Create a connection from custom connection type to allow users assigned to a file space to use the connected REST API source for loading JSON-based data to the SAP Datasphere object store using replication flows.") :arrow_upper_right:
    -   [Creating a Custom Connection Type](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/9c582ca295164a538cb61b7e7beb6719.html "Create a custom connection type to allow users assigned to a SAP Datasphere file space to connect to external REST APIs and load JSON-based data into the SAP Datasphere object store using replication flows.") :arrow_upper_right:

-   The REST API returns JSON data containing at least one array.
-   You can only create a replication flow with a REST API source in a local table file space.
-   Only SAP Datasphere \(HDL\_Files\) targets are supported.
-   Only *Initial and Delta* load type is supported.
-   Delta load metrics such as delta record count and delta run count are recorded only when delta synchronization is configured for the REST API connection. To configure delta synchronization, define a filter or query parameter supported by the target API and use the `${lastRunTime:<format>}` placeholder in the parameter value \(see [Use Dynamic Placeholders in Request Parameter Values](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/1e05f8338caf48c29c2a3440530f8255.html "Dynamic placeholders in request parameter values automatically insert runtime values into requests sent by a custom connection type.") :arrow_upper_right:\). Without delta synchronization, delta metrics are cumulative because each delta run processes all available records.



## Procedure

1.  Select a REST API connection as the source.
2.  Select the source container.

    REST API connections are structured in the following manner:

    -   Inside each connection is one or more resources. A resource can represent something like *GetAuditActivities*.

    -   Inside each resource can be one or more actions. You must select an action as your source container.


3.  Select an action container.

    All entities within the selected action are automatically added as replication objects.

4.  The system creates one replication object for each entity and automatically generates corresponding target objects in the repository.

    Each action contains one root entity and may contain other non-root entities that are dependent on the root entity and cannot be managed independently.

    > ### Note:  
    > The system generates target object \(table\) names in a replication flow using the format <code><i class="varname">&lt;custom_connection_technical_name&gt;</i>_<i class="varname">&lt;action_technical_name&gt;</i>_<i class="varname">&lt;entity_name&gt;</i></code>. The maximum total length is 100 characters: 15 for connection, 45 for action, and 40 for entity. If a component name exceeds its character limit, the system truncates it. This truncation can create duplicate target object names, causing your replication flow deployment to fail.
    > 
    > You cannot rename the target object or map to an existing target object. To avoid duplicates, choose your connection, action, and entity names carefully.
    > 
    > Note that prior to version 2026.18, replication flow target table names were generated with dots \(.\) instead of underscores \(\_\). If your replication flow returns errors related to the target table name, see SAP Note [3794129](https://me.sap.com/notes/3794129).

5.  Select SAP Datasphere \(HDL\_Files\) as the target connection.
6.  Select a replication object and complete the settings as follows:


    <table>
    <tr>
    <th valign="top">

    Properties
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Storage
    
    </td>
    <td valign="top">
    
    This describes the type of storage available in the space.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delta Capture
    
    </td>
    <td valign="top">
    
    \[only relevant for local tables\] Enable this option if you want the system to keep track of changes in your data source. Once enabled, the name of the delta capture table is displayed.For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Load Type
    
    </td>
    <td valign="top">
    
    Select the following load type:

    -   *Initial and Delta* - Replicate the data from the object at the start of the run and then continue to replicate inserted and updated records at specified intervals \(or scheduled times\).


    
    </td>
    </tr>
    </table>
    



## Restrictions

-   Projection features such as filtering and mapping are not supported.
-   Source settings are not available for this source type.
-   The replication flow UI does not support existing target objects. Target object names are automatically derived from the resource, action, and entity names and are expected to be unique.
-   You cannot modify individual replication objects or pause, resume, and retry them.

-   Source or target schema changes are not supported after deployment.
-   Deleted records in the REST API source are not deleted from the SAP Datasphere target. REST API replication supports insert and update \(upsert\) operations only.




## Replicating Source Objects Without Primary Keys

Replicating source objects without a primary key is not supported. Only source objects that have a primary key defined can be used as source objects in a replication flow.



## Data Types

The following table shows how REST API source data types are mapped to internal data types. Data types that are not supported are skipped during replication.


<table>
<tr>
<th valign="top">

Schema Attribute Type

</th>
<th valign="top">

Supported

</th>
<th valign="top">

Target Column Type

</th>
<th valign="top">

Notes

</th>
</tr>
<tr>
<td valign="top">

number

</td>
<td valign="top">

Yes

</td>
<td valign="top">

DOUBLE

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

number, format: double

</td>
<td valign="top">

Yes

</td>
<td valign="top">

DOUBLE

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

number, format: float

</td>
<td valign="top">

No

</td>
<td valign="top">

\-

</td>
<td valign="top">

Will cause replication failure. Do not use.

</td>
</tr>
<tr>
<td valign="top">

integer

</td>
<td valign="top">

Yes

</td>
<td valign="top">

BIGINT

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

integer, format: int32

</td>
<td valign="top">

Yes

</td>
<td valign="top">

INTEGER

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

integer, format: int64

</td>
<td valign="top">

Yes

</td>
<td valign="top">

BIGINT

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

string

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

string, format: date

</td>
<td valign="top">

Yes

</td>
<td valign="top">

DATE

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

string, format: uuid

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(36\)

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

string, format: hostname

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

string, format: ipv4

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

string, format: ipv6

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

string, format: password

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Format annotation is ignored; treated as a plain string.

</td>
</tr>
<tr>
<td valign="top">

string, format: byte

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Format annotation is ignored; treated as a plain string.

</td>
</tr>
<tr>
<td valign="top">

string, format: time

</td>
<td valign="top">

No

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Will cause replication failure. Do not use.

</td>
</tr>
<tr>
<td valign="top">

string, format: timestamp

</td>
<td valign="top">

No

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

The format annotation is not enforced or validated by the runtime. Values are stored as plain strings with no format validation.

</td>
</tr>
<tr>
<td valign="top">

string with minLength/maxLength

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Can only be set by importing an OpenAPI schema. Values that don't meet the constraints are ignored during the replication.

</td>
</tr>
<tr>
<td valign="top">

boolean

</td>
<td valign="top">

Yes

</td>
<td valign="top">

BOOLEAN

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

array

</td>
<td valign="top">

No

</td>
<td valign="top">

\-

</td>
<td valign="top">

Simple array attributes are not replicated.

</td>
</tr>
</table>

