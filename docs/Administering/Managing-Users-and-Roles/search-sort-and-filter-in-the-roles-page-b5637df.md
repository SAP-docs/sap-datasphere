<!-- loiob5637dfef7744590bdae82f0d57363af -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Search, Sort and Filter in the Roles Page

The *Roles* page gives you access to all SAP Datasphere roles. You can search, sort and filter the list of roles, open and edit existing roles, and create new roles.

This topic contains the following sections:

-   [Enter a String to Search On](search-sort-and-filter-in-the-roles-page-b5637df.md#loiob5637dfef7744590bdae82f0d57363af__section_x5m_d2v_zfb)
-   [Show, Hide and Order Columns](search-sort-and-filter-in-the-roles-page-b5637df.md#loiob5637dfef7744590bdae82f0d57363af__section_bqc_frm_zfb)
-   [Sort](search-sort-and-filter-in-the-roles-page-b5637df.md#loiob5637dfef7744590bdae82f0d57363af__section_rhy_frm_zfb)
-   [Filter by Criteria](search-sort-and-filter-in-the-roles-page-b5637df.md#loiob5637dfef7744590bdae82f0d57363af__section_criteria_filterb)
-   [Define Advanced Filter Conditions](search-sort-and-filter-in-the-roles-page-b5637df.md#loiob5637dfef7744590bdae82f0d57363af__section_prf_4gv_zfb)
-   [Display Former Interface](search-sort-and-filter-in-the-roles-page-b5637df.md#loiob5637dfef7744590bdae82f0d57363af__section_n4c_4sw_zfb)



<a name="loiob5637dfef7744590bdae82f0d57363af__section_tlx_r1b_1gc"/>

## Access the Roles Page

In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Security*\) ** \> ** <span class="FPA-icons-V3"></span> \(*Roles*\).



<a name="loiob5637dfef7744590bdae82f0d57363af__section_x5m_d2v_zfb"/>

## Enter a String to Search On

Enter one or more characters in the *Search* field and press *Enter* \(or click *Search*\).

-   As you type, the field will begin proposing objects and search strings. Click on a string to start a search on it.
-   The search is case-insensitive and automatically applies wildcards so that, for example, the string "`lend`" will find objects containing both "`lender`" and "`calender`".



<a name="loiob5637dfef7744590bdae82f0d57363af__section_bqc_frm_zfb"/>

## Show, Hide and Order Columns

You can control the display of columns in the role table.

1.  Click :gear:.
2.  Modify the column list in any of the following ways:
    -   To select a column for display, select its checkbox. To hide a column deselect its checkbox.
    -   To change the order of the columns in the table, click on a column name to highlight it and use the arrow buttons <span class="SAP-icons-V5"></span> \(Move column up\) and <span class="SAP-icons-V5"></span> \(Move column down\) to move it in the list.
    -   Click *Reset* to go back to the default column display.

3.  Click *OK* to apply your changes.



<a name="loiob5637dfef7744590bdae82f0d57363af__section_rhy_frm_zfb"/>

## Sort

You can control the ordering of data in the role table.

1.  Click <span class="SAP-icons-V5"></span> \(Sort\).

    By default, the table is sorted by *Best Match on Top*, which calculates relevance on a range of criteria, including roles that you have recently changed and those that you have created.

2.  To sort on a specific column, select a *Sort Order* and a *Sort By* column, and then click *OK* to apply the changes.



<a name="loiob5637dfef7744590bdae82f0d57363af__section_criteria_filterb"/>

## Filter by Criteria

You can filter the list by any of the categories listed in the *Filter By* area of the left panel.

To display the *Filter By* panel, click <span class="SAP-icons-V5"></span> \(Show filters\).

You can select one or more values in each filter category in the *Filter By* section:

-   Each value selected in a category acts as an `OR` condition.
-   Values selected in separate categories act together as `AND` conditions.

For example:


<table>
<tr>
<th valign="top">

To Display

</th>
<th valign="top">

Select Filter Criteria

</th>
</tr>
<tr>
<td valign="top">

All scoped roles.

</td>
<td valign="top">

*Role Scope*: *Scoped Role*

</td>
</tr>
<tr>
<td valign="top">

All roles that are either global or scoped.

</td>
<td valign="top">

*Role Scope*: *Scoped Role*, *Global Role*

</td>
</tr>
<tr>
<td valign="top">

Global or scoped roles that are assigned to the user "Lisa".

</td>
<td valign="top">

*Role Scope*: *Scoped Role*, *Global Role*

and

*User ID*: "Lisa"

</td>
</tr>
<tr>
<td valign="top">

All standard roles that are delivered with SAP Datasphere.

</td>
<td valign="top">

*License Type*: SAP Datasphere

and

*Role Type*: *Standard Role*

</td>
</tr>
</table>

The following filter categories are available:


<table>
<tr>
<th valign="top">

Filter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Default Role

</td>
<td valign="top">

Search for whether the role is a default role or not a default role.

</td>
</tr>
<tr>
<td valign="top">

License Type

</td>
<td valign="top">

Only the license SAP Datasphere is relevant.

</td>
</tr>
<tr>
<td valign="top">

Role Description

</td>
<td valign="top">

Search for the roles by its description.

</td>
</tr>
<tr>
<td valign="top">

Role Name

</td>
<td valign="top">

Search for the role by its name.

</td>
</tr>
<tr>
<td valign="top">

Role Scope

</td>
<td valign="top">

Search for whether the role is a standard role or a custom role.

</td>
</tr>
<tr>
<td valign="top">

Role Type

</td>
<td valign="top">

Search for whether the role is a standard role or a custom role.

</td>
</tr>
<tr>
<td valign="top">

Scope Name

</td>
<td valign="top">

Search for the roles to which the spaces you select are assigned.

</td>
</tr>
<tr>
<td valign="top">

User ID

</td>
<td valign="top">

Search for the users that are assigned the role by their unique ID.

</td>
</tr>
</table>



<a name="loiob5637dfef7744590bdae82f0d57363af__section_prf_4gv_zfb"/>

## Define Advanced Filter Conditions

For those filter options that are not related to date or time, you can create a custom filter with specific conditions.

1.  Click *Show More* at the bottom of a filter category to open the Filter Settings dialog. Some filters have a *Select Items* and a *Define Conditions* tab.
2.  On the *Define Conditions* tab, choose an operator and enter a value in the *Filter Condition* box.
3.  Click :heavy_plus_sign: to create an alternative condition. Each condition in one category acts as an `OR` operator, so that an object must meet one of the conditions to be included in the search results. If you define one condition in two categories, then each category acts as an `AND` operator, so that both conditions must be true for the object to be returned in the search results.

You can create advanced filter conditions for multiple filter categories. An object must meet one of the conditions in each of the categories to be included in the search results.



<a name="loiob5637dfef7744590bdae82f0d57363af__section_n4c_4sw_zfb"/>

## Display Former Interface

You can display the former interface of the *Roles* page, and again the current interface, by clicking <span class="SAP-icons-V5"></span> \(Show Former Interface\).

