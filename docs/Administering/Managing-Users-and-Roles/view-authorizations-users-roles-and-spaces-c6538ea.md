<!-- loioc6538ea2db884e599072e62bdb03e68c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# View Authorizations \(Users, Roles and Spaces\)

See all the users, roles, and spaces in the tenant and how they relate to each other.

In <span class="FPA-icons-V3"></span> \(*Security*\) ** \> ** <span class="SAP-icons-V5"></span> \(*Authorization Overview*\), a user with the DW Administrator global role can see all the users, roles, and spaces in the tenant and how they relate to each other. You can filter by user, role, or space to see:

-   which users are assigned with which roles to which spaces,
-   which users are assigned to which global roles.



## Enter a String to Search On

To display information related to the one or more terms, enter one or more characters in the *Search* field and press *Enter* \(or click *Search*\).

As you type, the field will begin proposing objects and search strings. Click on a string to trigger a search on it.

For example, to display all roles that are assigned to the user Lucia, enter "Lucia" in the *Search*.



<a name="loioc6538ea2db884e599072e62bdb03e68c__section_criteria_filter"/>

## Filter by Criteria

You can filter the list by any of the categories listed in the *Filter By* area of the left panel: user \(in *User Name*\), space \(in *Scope Name*\) and role \(in *Role Name*\).

You can select one or more values in each filter category in the *Filter By* section:

-   Each value selected in a category acts as an `OR` condition. For example, to display all roles that are assigned to the users Lucia and Ahmed, select Lucia and Ahmed in the *User Name* category.
-   Values selected in separate categories act together as `AND` conditions. For example, to display all the scoped roles that enables Lucia to access the Sales Asia space, select Lucia in the *User Name* category and Sales Asia in the *Scope Name* category.

