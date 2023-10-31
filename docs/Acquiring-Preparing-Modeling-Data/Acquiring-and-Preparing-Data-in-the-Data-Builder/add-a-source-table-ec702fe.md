<!-- loioec702fe3b1134f278c5c538b447b7435 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add a Source Table

Add a source table to read data from. You can add multiple source tables and combine them together using join or union operators.



<a name="loioec702fe3b1134f278c5c538b447b7435__steps_xpb_dqj_lyb"/>

## Procedure

1.  Navigate to the *View Transform Editor*.

2.  Drag a table from the *Repository* and drop it onto the diagram.

3.  Click the source table node to display its properties in the side panel, and review the properties in the *General* section:

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
    
    Information to identify the source table.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Alias
    
    </td>
    <td valign="top">
    
    You can specify an SQL alias for the table if required.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Distinct Values
    
    </td>
    <td valign="top">
    
    Indicates whether the source table uses SELECT DISTINCT statements to return only distinct values.
    
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
    
    Status
    
    </td>
    <td valign="top">
    
    The deployment and error status of the object. For more information, see [Saving and Deploying Objects](../Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    </table>
    
    If the delta capture setting is enabled for a table, you can view the *Delta Settings* section. By default, the option *Delta Capture* is selected. This option loads delta changes to the target table. If required, you can select the option *All Active Records* to load the full set of data to the target table.

    **Additional Information About Loading Delta Changes**

    To load delta changes from a source table \(including deleted records\), the delta capture setting must be enabled for the table. It is only possible to load delta changes from one source table. If you want to load delta changes from a source table, you need to ensure that the value of the option *Delta Capture* is *On* for both the source table and for the target table. In the *Transformation Flow Properties* panel, ensure that the load type *Initial and Delta* is selected.

4.  In the *Columns* section, you can view the columns of the source table. To check the data type of a column, hover over it and click <span class="FPA-icons"></span>.

    If the delta capture setting is enabled for a table, two additional columns are present in the table to track changes. For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).


