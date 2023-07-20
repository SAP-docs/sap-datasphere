<!-- loiocb2b78a037c346ccad0ade79c6e85c54 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Process Multiple Match Results

Multiple results are input records that are matched with two or more lookup records. You can choose among the match candidates or apply a new rule to them.



<a name="loiocb2b78a037c346ccad0ade79c6e85c54__steps_hmz_25d_cqb"/>

## Procedure

1.  Select the rule node and then click <span class="FPA-icons"></span> \(Preview Data\) to open the *Preview Data* panel.

2.  Click the *Multiple* tab.

    > ### Note:  
    > If you have added a further rule to process the records in the *Multiple* category of a rule, then you can review the records in the first rule but you cannot process them.

    The panel contains two tables:

    -   The left table lists input records for which the rule has found two or more match candidates with a score above the *Review Records Score*, grouped by pairing column value.
    -   The right table lists all of the lookup entity records. When you select a pairing group on the left, this table is filtered to show match candidates for that pairing column value in descending order of match score.

    In our example, 4,481 records out of 18,248 have two or more matches with a score higher than 80% and are displayed grouped by our pairing column, *County*.

    The first pairing group, `Royal Borough of Kensington and Chelsea` contains 430 records, but only two records are shown, as this is the number given in the *Rows per Pairing Group* field. As this group is selected, the lookup table is filtered to show the two match candidates for this pairing group:

    ![](images/IL_Results_-_Multiple_90ceef5.png)

    The following tools are available above the tables:


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
    
    Reject


    
    </td>
    <td valign="top">
    
    Reject all the match candidates for the selected input records and move the input records to the *Unmatched* tab.


    
    </td>
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
    
    Rows per Pairing Group


    
    </td>
    <td valign="top">
    
    Specify the maximum number of rows to display for each pairing group.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Match


    
    </td>
    <td valign="top">
    
    Match all the records in the selected pairing group to the selected lookup record.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Match Records


    
    </td>
    <td valign="top">
    
    Select whether to display only *Match Candidates* for the selected pairing group or *All Records* in the lookup entity.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons"></span> \(Settings\)


    
    </td>
    <td valign="top">
    
    Select and reorder table columns. 

    In the right-hand lookup records table *View Settings* dialog, you can use the *Sort* and *Filter* tabs to sort on and filter by values in multiple columns.


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Click in any table column header to reorder or filter by that column's values.

3.  Review each of the pairing groups that the rule has found multiple matches for.

    Select a pairing group in the left table to filter the right table to show only the match candidates for it:

    -   If one of the match candidates in the right table is correct, select it and click *Match* to move all the records in the pairing group to the *Matched* tab.
    -   If none of the match candidates is correct, you can:
        -   Select to show *All Records* in the lookup table and manually search for the appropriate match.
        -   Leave the record unmatched.


4.  If appropriate, add a new rule to further process the remaining pairing groups and their match candidates.

    Records that remain in the *Multiple* category at the end of the flow are not included in the output of your intelligent lookup unless you select the *Include Unmatched Records* option.


