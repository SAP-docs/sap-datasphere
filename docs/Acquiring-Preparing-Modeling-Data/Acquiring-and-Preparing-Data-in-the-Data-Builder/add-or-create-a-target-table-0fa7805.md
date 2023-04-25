<!-- loio0fa780568975458dbd90d11d1d81f2d9 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add or Create a Target Table

Add a target table to write data to. You can only have one target table in a data flow.



## Procedure

1.  Add a target table to the data flow in one of the following ways:

    -   Click <span class="FPA-icons"></span> \(Add Table\) in the toolbar, and drag and drop it onto the canvas to create a new target table

        The target table is added to your data flow. The text **New** at the bottom-right of the operator shows that the table is newly added.

    -   Drag an existing table from the *Source Browser*, drop it onto the canvas, and click the floating *Target* button to use it as the target table. You can choose:
        -   On the *Repository* tab - A local table.
        -   On the *Sources* tab:
            -   A table in an Open SQL schema - if the space is granted write access to the table or schema \(see [Allow the Space to Write to the Open SQL Schema](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/7eaa370fe4624dea9f182ee9c9ab645f.html "To grant the space write privileges in the Open SQL schema, use the GRANT_PRIVILEGE_TO_SPACE stored procedure. Once this is done, data flows running in the space can select tables in the Open SQL schema as targets and write data to them.") :arrow_upper_right:\).
            -   A table in a database user group schema - if the space is granted write access to the table or schema \(see [Allow a Space to Write to the Database User Group Schema](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/5b27e03849fe4c7182bcb4274f010e90.html "To grant a space write privileges in the database user group schema, use the GRANT_PRIVILEGE_TO_SPACE stored procedure. Once this is done, data flows running in the space can select tables in the schema as targets and write data to them.") :arrow_upper_right:\).
            -   A table in an SAP HDI container - if the space is granted write access to the table or schema \(see [Allow Your Space to Write to Your HDI Container](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/aa3627f987d04b5f95fec1c45083dde9.html "To allow data flows in your SAP Datasphere space to use tables in your HDI container as targets, you must set the appropriate roles and add the container to your space.") :arrow_upper_right:\).



2.  Click and drag the port on the right of the last operator in your data flow and drop it onto the target table.

    A flow is created between the operator and the target table.

3.  Click the target node to display its properties in the side panel, and complete the properties in the *General* section:


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

    Label


    
    </td>
    <td valign="top">

    Enter a label to display in the target table symbol.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Business Name / Technical Name / Type / Connection


    
    </td>
    <td valign="top">

    \[read-only\] Provide information to identify the target table.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Mode


    
    </td>
    <td valign="top">

    Specifies the mode with which to write to the target table or modify the data in the target table.

    You can choose between:

    -   *Append*: Write the data obtained from the data flow as new records appended to the end of the target table.
    -   *Truncate*: Erase the existing data in the target table and replace it with the data obtained from the data flow.
    -   *Delete*: Delete records in the target table based on the columns mapped in the target. All the column mappings are considered for the match condition and if the value of these columns match the record in the target table, the record will be deleted.

        > ### Restriction:  
        > The *Delete* mode fails for a target table when a mapped column contains NULL values.



    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Update Records By Primary Key \(UPSERT\)


    
    </td>
    <td valign="top">

    \[*Append* mode\] Instructs the flow to update, where appropriate, existing target table records that can be identified by their primary keys.

    If this option is not selected then all source records \(including those that are already present in the target table\) are appended, which may cause duplicate key errors.

    > ### Note:  
    > If no primary key is defined in the target table, then all records will be appended.

    This feature is based on the UPSERT statement \(see [Upsert](https://help.sap.com/viewer/a4ae14a90e33416a90edc658d94a5c06/Cloud/en-US/972f970f9c0942d89c528f8ecc5a4977.html) in the *SQL Reference for SAP Vora in SAP Data Intelligence* guide\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Status


    
    </td>
    <td valign="top">

     \[read-only\] Displays the deployment and error status of the object. 

    For more information, see [Saving and Deploying Objects](../Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Use As


    
    </td>
    <td valign="top">

    Specifies whether the table is used as a *Source* or *Target* in the data flow.

    > ### Note:  
    > Changing the use of a table will reset all its properties.


    
    </td>
    </tr>
    </table>
    
4.  In the *Mappings* section, review the mappings of incoming columns to the target table columns.

    -   When you connect any operator to the target table, each incoming columns that has the same name and a compatible data type with a column in the target table is automatically mapped to it.

    -   You can manually map an incoming columns with a target table column that has a compatible datatype by dragging the column from the left list and dropping it onto the appropriate column in the right list.

    -   To delete a mapping, select it, and click *Delete*. To delete all mappings, *Remove all Mappings.*

    -   You can, at any time, click <span class="FPA-icons"></span> \(Auto Map\) to relaunch automapping based on names and datatypes.


5.  In the *Columns* section, view the columns of the target table. To check the data type of a column, hover over it and click <span class="FPA-icons"></span>.

6.  \[optional\] In the *Advanced* section, configure the following properties:


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

    Control Batch Size


    
    </td>
    <td valign="top">

    To enforce a specific value for Batch Size, toggle this switch.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Batch Size \(Number of Rows\)


    
    </td>
    <td valign="top">

    Specifies the amount of data being read. That is, it indicates the number of rows that will be fetched from the source in each request.


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > You can click the icon *Restore Default* to restore the default settings.

7.  Click *Create and Deploy Table* in the properties panel to create and deploy the newly added target table to the repository in your space.

    This step is not necessary if you added an existing table.


