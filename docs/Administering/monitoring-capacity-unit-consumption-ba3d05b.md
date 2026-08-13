<!-- loioba3d05baac854171914c09d64bed7202 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Monitoring Capacity Unit Consumption

Monitor the number of capacity units consumed each month to track usage patterns and plan resource allocation.



## Prerequisites

To monitor capacity unit consumption, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access *Capacities* in the *Monitoring* app.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



## Context

The *Capacities Monitoring* tool enables users to define a custom date range to analyze capacity unit consumption over a selected period. It provides insights into monthly and daily capacity unit consumption, enabling users to track usage relative to their subscription and download detailed hourly data. These insights support optimized resource allocation and efficient subscription management.

On the *Spaces* tab, users can view and troubleshoot consumption spikes by identifying which spaces contribute to increased usage. It provides a breakdown by space for Premium Outbound Integration, object store usage, and total capacity unit consumption per space.



## Procedure

1.  From the side navigation menu, click :desktop_computer: *\(Monitoring\)* *\>* <span class="SAP-icons-V5"></span> *\(Capacities Monitoring\)* .

    The *Capacities Monitoring* app is shown.

2.  To view capacity unit consumption and other data per space, click the *Spaces* tab.


    <table>
    <tr>
    <th valign="top">

    Column Name
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Technical Name*
    
    </td>
    <td valign="top">
    
    Shows the name of the space where consumption is being tracked.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Used Premium Outbound Volume*
    
    </td>
    <td valign="top">
    
    Shows the amount of outbound data transferred from the space using Premium Outbound Integration, measured in gigabytes for the specified time frame.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Used Object Store Storage*
    
    </td>
    <td valign="top">
    
    Shows the amount of object store storage consumed by the space during the selected time period, measured in terabyte-hours \(TBh\). For example, a space containing 5 GB of data for 709 hours consumes approximately 3.46 TBh. The physical storage remains 5 GB; the 3.46 TBh value represents accumulated storage consumption over time.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Used Object Store Compute*
    
    </td>
    <td valign="top">
    
    Shows the total compute resources used for object store operations, measured in gigabyte-hours \(GBh\) for the specified time frame.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Used Object Store Requests*
    
    </td>
    <td valign="top">
    
    Shows the number of API requests made to the object store by the space in the specified time frame.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Capacity Unit Consumption*
    
    </td>
    <td valign="top">
    
    Shows the number of capacity units consumed by the space across supported services and resources in the specified time frame.
    
    </td>
    </tr>
    </table>
    
3.  To download a CSV file of the consumption, click <span class="SAP-icons-V5"></span>*Download Capacity Metrics as CSV*.

4.  Click <span class="SAP-icons-V5"></span>and select the beginning and end dates for the report.

5.  Click *Download*.

    The following table explains the information is in each column.


    <table>
    <tr>
    <th valign="top">

    Column Heading
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    MEASUREMENT\_PERIOD\_START
    
    </td>
    <td valign="top">
    
    Marks the beginning time period in yyyy-mm-dd hh:mm:ss format. The time data is separated by hour.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    CONSUMED\_BLOCKS
    
    </td>
    <td valign="top">
    
    Shows approximate consumed block hours.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    CONSUMED\_CU
    
    </td>
    <td valign="top">
    
    Shows the approximate consumed capacity units.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    MEASUREMENT\_PERIOD\_END
    
    </td>
    <td valign="top">
    
    Marks the ending time period in yyyy-mm-dd hh:mm:ss format. The time data is separated by hour.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    MEASURE\_NAME
    
    </td>
    <td valign="top">
    
    Shows the type of measure such as THRESHOLD\_MEMORY or PREMIUM\_OUTBOUND.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    OBJECT\_NAME
    
    </td>
    <td valign="top">
    
    Shows the name of the object when the consumption is associated with a specific object.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SPACE\_NAME
    
    </td>
    <td valign="top">
    
    Shows the name of the space when the consumption is associated with a specific object.
    
    </td>
    </tr>
    </table>
    
    The values shown for CONSUMED\_CU and CONSUMED\_BLOCKS are not final and can change. For metrics involving multiple tasks that generate CU consumption, such as Premium Outbound Integration or ECN, the values are approximate due to the concurrent nature of those tasks. When the values in these columns are empty, the cause could be:

    -   The entry did not present any consumption. This situation could happen when there are multiple workflows present, as entries are displayed even though they were not running at the time.
    -   The values are not available because the measurement has not been consolidated yet.

    The CSV file is downloaded, and you can view it in your spreadsheet application.

    > ### Note:  
    > The CSV file contains approximate data that may not reflect the finalized monthly total.


