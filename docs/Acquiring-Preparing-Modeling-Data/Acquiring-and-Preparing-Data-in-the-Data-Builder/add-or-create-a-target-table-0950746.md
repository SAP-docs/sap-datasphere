<!-- loio0950746ab4444e5ca6a665ee1b0380a1 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add or Create a Target Table

A transformation flow writes data to a target table. You can create a new target table or use an existing one.



## Procedure

1.  Add a target table to the transformation flow in one of the following ways:

    -   Click the *Create New Table* button.

        The target table is added to your transformation flow, and the *Properties* panel for the table appears. Enter a business name and a technical name for your target table. When you enter a business name, the system automatically suggests a corresponding technical name, but you can change the technical name if required.

    -   Drag an existing table from the *Repository*, and drop it onto the *Target* node.


    > ### Note:  
    > If the load type of the transformation flow is *Initial and Delta* and you change the target table, only delta data will be transferred to the new target table. If you want to transfer all data to the target table, you can reset the watermark in the *Data Integration Monitor*. For more information, see [Watermarks](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/890897f00a4944c7a6f90d3816a8d4c6.html "") :arrow_upper_right:.

2.  Click the target node to display its properties in the side panel, and review the properties in the *General* section:


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
    
    Information to identify the target table.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    The deployment and error status of the object. For more information, see [Saving and Deploying Objects](../Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Truncate
    
    </td>
    <td valign="top">
    
    If the value of the *Truncate* option is *Yes*, when you start the transformation flow, the system deletes the table content, but leaves the table structure intact and fills it with the relevant data from the source table.

    If not, the system inserts new data records after the existing data in the target table. For data records that already exist in the target table and have been changed in the source, the system updates the target records with the changed data from the source using the UPSERT mode. Note that the system will only update such target records if the target table has a primary key column.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delta Capture
    
    </td>
    <td valign="top">
    
    Indicates whether the delta capture setting is enabled for the table. For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delta Capture Table Name
    
    </td>
    <td valign="top">
    
    \[read-only\] The delta capture table name. The system displays this field if the delta capture setting is enabled for the table. For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).
    
    </td>
    </tr>
    </table>
    
3.  In the *Mappings* section, review the mappings of incoming columns to the target table columns.

    -   When you connect any operator to the target table, each incoming column that has the same name and a compatible data type with a column in the target table is automatically mapped to it.

    -   You can manually map an incoming columns with a target table column that has a compatible datatype by dragging the column from the left list and dropping it onto the appropriate column in the right list.

        > ### Note:  
        > For the data type "string", incoming columns and target table columns do not need to be the same length. It is possible to map incoming columns to target table columns that have a greater length.

    -   To delete a mapping, select it, and click *Delete*. To delete all mappings, *Remove all Mappings.*

    -   You can, at any time, click <span class="FPA-icons-V3"></span> \(Auto Map\) to relaunch automapping based on names and datatypes.


    > ### Note:  
    > If the delta capture setting is enabled for the target table of a transformation flow, the *Change Date* column of the target table will always contain the time that the transformation flow was run, even if an incoming column is mapped to the *Change Date* column.

4.  In the *Columns* section, view the columns of the target table. To check the data type of a column, hover over it and click <span class="FPA-icons-V3"></span>.

    If the delta capture setting is enabled for a table, two additional columns are present in the table to track changes. For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).


