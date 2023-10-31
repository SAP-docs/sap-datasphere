<!-- loio5b27e03849fe4c7182bcb4274f010e90 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Allow a Space to Write to the Database User Group Schema

To grant a space write privileges in the database user group schema, use the GRANT\_PRIVILEGE\_TO\_SPACE stored procedure. Once this is done, data flows running in the space can select tables in the schema as targets and write data to them.



<a name="loio5b27e03849fe4c7182bcb4274f010e90__prereq_bgq_x5z_lqb"/>

## Prerequisites

Only the administrator of a database user group has the privilege to run the stored procedure "DWC\_GLOBAL"."GRANT\_PRIVILEGE\_TO\_SPACE".



<a name="loio5b27e03849fe4c7182bcb4274f010e90__context_ytz_psz_2sb"/>

## Context

You can grant write privileges by running an SAP Datasphere specific stored procedure in the SQL console in the SAP HANA Database Explorer.



<a name="loio5b27e03849fe4c7182bcb4274f010e90__steps_ztz_psz_2sb"/>

## Procedure

1.  From the side navigation area, go to <span class="FPA-icons"></span> *\(System\)* → <span class="FPA-icons"></span> \(*Configuration*\) → *Database Access*→ *Database User Groups*.

2.  Select the database user group and click *Open Database Explorer*.

3.  In the SQL console in SAP HANA Database Explorer, call the stored procedure to grant the 'INSERT', 'UPDATE', or 'DELETE' privilege to a space using the following syntax:

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
    
    \[required\] Enter 'GRANT' to give the write privileges, or 'REVOKE' to remove the write privileges to the space.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    privilege
    
    </td>
    <td valign="top">
    
    -   'INSERT"

    -   'UPDATE'

    -   'DELETE'



    
    </td>
    <td valign="top">
    
    \[required\] Enter the write privilege that you want to grant \(or revoke\) to the space.

    > ### Note:  
    > You can grant one privilege at a time.


    
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
    
    \[required\] Enter the name of the schema you want the space to be able to write from.
    
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
    
    \[required\] You can grant the write privileges, either at the schema level or at the object level.

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
    
    \[required\] Enter the ID of the space you are granting the write privileges to.
    
    </td>
    </tr>
    </table>
    
    To grant update write access to all objects \(tables\) in the schema:

    ```
    CALL "DWC_GLOBAL"."GRANT_PRIVILEGE_TO_SPACE" (
    	OPERATION => 'GRANT', 
    	PRIVILEGE => 'UPDATE', 
    	SCHEMA_NAME => 'SALE#ETL', 
    	OBJECT_NAME => '', 
    	SPACE_ID => 'SALES');
    
    
    
    ```

    To grant update write access to the table MY\_TABLE:

    ```
    CALL "DWC_GLOBAL"."GRANT_PRIVILEGE_TO_SPACE" (
    	OPERATION => 'GRANT', 
    	PRIVILEGE => 'UPDATE', 
    	SCHEMA_NAME => 'SALE#ETL', 
    	OBJECT_NAME => 'MY_TABLE', 
    	SPACE_ID => 'SALES');
    
    
    ```

4.  Run the query by clicking <span class="SAP-icons-watt"></span> \(Run\) or press F8.




<a name="loio5b27e03849fe4c7182bcb4274f010e90__result_sw1_vf5_p4b"/>

## Results

If the run is successful, you receive a confirmation message in the *Result* pane. You can then open the *Data Builder*, create a data flow, and select the tables as targets.

