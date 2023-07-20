<!-- loioa94e1637db484a5c8ec2da83cfa75156 -->

# Prepare Your HDI Project for Exchanging Data with Your Space

To allow your SAP Datasphere space to read from and, if appropriate, write to the HDI container, you must configure your HDI project to build on your SAP Datasphere tenant and define the appropriate roles.



<a name="loioa94e1637db484a5c8ec2da83cfa75156__steps_jk3_ybq_5sb"/>

## Procedure

1.  Create the required roles to allow SAP Datasphere to read from and, optionally, write to the container.

    You must define the roles `DWC_CONSUMPTION_ROLE` and `DWC_CONSUMPTION_ROLE#` \(with grant option\) in the container to allow you to add it to your space and allow you to exchange data between the container and the space.

    The contents of the roles define the HDI objects that can be read from or written to. You can allow access to individual objects or to all the objects in the container.

    These examples show roles that provide read access to individual objects or to all objects in the container:


    <table>
    <tr>
    <th valign="top">

    Read Access to Individual Objects


    
    </th>
    <th valign="top">

    Read Access to the Schema


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    This example provides read access to one table and one view in the container:

    ```
    {
      "role": {
        "name": "DWC_CONSUMPTION_ROLE",
        "object_privileges": [
          {
            "name":"MyNamespace::Table1",
            "type":"TABLE",
            "privileges":[ "SELECT" ]
          },
          {
            "name":"MyNamespace::CalcView1",
            "type":"VIEW",
            "privileges":[ "SELECT" ]
          }     
        ]
     }
    }
    ```


    
    </td>
    <td valign="top">
    
    This example provides read access to all the objects in the container:

    ```
    {
      "role": {
        "name": "DWC_CONSUMPTION_ROLE",
        "schema_privileges": [
          {
            "privileges":[ "SELECT" ]
          }
        ]
     }
    }
    ```


    
    </td>
    </tr>
    </table>
    
    To allow data flows in your space to write to the container you must, in addition, define the roles `DWC_WRITE_ROLE` and `DWC_WRITE_ROLE#`.

    These examples show roles that provide write access to individual objects or to all objects in the container:


    <table>
    <tr>
    <th valign="top">

    Write Access to Individual Objects


    
    </th>
    <th valign="top">

    Write Access to the Schema


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    This example provides write access to two tables in the container:

    ```
    {
      "role": {
        "name": "DWC_WRITE_ROLE",
        "object_privileges": [
          {
            "name":"MyNamespace::Table1",
            "type":"TABLE",
            "privileges":[ "SELECT", "INSERT", "UPDATE", "DELETE" ]
          },
          {
            "name":"MyNamespace::Table2",
            "type":"TABLE",
            "privileges":[ "SELECT" ]
          }     
        ]
     }
    }
    ```


    
    </td>
    <td valign="top">
    
    This example provides write access to all the objects in the container:

    ```
    {
      "role": {
        "name": "DWC_WRITE_ROLE",
        "schema_privileges": [
          {
            "privileges":[ "SELECT", "INSERT", "UPDATE", "DELETE" ]
          }
        ]
     }
    }
    ```


    
    </td>
    </tr>
    </table>
    
    For detailed information about hdbroles, see [Roles \(.hdbrole and .hdbroleconfig\)](https://help.sap.com/viewer/3823b0f33420468ba5f1cf7f59bd6bd9/latest/en-US/625d7733c30b4666b4a522d7fa68a550.html) in the *SAP HANA Platform* documentation.

2.  Configure your *Cloud Foundry Settings* to build to your SAP Datasphere tenant.

3.  Edit your `mta.yaml` file to reference the database id of your SAP Datasphere tenant, your HDI container, and the name of your user-provided service instance \(see [Access Space Objects in Your HDI Container](access-space-objects-in-your-hdi-container-656eebc.md)\).

4.  Build your database module.

    Once the build is complete, the HDI container is available to be added to your SAP Datasphere space \(see [Add an HDI Container and Access its Objects in Your Space](add-an-hdi-container-and-access-its-objects-in-your-s-5d55da5.md)\).


