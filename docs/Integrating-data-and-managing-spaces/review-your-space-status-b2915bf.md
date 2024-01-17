<!-- loiob2915bf4c184465983f2ed055ebc00fc -->

# Review Your Space Status

Color codes and icons indicate the health of a space.

You can see the status of all spaces at the top of the *Space Management* page.

You also can see the status of an individual space at the top-left of the space.

Each status shows the used storage and may indicate whether a space needs extra attention. The status also shows whether a space is active or not \(locked\).


<table>
<tr>
<th valign="top">

Icon

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

![](images/Cold_Space_Status_ff2d06e.jpg)

</td>
<td valign="top">

**Cold**

The used storage is 5% or less.

</td>
</tr>
<tr>
<td valign="top">

![](images/Green_Space_Status_f746833.jpg)

</td>
<td valign="top">

**Healthy**

The used storage is between 6% and 90%.

</td>
</tr>
<tr>
<td valign="top">

![](images/Hot_Space_Status_c64656e.jpg)

</td>
<td valign="top">

**Critical**

The used storage is greater than 90%.

This space is close to exceeding it's storage quota. It might make sense to delete unnecessary data in your space or to extend the assigned storage.

If your space exceeds it's storage quota, it might change to a locked state.

</td>
</tr>
<tr>
<td valign="top">

![](images/Status_Locked_Space_9fa9e79.jpg)

</td>
<td valign="top">

**Locked**

A space is locked:

-   if the space exceeds its allocations of memory or disk storage,
-   if the audit logs consume too much disk storage,
-   if a space administrator has manually locked the space.

For more information on how to unlock a space, see [Lock or Unlock Your Space](lock-or-unlock-your-space-c05b6a6.md).

When a space is locked, its capabilities are limited. Users can continue to create and modify objects and save their changes in the repository, but they cannot deploy their changes to the run-time database.

Restrictions include:

-   changes to data layer objects can be saved, but deployment is blocked

-   uploading a CSV file is blocked

-   wrangling is blocked

-   open SQL users are blocked

-   insert privilege is removed from the Space Manager

-   assigning users and creating open SQL schemas in Space Management is blocked

-   all direct execution or scheduling of tasks in the *Data Integration Monitor* or in the *Data Builder* that allow to add data to the space.



</td>
</tr>
</table>

