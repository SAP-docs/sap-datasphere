<!-- loiof3d98b149b094592a0840a4e951f1426 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Process Matched Results

Matched results are input records that are matched with a lookup record. You can reject any matches that you do not agree with.



## Procedure

1.  Select the rule node and then click <span class="FPA-icons"></span> \(Preview Data\) to open the *Preview* panel.

2.  Click the *Matched* tab.

    The panel contains a single table listing matched records grouped by pairing column value.

    In our example, 4,138 out of 18,248 records have been matched with a score of 100% and are displayed grouped by our pairing column, *County*.

    The first pairing group, `Buckinghamshire`, contains 288 records, but only two records are shown, as this is the number given in the *Rows per Pairing Group* field:

    ![](images/IL_Results_-_Matched_f8f9d9a.png)

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
    </table>
    
    > ### Note:  
    > Click in any table column header to reorder or filter by that column's values.

3.  Review each of the pairing groups that the rule has matched with lookup records.

    If you don't agree with the matching of a pairing group, then select the checkbox to the left of the group, and click *Reject* to move all its records to the *Unmatched* tab.

    Records in the *Matched* category are always included in the output of your intelligent lookup.


