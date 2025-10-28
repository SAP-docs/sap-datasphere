<!-- loiofafc1e21bff040c386c7d691caa30915 -->

# Statuses and Substatuses for Replication Flows

Replication flows statuses and sub-statuses provides a better understanding of data loading processes and potential errors. It is useful for monitoring and troubleshooting replication flows.

On the left of the monitoring screen, you find the aggregated status information for your replication flow. If the status for one or more objects in a run differs from the overall status, this is indicated by an additional status value in brackets.

As long as the status is *Running* or *Active*, you cannot start another run for the same replication flow.

In addition to the main statuses \(Running, Active, Completed, Paused, Failed\), and the standard substatuses \(see [Understanding Statuses and Substatuses](understanding-statuses-and-substatuses-19cb5bd.md)\), additional substatuses can be combined at the replication flow level or on the object level.

**Combination of Statuses and Substatuses for a Replication Flow Running With Load Type: Initial Only**


<table>
<tr>
<th valign="top">

Statuses \(Substatuses

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Running \(Failed / Paused / Retrying Objects\)

</td>
<td valign="top">

The data is being loaded, but one or more objects have errors, and the user has paused one or more objects. Furthermore, one or more objects could not be loaded, and a new attempt is planned.

</td>
</tr>
<tr>
<td valign="top">

Running \(Failed / Paused Objects\)

</td>
<td valign="top">

The data is being loaded, but one or more objects have errors, and the user has paused one or more objects.

</td>
</tr>
<tr>
<td valign="top">

Running \(Failed objects\)

</td>
<td valign="top">

The data is being loaded, but one or more objects have errors.

</td>
</tr>
<tr>
<td valign="top">

Running \(Paused / Retrying Objects\)

</td>
<td valign="top">

The data is being loaded, but the user has paused one or more objects, or one or more objects could not be loaded \(error or data not ready\). A new attempt is planned.

</td>
</tr>
<tr>
<td valign="top">

Running \(Paused Objects\)

</td>
<td valign="top">

The data is being loaded, but the user has paused one or more objects.

</td>
</tr>
<tr>
<td valign="top">

Running \(Retrying Objects\)

</td>
<td valign="top">

The data is being loaded, but one or more objects could not be loaded. A new attempt is planned.

</td>
</tr>
</table>

**Combination of Statuses and Substatuses for a Replication Flow Running with Load Type: Initial and Delta or Delta Only**


<table>
<tr>
<th valign="top">

Statuses \(Substatuses

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Active \(Failed Objects\)

</td>
<td valign="top">

The data will be loaded according to the schedule \(delta load interval\), but one or more objects have errors.

</td>
</tr>
<tr>
<td valign="top">

Active \(Failed / Paused / Retrying Objects\)

</td>
<td valign="top">

The data will be loaded according to the schedule \(delta load interval\), but one or more objects have errors, and a user has paused one or more objects. Furthermore, one or more objects could not be loaded. A new attempt is planned.

</td>
</tr>
<tr>
<td valign="top">

Active \(Failed / Paused Objects\)

</td>
<td valign="top">

The data will be loaded according to the schedule \(delta load interval\), but one or more objects have errors, and a user has paused one or more objects.

</td>
</tr>
<tr>
<td valign="top">

Active \(Paused / Retrying Objects\)

</td>
<td valign="top">

The data will be loaded according to the schedule \(delta load interval\), but one or more objects have been paused by a user, or one or more objects could not be loaded \(error or data not ready yet\). A new attempt is planned.

</td>
</tr>
<tr>
<td valign="top">

Active \(Paused Objects\)

</td>
<td valign="top">

The data is being loaded, but the user has paused one or more objects.

</td>
</tr>
<tr>
<td valign="top">

Active \(Retrying Objects\)

</td>
<td valign="top">

The data will be loaded according to the schedule \(delta load interval\), but one or more objects could not be loaded. A new attempt is planned.

</td>
</tr>
</table>

**Statuses at Object Level**


<table>
<tr>
<th valign="top">

Statuses

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Created

</td>
<td valign="top">

The replication task for the object is created in the runtime, but has not started yet.

</td>
</tr>
<tr>
<td valign="top">

Completed

</td>
<td valign="top">

The replication task for the object has successfully transferred the data to the target.

</td>
</tr>
<tr>
<td valign="top">

Failed

</td>
<td valign="top">

The replication task for the object has failed during the transfer of data.

</td>
</tr>
<tr>
<td valign="top">

Retrying

</td>
<td valign="top">

The replication task for the object is in retrying state, due to temporary errors, or waiting for delta data from the source system.

</td>
</tr>
<tr>
<td valign="top">

Deleting

</td>
<td valign="top">

The replication task for the object is getting cleaned up or removed by the runtime.

</td>
</tr>
<tr>
<td valign="top">

Paused

</td>
<td valign="top">

The replication task for the object has been paused by the user.

</td>
</tr>
<tr>
<td valign="top">

Pausing

</td>
<td valign="top">

The replication task for the object is in the process of being paused.

</td>
</tr>
<tr>
<td valign="top">

Running, Initial Running, Delta Running

</td>
<td valign="top">

The replication task for the object is currently transferring data to the target object.

</td>
</tr>
<tr>
<td valign="top">

Restarting

</td>
<td valign="top">

The replication task for the object is re-initializing.

</td>
</tr>
</table>

To understand how to manage existing replication flow runs, see [Working With Existing Replication Flow Runs](working-with-existing-replication-flow-runs-da62e1e.md)

