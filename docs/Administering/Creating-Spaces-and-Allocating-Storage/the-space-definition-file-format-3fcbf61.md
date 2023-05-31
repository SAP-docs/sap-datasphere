<!-- loio3fcbf619f2774b849fa7df58163b3609 -->

# The Space Definition File Format

Space properties are set and retrieved in the space definition file format and stored as a `.json` file.

A space definition file must not exceed 25MB, and can contain the following space information:

-   [Space Properties](the-space-definition-file-format-3fcbf61.md#loio3fcbf619f2774b849fa7df58163b3609__section_space_properties)
-   [Members](the-space-definition-file-format-3fcbf61.md#loio3fcbf619f2774b849fa7df58163b3609__section_members)
-   [Database Users](the-space-definition-file-format-3fcbf61.md#loio3fcbf619f2774b849fa7df58163b3609__section_database_users)
-   [HDI Containers](the-space-definition-file-format-3fcbf61.md#loio3fcbf619f2774b849fa7df58163b3609__section_hdi_containers)
-   [Table, View, and Data Access Control Definitions](the-space-definition-file-format-3fcbf61.md#loio3fcbf619f2774b849fa7df58163b3609__section_entity_definitions)



<a name="loio3fcbf619f2774b849fa7df58163b3609__section_space_properties"/>

## Space Properties

Users with the *DW Administrator* role can create spaces and set any space properties \(see [Create a Space](create-a-space-bbd41b8.md)\) using the following syntax:

```
{
  "<SPACE_ID>": {
    "spaceDefinition": {
      "version": "1.0.4",
      "label": "<Space_Name>",
      "assignedStorage": <bytes>,
      "assignedRam": <bytes>,
      "priority": <value>,
      "injection": {
        "dppRead": {
          "retentionPeriod": <days>,
          "isAuditPolicyActive": true|false
        },
        "dppChange": {
          "retentionPeriod": <days>,
          "isAuditPolicyActive": true|false
        }
      },
      "allowConsumption": true|false,
      "enableDataLake": true|false,
      "members": [],
      "dbusers": {},
      "hdicontainers": {},
      "workloadClass": {
        "totalStatementMemoryLimit": {
          "value": 0,
          "unit": "Gigabyte|Percent"
        },
        "totalStatementThreadLimit": {
          "value": 0,
          "unit": "Counter|Percent"

    }
  }
}
```

> ### Note:  
> Users with the *DW Space Administrator* role cannot create spaces, but they can set space properties except `SPACE_ID`, `assignedStorage`, `assignedRam`, and `priority`.

Parameters are set as follows:


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

Space Property



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*<SPACE\_ID\>*



</td>
<td valign="top">

Space ID



</td>
<td valign="top">

\[required\] Enter the technical name of the space. Can contain a maximum of 20 uppercase letters or numbers and must not contain spaces or special characters other than `_` \(underscore\). Unless advised to do so, must not contain prefix \_SYS and should not contain prefixes: DWC\_, SAP\_ \(See [Rules for Technical Names](rules-for-technical-names-982f9a3.md)\).



</td>
</tr>
<tr>
<td valign="top">

`version`



</td>
<td valign="top">

\-



</td>
<td valign="top">

\[required\] Enter the version of the space definition file fomat. This must always be set to `1.0.4`.



</td>
</tr>
<tr>
<td valign="top">

`label`



</td>
<td valign="top">

Space Name



</td>
<td valign="top">

Enter the business name of the space. Can contain a maximum of 30 characters, and can contain spaces and special characters.

Default value: *<Space\_ID\>*



</td>
</tr>
<tr>
<td valign="top">

`assignedStorage`



</td>
<td valign="top">

Disk \(GB\)



</td>
<td valign="top">

Enter the amount of storage allocated to the space in bytes. You can enter any value between `100000` bytes \(100MB\) and the total storage size available in the tenant.

Default value: `2000000000` bytes \(2GB\)

> ### Note:  
> To set no size limit for the space \(and disable the *Enable Space Quota* option\), enter `0` for both this parameter and `assignedRam`.



</td>
</tr>
<tr>
<td valign="top">

`assignedRam`



</td>
<td valign="top">

In-Memory \(GB\)



</td>
<td valign="top">

Enter the amount of ram allocated to the space in bytes. You can enter any value between `100000` bytes \(100MB\) and the total storage size available in the tenant.

Default value: `1000000000` bytes \(1GB\)



</td>
</tr>
<tr>
<td valign="top">

`Priority`



</td>
<td valign="top">

Space Priority



</td>
<td valign="top">

Enter the prioritization of this space when querying the database. You can enter a value from 1 \(lowest priority\) to 8 \(highest priority\).

Default value: `5`



</td>
</tr>
<tr>
<td valign="top">

`dppRead.isAuditPolicyActive`

`dppRead.retentionPeriod`

`dppChange.isAuditPolicyActive`

`dppChange.retentionPeriod`



</td>
<td valign="top">

Enable Audit Log for Read Operations

Keep Logs for *<n\>* Days

Enable Audit Log for Change Operations

Keep Logs for *<n\>* Days



</td>
<td valign="top">

Enter the audit logging policy for read and change operations and the number of days that the logs are retained. you can retain logs for any period between `7` and `10000` days.

Default values: `false`, `30`, `false`, `30`



</td>
</tr>
<tr>
<td valign="top">

`allowConsumption`



</td>
<td valign="top">

Expose for Consumption by Default



</td>
<td valign="top">

Choose the default setting for the *Expose for Consumption* property for views created in this space.

Default value: `false`



</td>
</tr>
<tr>
<td valign="top">

`enableDataLake`



</td>
<td valign="top">

Use This Space to Access the Data Lake



</td>
<td valign="top">

Enable access to the SAP HANA Cloud data lake. Enabling this option is only possible if no other space already has access to the data lake.

Default value: `false`



</td>
</tr>
<tr>
<td valign="top">

`members`



</td>
<td valign="top">

Member Assignment



</td>
<td valign="top">

See [Members](the-space-definition-file-format-3fcbf61.md#loio3fcbf619f2774b849fa7df58163b3609__section_members).



</td>
</tr>
<tr>
<td valign="top">

`dbusers`



</td>
<td valign="top">

Database Users



</td>
<td valign="top">

See [Database Users](the-space-definition-file-format-3fcbf61.md#loio3fcbf619f2774b849fa7df58163b3609__section_database_users).



</td>
</tr>
<tr>
<td valign="top">

`hdicontainers`



</td>
<td valign="top">

HDI Containers



</td>
<td valign="top">

See [HDI Containers](the-space-definition-file-format-3fcbf61.md#loio3fcbf619f2774b849fa7df58163b3609__section_hdi_containers).



</td>
</tr>
<tr>
<td valign="top">

`workloadClass.totalStatementMemoryLimit.value`

`workloadClass.totalStatementMemoryLimit.unit`



</td>
<td valign="top">

Total Statement Memory Limit

GB/%



</td>
<td valign="top">

Enter the maximum number \(or percentage\) of GBs of memory that statements running concurrently in the space can consume. You can enter any value or percentage between 0 \(no limit\) and the total amount of memory available in your tenant.

Default values: `0`, `Gigabyte`



</td>
</tr>
<tr>
<td valign="top">

`workloadClass.totalStatementThreadLimit.value`

`workloadClass.totalStatementThreadLimit.unit`



</td>
<td valign="top">

Total Statement Thread Limit

Threads/%



</td>
<td valign="top">

Enter the maximum number \(or percentage\) of threads that statements running concurrently in the space can consume. You can enter any value or percentage between 0 \(no limit\) and the total number of threads available in your tenant.

Default values: `0`, `Counter`



</td>
</tr>
</table>

For example, the following file will create a new space, with all default properties:

```
{
  "NEWSPACE": {
    "spaceDefinition": {
      "version": "1.0.4"
    } 
  } 
}
```

> ### Note:  
> If a property is not set it will receive the default value \(on creation\) or will keep its current value \(on update\).

This second file will update `NEWSPACE` by modifying the *Space Name* and increasing the *Disk \(GB\)* and *In-Memory \(GB\)* allocations:

```
{
  "NEWSPACE": {
    "spaceDefinition": {
      "version": "1.0.4",
      "label": "My New Space",
      "assignedStorage": 6000000000,
      "assignedRam": 5000000000
    } 
  } 
}
```

This third file will update the *Space Priority*, and will leave the other parameters as previously set:

```
{
  "NEWSPACE": {
    "spaceDefinition": {
      "version": "1.0.4",
      "priority": 4
    } 
  } 
}
```

> ### Note:  
> The following properties are not supported when creating, reading, or updating spaces using `dwc`:
> 
> -   *Connections*
> -   *Time Data*
> -   *Space Status* and other run-time properties



<a name="loio3fcbf619f2774b849fa7df58163b3609__section_members"/>

## Members

Users with the *DW Administrator* or *DW Space Administrator* role can add members to a space \(see [Assign Members to Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/9d59fe511ae644d98384897443054c16.html "As a Space Administrator, you can assign users as members of your space.") :arrow_upper_right:\) using the following syntax:

```
{
  ...
  "members":[
    {
      "name":"<User_ID>",
      "type":"user"
    }
  ]
}
```

Parameters are set as follows:


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

Space Property



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*<name\>*



</td>
<td valign="top">

*Member*



</td>
<td valign="top">

\[required\] Enter a user ID recognized by your identity provider.

> ### Note:  
> All members added to your space must already be registered as users of SAP Datasphere.



</td>
</tr>
<tr>
<td valign="top">

`type`



</td>
<td valign="top">

\-



</td>
<td valign="top">

\[required\] Enter the type of the member. This must always be set to `user`.



</td>
</tr>
</table>

For example, the following file will add three members to `NEWSPACE`:

```
{
  "NEWSPACE": {
    "spaceDefinition": {
      "version": "1.0.4",
      "members": [
        {
          "name": "jennifer.jones@sap.com",
          "type": "user"
        },
        {
          "name": "bobby.brown@sap.com",
          "type": "user"
        },
        {
          "name": "peter.parker@sap.com",
          "type": "user"
        }
      ]
    } 
  } 
}
```

When updating space members via `dwc`, you must always list all members that you want to have assigned to the space. This second file will add two new members and remove `peter.parker@sap.com`:

```
{
  "NEWSPACE": {
    "spaceDefinition": {
      "version": "1.0.4",
      "members": [
        {
          "name": "jennifer.jones@sap.com",
          "type": "user"
        },
        {
          "name": "bobby.brown@sap.com",
          "type": "user"
        },
        {
          "name": "tim.taylor@sap.com",
          "type": "user"
        },
        {
          "name": "andy.anderson@sap.com",
          "type": "user"
        }
      ]
    } 
  } 
}
```



<a name="loio3fcbf619f2774b849fa7df58163b3609__section_database_users"/>

## Database Users

Users with the *DW Administrator*, *DW Space Administrator*, or *DW Integrator* role can add database users to a space \(see [Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/3de55a78a4614deda589633baea28645.html "Create a database user in your space to read and write directly to the SAP HANA Cloud database on which SAP Datasphere runs. Each database user has an Open SQL schema, which is attached to a space schema and provides a secure method for exchanging data with the space.") :arrow_upper_right:\) using the following syntax:

```
{
  ...
  "dbusers":{
    "<Space_ID>#<DB_UserName>":{
      "ingestion":{
        "auditing":{
          "dppRead":{
            "retentionPeriod":<days>
            "isAuditPolicyActive":false
          },
          "dppChange":{
            "retentionPeriod":<days>
            "isAuditPolicyActive":false
          }
        }
      },
      "consumption":{
        "consumptionWithGrant":false,
        "spaceSchemaAccess":false,
        "scriptServerAccess":false,
        "localSchemaAccess":false,
        "hdiGrantorForCupsAccess":false
      }
    }
  }
}
```

Parameters are set as follows:


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

Space Property



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*<SPACE\_ID\>*



</td>
<td valign="top">

*Space ID*



</td>
<td valign="top">

\[required\] Must be the same as the *<Space\_ID\>* used at the root of the space definition file.



</td>
</tr>
<tr>
<td valign="top">

*<DB\_UserName\>*



</td>
<td valign="top">

*Database User Name Suffix*



</td>
<td valign="top">

\[required\] Enter the name of the database user. Can contain a maximum of 20 uppercase letters or numbers and must not contain spaces or special characters other than `_` \(underscore\).



</td>
</tr>
<tr>
<td valign="top">

`ingestion.auditing.dppRead.isAuditPolicyActive`

`ingestion.auditing.dppRead.retentionPeriod`

`ingestion.auditing.dppChange.isAuditPolicyActive`

`ingestion.auditing.dppChange.retentionPeriod`



</td>
<td valign="top">

Enable Audit Log for Read Operations

Keep Logs for *<n\>* Days

Enable Audit Log for Change Operations

Keep Logs for *<n\>* Days



</td>
<td valign="top">

Enter the audit logging policy for read and change operations and the number of days that the logs are retained. you can retain logs for any period between `7` and `10000` days.

Default values: `false`, `30`, `false`, `30`



</td>
</tr>
<tr>
<td valign="top">

`consumption.consumptionWithGrant`



</td>
<td valign="top">

*With Grant Option*



</td>
<td valign="top">

Allow the database user to grant read access to the space schema to other users.

Default value: `false`



</td>
</tr>
<tr>
<td valign="top">

`consumption.spaceSchemaAccess`



</td>
<td valign="top">

*Enable Read Access \(SQL\)*



</td>
<td valign="top">

Grant the database user read access to the space schema.

Default value: `false`



</td>
</tr>
<tr>
<td valign="top">

`consumption.scriptServerAccess`



</td>
<td valign="top">

*Enable Automated Predictive Library \(APL\) and Predictive Analysis Library \(PAL*



</td>
<td valign="top">

Grant the database user access to the SAP HANA Cloud machine learning libraries.

Default value: `false`



</td>
</tr>
<tr>
<td valign="top">

`consumption.localSchemaAccess`



</td>
<td valign="top">

*Enable Write Access \(SQL, DDL, & DML\)*



</td>
<td valign="top">

Grant the database user write access to the OpenSQL schema.

Default value: `false`



</td>
</tr>
<tr>
<td valign="top">

`consumption.hdiGrantorForCupsAccess`



</td>
<td valign="top">

*Enable HDI Consumption*



</td>
<td valign="top">

Grant the database user read access to HDI containers associated with the space.

Default value: `false`



</td>
</tr>
</table>

For example, the following file will add a database user to `NEWSPACE`:

```
{
  "NEWSPACE": {
    "spaceDefinition": {
      "version": "1.0.4",
      "dbusers": {
        "MYSPACE#JJONES": {
          "ingestion": {
            "auditing": {
              "dppRead": {
                "retentionPeriod": 21,
                "isAuditPolicyActive": true
              }
            }           
          },
          "consumption": {
            "consumptionWithGrant": true,
            "spaceSchemaAccess": true,
            "scriptServerAccess": true,
            "localSchemaAccess": true,
            "hdiGrantorForCupsAccess": true
          }
        }
      }
    } 
  } 
}
```

> ### Note:  
> You can use the `dwc dbusers password reset` command to obtain a new password for a database user \(see[Manage Spaces via the Command Line](manage-spaces-via-the-command-line-5eac5b7.md)\).



<a name="loio3fcbf619f2774b849fa7df58163b3609__section_hdi_containers"/>

## HDI Containers

Users with the *DW Administrator*, *DW Space Administrator*, or *DW Integrator* role can associate HDI containers to a space \(see [Exchanging Data with SAP SQL Data Warehousing HDI Containers](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/1aec7ca95af24208a61c1a444b249d95.html "You can enable SAP SQL Data Warehousing on your SAP Datasphere tenant to exchange data between your HDI containers and your SAP Datasphere spaces without the need for data movement.") :arrow_upper_right:\) using the following syntax:

```
{
  ...
  "hdicontainers":{
    "<Container_Name>":{}
    },

```

Parameters are set as follows:


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

Space Property



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*<Container\_Name\>*



</td>
<td valign="top">

*HDI Container Name*



</td>
<td valign="top">

\[required\] Enter the name of an HDI container that is associated with your SAP Datasphere instance and which is not assigned to any other space.



</td>
</tr>
</table>

For example, the following file will associate two HDB containers to `NEWSPACE`:

```
{
  "NEWSPACE": {
    "spaceDefinition": {
      "version": "1.0.4",
      "hdicontainers": {
        "MyHDIContainer": {},
        "MyOtherContainer": {},
      } 
    } 
  } 
}
```



<a name="loio3fcbf619f2774b849fa7df58163b3609__section_entity_definitions"/>

## Table, View, and Data Access Control Definitions

Users with the *DW Administrator* or *DW Space Administrator* role can add tables and views, and data access controls to a space using the standard CSN syntax \(see [Core Data Services Schema Notation \(CSN\)](https://cap.cloud.sap/docs/cds/csn#entity-definitions)\). Users with the *DW Modeler* role can add tables and views.

For example, the following file will create a table with two columns in `NEWSPACE`:

```
{
  "NEWSPACE": {
    "spaceDefinition": {
      "version": "1.0.4"
    },
    "definitions": {
      "Products": {
        "kind": "entity",
        "elements": {
          "Product ID": {
            "type": "cds.Integer64",
            "key": true,
            "notNull": true
          },
          "Product Name": {
            "type": "cds.String",
            "length": 5000
          }
        }
      }
    }
  }
}
```

> ### Note:  
> To obtain more complex examples, read existing objects from a space into a file using the `-D` option \(see [Read a Space](manage-spaces-via-the-command-line-5eac5b7.md#loio5eac5b71e2d34c32b63f3d8d47a0b1d0__section_read_a_space)\).

