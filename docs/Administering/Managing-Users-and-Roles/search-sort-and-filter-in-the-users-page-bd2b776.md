<!-- loiobd2b776b0ef94d89a7db1110e8012aac -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Search, Sort and Filter in the Users Page

The Users page gives you access to all SAP Datasphere users. You can search, sort and filter the list of users, open and edit existing users, and create new users.

This topic contains the following sections:

-   [Enter a String to Search On](search-sort-and-filter-in-the-users-page-bd2b776.md#loiobd2b776b0ef94d89a7db1110e8012aac__section_x5m_d2v_zfc)
-   [Show, Hide and Order Columns](search-sort-and-filter-in-the-users-page-bd2b776.md#loiobd2b776b0ef94d89a7db1110e8012aac__section_bqc_frm_zfc)
-   [Sort](search-sort-and-filter-in-the-users-page-bd2b776.md#loiobd2b776b0ef94d89a7db1110e8012aac__section_rhy_frm_zfc)
-   [Filter by Criteria](search-sort-and-filter-in-the-users-page-bd2b776.md#loiobd2b776b0ef94d89a7db1110e8012aac__section_criteria_filter)
-   [Define Advanced Filter Conditions](search-sort-and-filter-in-the-users-page-bd2b776.md#loiobd2b776b0ef94d89a7db1110e8012aac__section_prf_4gv_zfc)
-   [Display Former Interface](search-sort-and-filter-in-the-users-page-bd2b776.md#loiobd2b776b0ef94d89a7db1110e8012aac__section_n4c_4sw_zfc)



<a name="loiobd2b776b0ef94d89a7db1110e8012aac__section_tlx_r1b_1gc"/>

## Access the Users Page

In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Security*\) ** \> ** <span class="FPA-icons-V3"></span> \(*Users*\).



<a name="loiobd2b776b0ef94d89a7db1110e8012aac__section_x5m_d2v_zfc"/>

## Enter a String to Search On

Enter one or more characters in the *Search* field and press *Enter* \(or click *Search*\).

-   As you type, the field will begin proposing objects and search strings. Click on a string to start a search on it.
-   The search is case-insensitive and automatically applies wildcards so that, for example, the string "`rob`" will find objects containing both "`roberta`" and "`robert`".



<a name="loiobd2b776b0ef94d89a7db1110e8012aac__section_bqc_frm_zfc"/>

## Show, Hide and Order Columns

You can control the display of columns in the user table.

1.  Click :gear:.
2.  Modify the column list in any of the following ways:
    -   To select a column for display, select its checkbox. To hide a column deselect its checkbox.
    -   To change the order of the columns in the table, click on a column name to highlight it and use the arrow buttons <span class="SAP-icons-V5"></span> \(Move column up\) and <span class="SAP-icons-V5"></span> \(Move column down\) to move it in the list.
    -   Click *Reset* to go back to the default column display.

3.  Click *OK* to apply your changes.



<a name="loiobd2b776b0ef94d89a7db1110e8012aac__section_rhy_frm_zfc"/>

## Sort

You can control the ordering of data in the user table.

1.  Click <span class="SAP-icons-V5"></span> \(Sort\).

    By default, the table is sorted by *Best Match on Top*, which calculates relevance on a range of criteria, including users that you have recently changed and those that you have created.

2.  To sort on a specific column, select a *Sort Order* and a *Sort By* column, and then click *OK* to apply the changes.



<a name="loiobd2b776b0ef94d89a7db1110e8012aac__section_criteria_filter"/>

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

All users assigned to the "Sales Europe" space.

</td>
<td valign="top">

*Scope Name*: "Sales Modeler"

</td>
</tr>
<tr>
<td valign="top">

All users assigned to the "Sales Europe" or the "Sales Asia" space.

</td>
<td valign="top">

*Scope Name*: "Sales Modeler", "Sales Asia"

</td>
</tr>
<tr>
<td valign="top">

Users assigned to the "Sales Europe" or the "Sales Asia" space and who were last connected to the SAP Datasphere tenant in Quarter 1 of 2025.

</td>
<td valign="top">

*Scope Name*: "Sales Modeler", "Sales Asia"

and

*Last Connected On*: date range from January 1st to March 31 2025

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

Created On

</td>
<td valign="top">

Select the date range for when the user was created on.

</td>
</tr>
<tr>
<td valign="top">

Display Name

</td>
<td valign="top">

Search for the users by their display name.

</td>
</tr>
<tr>
<td valign="top">

First Name

</td>
<td valign="top">

Search for the users by their first name.

</td>
</tr>
<tr>
<td valign="top">

Last Connected On

</td>
<td valign="top">

Select the date range for when the user last connected into the SAP Datasphere tenant.

</td>
</tr>
<tr>
<td valign="top">

Last Name

</td>
<td valign="top">

Search for the users by their last name.

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

Manager Name

</td>
<td valign="top">

Not used in SAP Datasphere.

</td>
</tr>
<tr>
<td valign="top">

Role Name

</td>
<td valign="top">

Search for the users to which the roles you select are assigned.

</td>
</tr>
<tr>
<td valign="top">

Scope Name

</td>
<td valign="top">

Search for the users to which the spaces you select are assigned via scoped roles.

</td>
</tr>
<tr>
<td valign="top">

User Status

</td>
<td valign="top">

Select the user status: activated or deactivated.

</td>
</tr>
<tr>
<td valign="top">

User ID

</td>
<td valign="top">

Search for the users by their unique ID.

</td>
</tr>
</table>



<a name="loiobd2b776b0ef94d89a7db1110e8012aac__section_prf_4gv_zfc"/>

## Define Advanced Filter Conditions

For those filter options that are not related to date or time, you can create a custom filter with specific conditions.

1.  Click *Show More* at the bottom of a filter category to open the Filter Settings dialog. Some filters have a *Select Items* and a *Define Conditions* tab.
2.  On the *Define Conditions* tab, choose an operator and enter a value in the *Filter Condition* box.
3.  Click :heavy_plus_sign: to create an alternative condition. Each condition in one category acts as an `OR` operator, so that an object must meet one of the conditions to be included in the search results. If you define one condition in two categories, then each category acts as an `AND` operator, so that both conditions must be true for the object to be returned in the search results.

You can create advanced filter conditions for multiple filter categories. An object must meet one of the conditions in each of the categories to be included in the search results.



<a name="loiobd2b776b0ef94d89a7db1110e8012aac__section_n4c_4sw_zfc"/>

## Display Former Interface

You can display the former interface of the *Users* page, and again the current interface, by clicking <span class="SAP-icons-V5"></span> \(Show Former Interface\).

