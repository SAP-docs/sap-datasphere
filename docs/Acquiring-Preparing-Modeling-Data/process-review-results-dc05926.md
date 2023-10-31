<!-- loiodc05926d63674b45b55168d06858fdfa -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Process Review Results

Review results are input records that are matched with a lookup record with a score between the *Review* and *Matched* thresholds. You can approve or reject proposed matches.



## Procedure

1.  Select the rule node and then click <span class="FPA-icons"></span> \(Preview Data\) to open the *Preview Data* panel.

2.  Click the *Review* tab.

    The panel contains a single table listing matched records requiring review grouped by pairing column value.

    In our example, 4,206 records out of 18,248 have been matched with a score between 80% and 100% and are displayed grouped by our pairing column, *County*.

    The first pairing group, `City of Westminster`, contains 858 records, but only two records are shown, as this is the number given in the *Rows per Pairing Group* field:

    ![](images/IL_Results_-_Review_07f82ac.png)

    The following tools are available above the table:


    <table>
    <tr>
    <th valign="top">

    Tools
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons"></span> \(Collapse All\) / <span class="SAP-icons"></span> \(Expand All\)
    
    </td>
    <td valign="top">
    
    Collapse or expand all pairing groups.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Confirm
    
    </td>
    <td valign="top">
    
    Confirm the selected match and move the records to the *Matched* tab.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Reject
    
    </td>
    <td valign="top">
    
    Reject the selected match and move the matched records to the *Unmatched* tab.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Rows per Pairing Group
    
    </td>
    <td valign="top">
    
    Specify the maximum number of rows to display for each pairing group.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons"></span> \(Settings\)
    
    </td>
    <td valign="top">
    
    Select and reorder table columns.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Click in any table column header to reorder or filter by that column's values.

3.  Review each of the pairing groups that the rule has tentatively matched:

    Select the checkbox to the left of one or more pairing groups:

    -   If you agree with the proposed match, click *Confirm* to move all the records in the selected pairing groups to the *Matched* tab.
    -   If you don't agree with the proposed match, click *Reject* to move all the records in the selected pairing groups to the *Unmatched* tab.

    Records in the *Review* category are included in the output of your intelligent lookup unless you deselect the *Include Review Records* option.


