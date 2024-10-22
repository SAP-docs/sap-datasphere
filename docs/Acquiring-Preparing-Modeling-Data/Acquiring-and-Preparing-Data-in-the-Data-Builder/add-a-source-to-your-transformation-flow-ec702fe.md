<!-- loioec702fe3b1134f278c5c538b447b7435 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add a Source to Your Transformation Flow

Add a source to your transformation flow to read data from.



<a name="loioec702fe3b1134f278c5c538b447b7435__steps_xpb_dqj_lyb"/>

## Procedure

1.  Navigate to the *Graphical View Editor*.

2.  Browse or search for the object you want to add on either of the tabs.

    -   The *Repository* tab lists all the tables and views that are available in the space.
    -   The *Sources* tab lists all the Open SQL schemas that have been integrated to the space from which you can import tables and views. Each Open SQL schema appears as a root node in this tab \(see [Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/3de55a78a4614deda589633baea28645.html "Create a database user in your space to read and write directly to the SAP HANA Cloud database on which SAP Datasphere runs. Each database user has an Open SQL schema, which is attached to a space schema and provides a secure method for exchanging data with the space.") :arrow_upper_right:\).

3.  Drag a table from the relevant tab and drop it onto the diagram.

4.  If the source is a view containing one or more input parameters, the *Map Input Parameters* dialog is displayed, and you can enter a value to resolve the input parameter.

    You can click*Cancel* in the dialog and do not specify a value to resolve the input parameter, an error is displayed on the source, and you must subsequently specify a value in the source side panel *Input Parameters* section.

5.  Click the source node to display its properties in the side panel, and review the properties in the *General* section:

    ****


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
    
    Business Name / Technical Name
    
    </td>
    <td valign="top">
    
    Information to identify the source object.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Alias
    
    </td>
    <td valign="top">
    
    You can specify an SQL alias for the source object if required.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Distinct Values
    
    </td>
    <td valign="top">
    
    Indicates whether the source object uses SELECT DISTINCT statements to return only distinct values.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delta Capture
    
    </td>
    <td valign="top">
    
    Indicates whether the delta capture setting is enabled for a table. For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delta Capture Table Name
    
    </td>
    <td valign="top">
    
    Display the default name for the delta capture table \(Technical name + Delta\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    The deployment and error status of the object. For more information, see [Saving and Deploying Objects](../saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delta Capture Settings
    
    </td>
    <td valign="top">
    
    Indicates how you want to load the records from the table:

    -   Delta capture: You want to load the delta changes to the target table.
    -   All active records: You want to load the active records to the target table: It excludes both the delta capture columns and records marked as deleted.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Input Parameters
    
    </td>
    <td valign="top">
    
    If the source contains input parameters, you can view them here.
    
    </td>
    </tr>
    </table>
    
    **Additional Information About Loading Delta Changes**

    To load delta changes from a source table \(including deleted records\), the delta capture setting must be enabled for the table. It is only possible to load delta changes from one source table. If you want to load delta changes from a source table, you need to ensure that the value of the option *Delta Capture* is *On* for both the source table and for the target table. In the *Transformation Flow Properties* panel, ensure that the load type *Initial and Delta* is selected.

6.  In the *Columns* section, you can view the columns of the source table. To check the data type of a column, hover over it and click <span class="FPA-icons-V3"></span>.

    If the delta capture setting is enabled for a table, two additional columns are present in the table to track changes. For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).

    > ### Note:  
    > If the delta capture setting is enabled for a source table, the columns *Change Date* and *Change Type* are automatically mapped to these columns in the target table. Mapping these columns \(or a calculated column that contains the content of these columns\) to any other target column is not permitted. For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).

    > ### Note:  
    > The *Change Type* column does not support null values. Ensure that no null values are written to the *Change Type* column of the target table.
    > 
    > **Example**
    > 
    > You add two source tables. The delta capture setting is enabled for one table and disabled for the other. You create a union for these two tables. In the target table, the *Change Type* column will contain null values. In this case, running the transformation flow will result in errors.


