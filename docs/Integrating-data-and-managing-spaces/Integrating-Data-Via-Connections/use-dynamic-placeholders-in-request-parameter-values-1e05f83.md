<!-- loio1e05f8338caf48c29c2a3440530f8255 -->

# Use Dynamic Placeholders in Request Parameter Values

Dynamic placeholders in request parameter values automatically insert runtime values into requests sent by a custom connection type.



## Context

Dynamic placeholders can be used in request parameters that are passed as query parameters, headers, or cookies, provided that the target API supports the supplied value format. For example, they can be used in filter or query parameters to retrieve data that has changed since a previous execution.



## Delta Synchronization

To configure delta synchronization, define a filter or query parameter supported by the target API and use a `${lastRunTime:<format>}` placeholder in the parameter value.

During the first execution, when no previous execution timestamp exists, the placeholder resolves to a value from the year 2000, allowing the initial run to retrieve historical data. Subsequent executions use the timestamp of the previous run.

**Examples**:

-   OData filter: `adminData/updatedOn ge ${lastRunTime:ISO}`
-   SQL-based query: `SELECT * FROM accounts WHERE lastUpdated > ${lastRunTime:ISO}`




## lastRunTime Placeholder

The `${lastRunTime:<format>}` placeholder resolves to the timestamp of the last successful action execution using the specified format.

**Supported lastRunTime Formats**


<table>
<tr>
<th valign="top">

**Format**

</th>
<th valign="top">

**Example**

</th>
</tr>
<tr>
<td valign="top">

`${lastRunTime:ISO}`

</td>
<td valign="top">

2026-07-05T14:30:00.000Z

</td>
</tr>
<tr>
<td valign="top">

`${lastRunTime:unix}`

</td>
<td valign="top">

1783261800

</td>
</tr>
<tr>
<td valign="top">

`{lastRunTime:unixms}`

</td>
<td valign="top">

1783261800000

</td>
</tr>
<tr>
<td valign="top">

`${lastRunTime:yyyy-MM-dd}`

</td>
<td valign="top">

2026-07-05

</td>
</tr>
<tr>
<td valign="top">

`${lastRunTime:yyyy-MM-dd HH:mm:ss}`

</td>
<td valign="top">

2026-07-05 14:30:00

</td>
</tr>
<tr>
<td valign="top">

`${lastRunTime:yyyyMMdd'T'HHmmss'Z'}`

</td>
<td valign="top">

20260705T143000Z

</td>
</tr>
<tr>
<td valign="top">

`${lastRunTime:dd/MM/yyyy}`

</td>
<td valign="top">

05/07/2026

</td>
</tr>
</table>



## now Placeholder

The `${now:<format>}` placeholder resolves to the current date and time.

It supports the same format options as `${lastRunTime:<format>}`.


<table>
<tr>
<th valign="top">

**Format**

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

$\{now:ISO\}

</td>
<td valign="top">

2026-07-06T14:30:00.000Z

</td>
</tr>
<tr>
<td valign="top">

$\{now:unix\}

</td>
<td valign="top">

1783348200

</td>
</tr>
<tr>
<td valign="top">

$\{now:unixms\}

</td>
<td valign="top">

1783348200000

</td>
</tr>
<tr>
<td valign="top">

$\{now:yyyy-MM-dd\}

</td>
<td valign="top">

2026-07-06

</td>
</tr>
<tr>
<td valign="top">

$\{now:yyyy-MM-dd'T'HH:mm:ss'Z'\}

</td>
<td valign="top">

2026-07-06T14:30:00Z

</td>
</tr>
</table>

