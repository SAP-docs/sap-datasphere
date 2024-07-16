<!-- loio7eaa370fe4624dea9f182ee9c9ab645f -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Allow the Space to Access the Open SQL Schema

To grant the space write privileges in the Open SQL schema and the ability to write data to target tables in the schema, use the GRANT\_PRIVILEGE\_TO\_SPACE stored procedure. Once this is done, data flows running in the space can select tables in the Open SQL schema as targets and write data to them, and task chains can run procedures in the schema.



<a name="loio7eaa370fe4624dea9f182ee9c9ab645f__prereq_bgq_x5z_lqb"/>

## Prerequisites

Only the database user for the open SQL schema has the privilege to run the stored procedure "DWC\_GLOBAL"."GRANT\_PRIVILEGE\_TO\_SPACE".



<a name="loio7eaa370fe4624dea9f182ee9c9ab645f__context_odf_tdb_lqb"/>

## Context

You can grant write privileges by running an SAP Datasphere specific stored procedure in the SQL console in the SAP HANA Database Explorer.



<a name="loio7eaa370fe4624dea9f182ee9c9ab645f__steps_v32_wsc_lqb"/>

## Procedure

1.  In the side navigation area, click ![](images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.

2.  In the space page, go to *Database Access* \> *Database Users*, then select the database user and click *Open Database Explorer*.

3.  In the SQL console in SAP HANA Database Explorer, call the stored procedure to grant the ‘INSERT’, ‘UPDATE’, or ‘DELETE’ privilege to a space using the following syntax:

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
    
    -   'INSERT'

    -   'UPDATE'

    -   'DELETE'

    -   'EXECUTE'



    
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
    
    '\[name of the Open SQL schema\]'
    
    </td>
    <td valign="top">
    
    \[required\] Enter the name of the Open SQL Schema you want the space to be able to write into.
    
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

    To grant a space the ability to run procedures in the Open SQL schema:

    ```
    CALL "DWC_GLOBAL"."GRANT_PRIVILEGE_TO_SPACE" (
    	OPERATION => 'GRANT', 
    	PRIVILEGE => 'EXECUTE', 
    	SCHEMA_NAME => 'SALE#ETL', 
    	OBJECT_NAME => '', 
    	SPACE_ID => 'SALES');
    
    
    ```

    For more information on the SAP HANA statement CREATE PROCEDURE, see [CREATE PROCEDURE Statement \(Procedural\)](https://help.sap.com/docs/HANA_SERVICE_CF/7c78579ce9b14a669c1f3295b0d8ca16/20d467407519101484f190f545d54b24.html) in the *SAP HANA SQL Reference Guide for SAP HANA Platform*.

4.  Run the query by clicking <span class="SAP-icons-watt"></span> \(Run\) or press F8.




<a name="loio7eaa370fe4624dea9f182ee9c9ab645f__result_sw1_vf5_p4b"/>

## Results

If the run is successful, you receive a confirmation message in the *Result* pane. You can then open the *Data Builder*, create a data flow, and select the tables as targets.

