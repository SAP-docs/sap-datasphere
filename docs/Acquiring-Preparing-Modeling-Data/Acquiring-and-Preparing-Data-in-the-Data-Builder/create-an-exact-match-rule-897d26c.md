<!-- loio897d26c3ffe24efaa27cd0d7262a78ad -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create an Exact Match Rule

Create an exact match rule to compare values in input entity columns and lookup entity columns.



<a name="loio897d26c3ffe24efaa27cd0d7262a78ad__steps_ysw_pzb_cqb"/>

## Procedure

1.  Click the rule node to open its properties panel and set the following properties in the *General* section:


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

    Business Name


    
    </td>
    <td valign="top">

    Enter a name for your rule to identify it in the diagram.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Match Strategy


    
    </td>
    <td valign="top">

    Choose *Exact Match*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Input Scope


    
    </td>
    <td valign="top">

    \[read-only\] Specifies which input records are processed by the rule.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Lookup Scope


    
    </td>
    <td valign="top">

    \[read-only\] Specifies which lookup records are available for matching by the rule.


    
    </td>
    </tr>
    </table>
    
2.  Use the *Match Columns* section to specify columns to compare.

    Drag a column from the input entity and drop it onto a column in the lookup entity to specify that the values in the two columns must match exactly. If you map additional columns, the values in each column pair must all match exactly.


    <table>
    <tr>
    <th valign="top">

    Example


    
    </th>
    <th valign="top">

    Matching Criteria


    
    </th>
    </tr>
    <tr>
    <td valign="top">

    ![](images/Exact_Match_-_One_Column_Pair_54e2255.png)


    
    </td>
    <td valign="top">

    An input record is matched with a lookup record if:

    -   The value in the input `County` column exactly matches the value in the lookup `County Name` column.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    ![](images/Exact_Match_-_Two_Column_Pairs_adecfff.png)


    
    </td>
    <td valign="top">

    An input record is matched with a lookup record if:

    -   The value in the input `Town` column exactly matches the value in the lookup `Town Name` column, and
    -   The value in the input `County` column exactly matches the value in the lookup `County Name` column.


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > You can only map a column to a column of the same data type.

3.  \[optional\] Control case-sensitivity and whitespace trimming with the options in the *Advanced Settings* section.


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

    Case-Sensitive


    
    </td>
    <td valign="top">

    Disable this option to allow case-insensitive matching. 

    By default, exact match rules are case-sensitive so that, for example, an input column containing the string "`paris`" will not be matched with a lookup column containing "`Paris`".


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Trim Leading and Trailing Whitespace 


    
    </td>
    <td valign="top">

    Disable this option to take into account any space characters preceding or following string values. 

    By default, exact match rules trim whitespace so that, for example, an input column containing the string "`London`" or `London` will be matched with a lookup column containing `London`.


    
    </td>
    </tr>
    </table>
    
4.  Save, deploy, and run your intelligent lookup to see the results of your rule.

    1.  Click <span class="SAP-icons"></span> \(Deploy\) to save and deploy your intelligent lookup.

        If you have not previously saved the intelligent lookup, you will be prompted to provide a business and technical name for it. Enter appropriate names, and then click Save.

        > ### Note:  
        > You need to re-deploy your intelligent lookup each time your make a change to it. If you have pending changes, they will be saved automatically before deployment.

    2.  Once deployment is complete, click <span class="FPA-icons"></span> \(Run\) to run the intelligent lookup and review the results.



