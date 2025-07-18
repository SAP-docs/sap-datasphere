<!-- loiof414c3d62bfe49b38e2cfdd7b4e7d786 -->

# Allocate Storage to a Space

Use the *Space Storage* properties to allocate disk and memory storage to the space and to choose whether it will have access to the SAP HANA data lake.



<a name="loiof414c3d62bfe49b38e2cfdd7b4e7d786__prereq_a1p_1gd_r2c"/>

## Prerequisites

To allocate disk and memory storage to your space, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-------M`\) - To update all spaces and space properties.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

> ### Note:  
> Relevant only for spaces with a storage type *SAP HANA Database \(Disk and In-Memory\)*, and not for *SAP HANA Data Lake Files* spaces.



## Context

SAP Datasphere supports data tiering using the features of SAP HANA Cloud:

-   Memory Storage \(hot data\) - Keep your most recent, frequently-accessed, and mission-critical data loaded constantly in memory to maximize real-time processing and analytics speeds.

    When you persist a view, the persisted data is stored in memory \(see [Persist Data in a Graphical or SQL View](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/9bd12cf116ae40e09cdba8b60cf75e11.html "Improve the performance while working with views by persisting the view data, and scheduling regular updates to keep your data up-to-date.") :arrow_upper_right:\).

-   Disk \(warm data\) - Store master data and less recent transactional data on disk to reduce storage costs.

    When you load data to a local table or replicate data to a remote table in SAP Datasphere, the data is stored on disk by default, but you can load it in memory by activating the *Store Table Data in Memory* switch \(see [Accelerate Table Data Access with In-Memory Storage](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/407d1dff76a842699ea08c17eb8748dd.html "By default, when you are working in an SAP HANA Cloud, SAP HANA database space, table data is stored on disk. You can improve performance by enabling in-memory storage.") :arrow_upper_right:\).

-   Data Lake \(cold data\) - Store historical data that is infrequently accessed in the data lake. With its low cost and high scalability, the data lake is also suitable for storing vast quantities of raw structured and unstructured data, including IoT data. For more information, see [Integrating Data to and From SAP HANA Cloud Data Lake](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/e84545bd205b4f9f9c1731144c7d3075.html "Users with an administrator role can connect an SAP Datasphere space with SAP HANA Cloud, data lake to store and access large amounts of data.") :arrow_upper_right:.

You can allocate specific amounts of memory and disk storage to a space or disable the *Enable Space Quota* option, and allow the space to consume all the storage it needs, up to the total amount available in your tenant.



<a name="loiof414c3d62bfe49b38e2cfdd7b4e7d786__steps_y55_pm1_wrb"/>

## Procedure

1.  In the side navigation area, click ![](../images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.

2.  Use the *Space Storage* properties to allocate disk and memory storage to the space and to choose whether it will have access to the SAP HANA data lake.


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Space Quota
    
    </td>
    <td valign="top">
    
    Disable this option to allow the space to consume any amount of disk and memory storage up to the total amounts available in your tenant.

    If this option was disabled and then subsequently re-enabled, the *Disk* and *Memory* properties are initialized to the minimum values required by the current contents of the space.

    Default: Enabled
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Disk \(GB\)
    
    </td>
    <td valign="top">
    
    Enter the amount of disk storage allocated in GB. You can use the buttons to change the amount by whole GBs or enter fractional values in increments of 100 MB by hand.

    Default: 2 GB
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Memory \(GB\)
    
    </td>
    <td valign="top">
    
    Enter the amount of memory storage allocated in GB. This value cannot exceed the amount of disk storage allocated. You can use the buttons to change the amount by whole GBs or enter fractional values in increments of 100 MB by hand.

    > ### Note:  
    > The memory allocated is used to store data and is not related to processing memory. For more information on limiting processing memory in a space, see [Set Priorities and Statement Limits for Spaces or Groups](set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md).

    Default: 1 GB
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Use This Space to Access the Data Lake
    
    </td>
    <td valign="top">
    
    Enable access to the SAP HANA Cloud data lake. Only one space can connect to the data lake.

    > ### Note:  
    > Even though the option is available for selection, you should check first that no other space already has access to the data lake. To do so, you can choose the table layout in the *Space Management* overview page and sort on the *Data Lake Access* column.

    Default: Disabled
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > If a space exceeds its allocations of memory or disk storage, it will be locked until a user of the space deletes the excess data or an administrator assigns additional storage. See [Unlock a Locked Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/c05b6a6d06db427dbdd3041d61fd5840.html "When a space exceeds its assigned storage or when the audit logs enabled in the space consume too much disk storage, the space is automatically locked after 60 minutes if you do not free up space.") :arrow_upper_right:.

3.  Click *Save* to save your changes to the space, or *Deploy* to save and immediately make the changes available to users assigned to the space.




<a name="loiof414c3d62bfe49b38e2cfdd7b4e7d786__result_px4_425_4bc"/>

## Results

To view the total storage available and the amount assigned to and used by all spaces, see [Monitoring SAP Datasphere](../Monitoring-SAP-Datasphere/monitoring-sap-datasphere-28910cd.md).

