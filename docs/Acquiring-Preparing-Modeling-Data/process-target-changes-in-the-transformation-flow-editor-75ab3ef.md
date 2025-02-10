<!-- loio75ab3ef235f845b6bfddcafee198449c -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Process Target Changes in the Transformation Flow Editor

If the target table of your transformation flow is modified, then the next time you open the transformation flow, you will be asked to process the changes. If a change has generated errors in your transformation flow, you will receive a notification inviting you to review them.



## Procedure

1.  If a target change has generated errors in your transformation flow, you will receive a notification inviting you to review them, and you can click the notification to open it directly.

    The *Target Updates* dialog opens, listing the objects that have been modified.

    > ### Note:  
    > If the changes do not generate errors \(for example, new columns are available\), you will not receive a notification, but the dialog will still be displayed the next time that you open the transformation flow.

2.  Click *OK* to dismiss the dialog and open the diagram. The following validation messages may be displayed:


    <table>
    <tr>
    <th valign="top">

    Change
    
    </th>
    <th valign="top">

    Impact
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    New Column
    
    </td>
    <td valign="top">
    
    New target columns are left unmapped by default in the target table node of the transformation flow:

    -   An information message listing all new columns is displayed on the target.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Change Column Data Type
    
    </td>
    <td valign="top">
    
    Target column data type changes may generate information or error messages for the transformation flow:

    -   An information message listing all columns with changed data types is displayed on the target.
    -   An error message is displayed on any node where an incompatible data type change is present.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delete Column
    
    </td>
    <td valign="top">
    
    Deleted target columns generate errors for the transformation flow if the columns are used in the transformation flow:

    -   An information message listing all deleted columns is displayed on the target.
    -   An error message is displayed on any intermediate node \(join, union, projection, aggregation, script\) in which a deleted column was used.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Change Key Column
    
    </td>
    <td valign="top">
    
    Changes to key columns will generate information messages:

    -   An information message listing all changed key columns is displayed on the target.


    
    </td>
    </tr>
    </table>
    
3.  Review all information messages to ensure that they do not adversely impact the output of your transformation flow.

4.  Review and resolve any error messages.

5.  If appropriate, map any new target columns in the target table node.

    You cannot modify the structure of the target table directly in the transformation flow editor. If you need to make such changes \(for example to add new source columns or change data types\), you must open and edit it in the table editor. Once you have saved the updated target table, you can return to the transformation flow and adjust mappings as appropriate in the target table node.

6.  Click <span class="FPA-icons-V3"></span> \(Save\) to save the changes to your transformation flow and dismiss the information messages.


