<!-- loio44021ca7d63b44e9b71cc4afa66d7c9e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Allow a Space to Read From the Database User Group Schema

By default, no SAP Datasphere space can access the database user group schema. To grant a space read privileges from the database user group schema, use the GRANT\_PRIVILEGE\_TO\_SPACE stored procedure.



<a name="loio44021ca7d63b44e9b71cc4afa66d7c9e__prereq_bgq_x5z_lqb"/>

## Prerequisites

To allow a space to read from the database user group schema, you must have a database user group administrator and a password \([Creating a Database User Group](creating-a-database-user-group-1097a47.md)\).



## Context

You can grant read privileges by running an SAP Datasphere specific stored procedure in the SQL console in the SAP HANA Database Explorer.



## Procedure

1.  From the side navigation area, go to <span class="FPA-icons-V3"></span> *\(System\)* → <span class="FPA-icons-V3"></span> \(*Configuration*\) → *Database Access*→ *Database User Groups*.

2.  Select the database user group and click *Open Database Explorer*.

3.  In the SQL console in SAP HANA Database Explorer, call the stored procedure to grant the 'SELECT' privilege to a space using the following syntax:

    ```
    CALL "DWC_GLOBAL"."GRANT_PRIVILEGE_TO_SPACE" (
    	OPERATION => <operation>, 
    	PRIVILEGE => <privilege>, 
    	SCHEMA_NAME => <schema name>, 
    	OBJECT_NAME => <object name>, 
    SPACE_ID => <space ID>);
    
    
    ```

    Parameters are set as follows:


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Values
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    operation
    
    </td>
    <td valign="top">
    
    -   'GRANT'

    -   'REVOKE'



    
    </td>
    <td valign="top">
    
    \[required\] Enter 'GRANT' to give the read privileges, or 'REVOKE' to remove the read privileges to the space.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    privilege
    
    </td>
    <td valign="top">
    
    'SELECT'
    
    </td>
    <td valign="top">
    
    \[required\] Enter the read privilege that you want to grant \(or revoke\) to the space.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    schema\_name
    
    </td>
    <td valign="top">
    
    '\[name of database user group schema\]'
    
    </td>
    <td valign="top">
    
    \[required\] Enter the name of the schema you want the space to be able to read from.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    object\_name
    
    </td>
    <td valign="top">
    
    -   ' '

    -   null

    -   '\[name of the objet\]'



    
    </td>
    <td valign="top">
    
    \[required\] You can grant the read privileges, either at the schema level or at the object level.

    -   At the schema level \(all objets in the schema\): enter null or ' '.

    -   At the object level: enter a valid table name.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    space\_id
    
    </td>
    <td valign="top">
    
    '\[ID of the space\]'
    
    </td>
    <td valign="top">
    
    \[required\] Enter the ID of the space you are granting the read privileges to.
    
    </td>
    </tr>
    </table>
    
    To grant read access to all objects \(tables\) in the schema:

    ```
    CALL "DWC_GLOBAL"."GRANT_PRIVILEGE_TO_SPACE" (
    	OPERATION => 'GRANT', 
    	PRIVILEGE => 'SELECT', 
    	SCHEMA_NAME => 'SALE#ETL', 
    	OBJECT_NAME => '', 
    	SPACE_ID => 'SALES');
    
    
    
    ```

    To grant read access to the table MY\_TABLE:

    ```
    CALL "DWC_GLOBAL"."GRANT_PRIVILEGE_TO_SPACE" (
    	OPERATION => 'GRANT', 
    	PRIVILEGE => 'SELECT', 
    	SCHEMA_NAME => 'SALE#ETL', 
    	OBJECT_NAME => 'MY_TABLE', 
    	SPACE_ID => 'SALES');
    
    
    ```

4.  Run the query by clicking <span class="SAP-icons-watt"></span> \(Run\) or press F8.




<a name="loio44021ca7d63b44e9b71cc4afa66d7c9e__result_sw1_vf5_p4b"/>

## Results

If the run is successful, you receive a confirmation message in the *Result* pane. You can then open the *Data Builder*, create a data flow, and select the tables as sources.

