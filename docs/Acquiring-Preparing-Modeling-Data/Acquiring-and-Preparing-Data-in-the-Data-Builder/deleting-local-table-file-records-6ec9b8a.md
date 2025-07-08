<!-- loio6ec9b8a89dc64b5cac069cee81399c92 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Deleting Local Table \(File\) Records

Delete records from a local table \(File\) and free up storage through housekeeping on obsolete or already processed data changes.



<a name="loio6ec9b8a89dc64b5cac069cee81399c92__section_dq3_wvs_g2c"/>

## Prerequisites

To delete local table \(file\) records, you must have a scoped role that grants you access to a space with one of the following privileges:

-   **Data Warehouse Data Integration** \(--U-E---\) – The **DW Integrator** role template, for example, grants this privilege.
-   **Data Warehouse Consumption** \(--U-E---\) – The **DW Modeler** role template, for example, grants this privilege.

    > ### Note:  
    > For both privileges, the "Update" permission allows you to directly run the records deletion, and the "Execute" permission to schedule it.


For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:.



Local Tables \(File\) store large amount of data, including historical data. When data is updated, a new version is stored in the object store. Keeping all these versions consume a lot of memory, and can affect performance. You must clean them up once they have been consumed by flows to optimize storage costs and improve performance while reading your local tables \(file\).

> ### Note:  
> This activity of deleting previous versions of data is called "VACUUM\_FILES" in the *System Monitor* and "vacuum" in some logs messages.

1.  From the *Data Builder*, open your local table \(file\) in the *Table Editor*.
2.  Select from the toolbar, <span class="FPA-icons-V3"></span> \(Delete Data From Table\).
3.  Choose one of the 2 available options:

    -   *Delete All Records \(Mark as Deleted\)*: Records will not be physically deleted but marked as deleted and filtered out when accessing the active records of the local table. They will still consume storage, and they can still be processed by other apps that consume them.
    -   *Delete previous versions \(Vacuum\), which are older than the specified number of days*: Records that meet your defined criteria will be permanently deleted. Default value is 90 days. Minimum authorized value is 7 so that records from the last 7 days cannot be deleted. In addition, only records that have been fully processed can be deleted.

        > ### Note:  
        > 7 days means start time of the task + 169 hours \(7 days X 24 hours + 1hour\). For more information about the 7 retention days and vacuum, see [Remove files no longer referenced by a Delta table](https://docs.delta.io/latest/delta-utility.html#remove-files-no-longer-referenced-by-a-delta-table)

        > ### Example:  
        > If I decide to start the vacuum activity today February 4 at 10:00 am, and set the minimum value to 7 days, records inserted or changed between February 3, 10:00 am and February 10, 11:00 am won’t be deleted.


    \[Optional\]. When you select one of these options, you can override the default *Apache Spark Application Settings* that were defined at space creation by your administrator:

    -   *Use Default*: The default application is the application selected by an administrator during the file space creation.
    -   *Define New Setting for This Table*: Select another *Apache Spark Application* that fits your need.

4.  Confirm with *Delete* to start the deletion task.

    > ### Note:  
    > You can automate the deletion of data records using a task chain.
    > 
    > For more information, see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md).


