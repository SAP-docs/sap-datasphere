<!-- loiob2915bf4c184465983f2ed055ebc00fc -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Review Your Space Status

Color codes and icons indicate the health of a space.

> ### Note:  
> Relevant only for spaces with a storage type *SAP HANA Database \(Disk and In-Memory\)*, and not for *SAP HANA Data Lake Files* spaces.

You can see the status of all spaces at the top of the *Space Management* page.

You also can see the status of an individual space at the top-left of the space.

Each status shows the used storage and may indicate whether a space needs extra attention. The status also shows whether a space is active or not \(locked\).


<table>
<tr>
<th valign="top">

Status

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

<span style="color:#007cc0;"><span class="FPA-icons-V3"></span></span> \(**Cold**\)

</td>
<td valign="top">

The used storage is 5% or less.

</td>
</tr>
<tr>
<td valign="top">

<span style="color:#007833;"><span class="FPA-icons-V3"></span></span> \(**Healthy**\)

</td>
<td valign="top">

The used storage is between 6% and 90%

</td>
</tr>
<tr>
<td valign="top">

<span style="color:#d14900;"><span class="FPA-icons-V3"></span></span> \(**Critical**\)

</td>
<td valign="top">

The used storage is greater than 90%.

This space is close to exceeding it's storage quota. It might make sense to delete unnecessary data in your space or to extend the assigned storage.

If your space exceeds it's storage quota, it might change to a locked state.

</td>
</tr>
<tr>
<td valign="top">

<span style="color:#cc1919;"><span class="FPA-icons-V3"></span></span> \(**Locked**\)

</td>
<td valign="top">

A space is locked:

-   if the space exceeds its allocations of memory or disk storage,
-   if the audit logs consume too much disk storage,
-   if a space administrator has manually locked the space.

For more information on how to unlock a space, see [Unlock a Locked Space](unlock-a-locked-space-c05b6a6.md).

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

