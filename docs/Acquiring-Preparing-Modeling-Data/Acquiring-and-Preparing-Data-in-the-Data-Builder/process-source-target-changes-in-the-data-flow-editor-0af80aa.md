<!-- loio0af80aa3a0774c67803565fe0888df99 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Process Source/Target Changes in the Data Flow Editor

If one or more of the sources \(or the target table\) of your data flow is modified, then the next time you open the data flow, you will be asked to process the changes. If a change has generated errors in your data flow, you will receive a notification inviting you to review them.



## Procedure

1.  If a source or target change has generated errors in your data flow, you will receive a notification inviting you to review them, and you can click the notification to open it directly.

    The *Source/Target Updates* dialog opens, listing the objects that have been modified.

    > ### Note:  
    > If the changes do not generate errors \(for example, new columns are available\), you will not receive a notification, but the dialog will still be displayed the next time that you open the data flow.

2.  Click *OK* to dismiss the dialog and open the diagram. The following validation messages may be displayed:


    <table>
    <tr>
    <th valign="top">

    Change


    
    </th>
    <th valign="top">

    Impact in Dependent Data Flows


    
    </th>
    </tr>
    <tr>
    <td valign="top">

    New Column


    
    </td>
    <td valign="top">

    New source or target columns are left unmapped by default in the target table node of dependent data flows:

    -   An information message listing all new columns is displayed on the source and/or target.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Change Column Data Type


    
    </td>
    <td valign="top">

    Source or target column data type changes may generate information or error messages in dependent data flows:

    -   An information message listing all columns with changed data types is displayed on the source and/or target.
    -   An error message is displayed on any node where an incompatible data type change is present.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Delete Column


    
    </td>
    <td valign="top">

    Deleted source columns generate errors in dependent data flows if the columns are used in these data flows:

    -   An information message listing all deleted columns is displayed on the source and/or target.
    -   An error message is displayed on any intermediate node \(join, union, projection, aggregation, script\) in which a deleted column was used.


    
    </td>
    </tr>
    </table>
    
3.  Review all information messages to ensure that they do not adversely impact the output of your data flow.

4.  Review and resolve any error messages on intermediate data flow nodes.

5.  If appropriate, map any new source or target columns in the target table node.

    You cannot modify the structure of the target table directly in the data flow editor. If you need to make such changes \(for example to add new source columns or change data types\), you must open and edit it in the table editor. Once you have saved the updated target table, you can return to the data flow and adjust mappings as appropriate in the target table node.

    > ### Note:  
    > If you leave any target table column unmapped, new runs of the data flow will insert null values into it.

6.  Click <span class="FPA-icons"></span> \(Save\) to save the changes to your data flow and dismiss the information messages.


