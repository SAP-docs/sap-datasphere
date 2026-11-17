<!-- loio0e99f510118748a2973e26f524c845c1 -->

# Repository Downtime Impacts on the Data Integration Monitor Features

Repository unavailability does not prevent monitoring activities, but impacts metadata-dependent features.



## Overview

When the SAP Datasphere repository is temporarily unavailable, tasks that are run in the *Data Integration* monitor continue to work as usual. Also, the *Data Integration*monitor continues to display monitoring information that is retrieved from runtime and control-table data. However, some monitor features that depend on repository metadata are unavailable or provide limited functionality.

The impact varies by monitor. The following table summarizes the impact of repository unavailability on each monitor. For detailed impacts, refer to the relevant section below in this topic.


<table>
<tr>
<th valign="top">

Monitor

</th>
<th valign="top">

Monitoring Data Available

</th>
<th valign="top">

Business Name Displayed

</th>
<th valign="top">

Warning Displayed

</th>
<th valign="top">

Features Disabled

</th>
</tr>
<tr>
<td valign="top">

*Local Tables* Monitor and *Local Tables \(file\)* Monitor

</td>
<td valign="top">

Yes

</td>
<td valign="top">

No - Technical names are displayed

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

*Remote Tables* Monitor

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Technical names may be displayed

</td>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

*Views* Monitor

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Technical names may be displayed

</td>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

*Task Chains* Monitor

</td>
<td valign="top">

Yes

</td>
<td valign="top">

No - Technical names are displayed

</td>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

*Flows* Monitor

</td>
<td valign="top">

Yes

</td>
<td valign="top">

No - Technical names are displayed

</td>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
</tr>
</table>



### Summary

Repository unavailability primarily affects features that require design-time object information. Runtime monitoring information remains available for most monitors.

As a result, monitoring and analysis activities can typically continue, while metadata-dependent functions such as business-name resolution, data deletion, and schedule management may be limited or unavailable



## Local Tables Monitor and Local Tables \(File\) Monitor

The *Local Tables* and the *Local Tables \(File\)*Monitors remain accessible when the repository is unavailable: you can continue to view monitoring information, review object status and runtime information, and analyze run results.



### Overview Page

The monitors continue to display monitoring information, but:

-   A message is displayed indicating that the repository is unavailable and technical names are shown instead of business names.
-   The technical name column is displayed to help identify objects.



### Object Details Page

A warning message is displayed indicating that the repository is unavailable and certain features are disabled.

The following actions are unavailable:

-   *Delete Records*
-   *Open Data Editor*
-   Other repository-dependent object actions



### Data Deletion Page

The following data deletion functions are disabled:

-   *Deletion Type* selection
-   *Refresh Estimate* button
-   *Show Preview* button
-   *Delete Records* confirmation button in the dialog

As a result, data deletion operations can't be started while the repository is unavailable.



### Schedule Management

Schedule management actions are disabled, including:

-   *Create Schedule* button
-   *Add from Connection* menu action
-   *Schedule* menu action \(Create/delete/edit any schedule, this includes merge and optimize schedules\)

> ### Note:  
> In the *Local Tables \(File\)* monitor, direct optimize and merge operations remain available while the repository is unavailable.



## Remote Tables Monitor

The *Remote Tables* Monitor continues to function, and monitoring data remains available.

When repository information can't be retrieved:

-   Technical names may be displayed instead of business names.
-   No warning message is shown.



## Views Monitor

The *Views* Monitor continues to function, and monitoring data remains available.

When repository information can't be retrieved:

-   Technical names may be displayed instead of business names.
-   No warning message is shown.



## Task Chains Monitor

The *Task Chains* Monitor continues to provide access to task chain monitoring data because runtime information is retrieved independently of the repository.

When the repository is unavailable:

-   Business names are replaced by technical names \(object IDs\) in the task chain overview, task chain run details, and task chain node names.
-   No warning message is shown.



## Flows Monitor \(Data Flows, Transformation Flows, Replication Flows\)

The *Flows* Monitor continues to provide monitoring information, and actions \(Run, Cancel/Stop, Schedule, Download logs\) are still working, as they depend on the runtime \(SAP HANA\) being available, run instances existing, space lock, and user privileges.

When the repository is unavailable:

-   Technical names are displayed instead of business names.
-   No warning message is shown.



## Remote Queries Monitor

The *Remote Queries* Monitor continues to provide monitoring information.

When the repository is unavailable:

-   Business name Column is empty.
-   No warning message is shown.



## Objects with Failed Runs Monitor

The *Object With Failed Runs* Monitor continues to provide monitoring information when the repository is unavailable. Failed run information is retrieved from runtime data and therefore remains available.

When the repository is unavailable:

-   Technical names are displayed instead of business names.
-   No warning message is shown.

