<!-- loioffcae430ffd6446f9fb1ad42d085022b -->

# Select a Table or View to Define Permissions

Select a table or view containing user ids and one or more filter criteria to provide permissions information to your data access control.



<a name="loioffcae430ffd6446f9fb1ad42d085022b__context_b2z_qfb_q4b"/>

## Context

This permissions entity must have at least two columns as follows:

-   A column containing user ids in the format required by your identity provider \(email addresses, logon names, or other identifiers\). This column must be selected as the *Identifier Column* in your data access control.
-   One or more columns containing filter criteria \(country or region names or ids, department names or ids, or any other criteria to control how your data is exposed to users\). These columns must be selected as *Criteria* columns in your data access control.



<a name="loioffcae430ffd6446f9fb1ad42d085022b__steps_xqj_rfb_q4b"/>

## Procedure

1.  Click the *Permissions Entity* field to open the *Select Permissions Entity* dialog.

2.  In the *Data Objects* list, select the table or view containing your user logins and columns with filter criteria.

3.  In the *Available Columns* list, select one or more columns containing the criteria on which you want to control the display of data.

    These columns will be listed in the *Criteria* section. When you assign a data access control to a view, these columns must be mapped to columns in the view to enforce filtering by these criteria.

4.  Click *OK* to confirm the selection.


