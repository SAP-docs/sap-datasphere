<!-- loio872ad509995a451890bf8b80b73ec0e6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Delete Data From Your Local Tables \(File\)

Delete records or versions of a local table \(File\), creating a direct task or using a schedule, and free up storage allocating the required amount of compute resources that the file space can consume when processing these tasks.

Local Tables \(File\) store large amount of data, including delta capture changes and historical data. When data is updated, the information is kept on your local table \(file\) with the delta changes columns, and a new version is stored in the object store. Keeping all these records and versions consume a lot of memory, and can impact performance. You must clean them up on regular basis to ensure to keep control on your costs and to improve performance while reading your local tables \(file\).

> ### Note:  
> To delete local table \(file\) records, you must have a scoped role that grants you access to a space with one of the following privileges:
> 
> -   Data Warehouse Data Integration \(--U-E---\) – The DW Integrator role template, for example, grants this privilege.
> 
> The "Update" permission allows you to directly run the records deletion, and the "Execute" permission to schedule it. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:



<a name="loio872ad509995a451890bf8b80b73ec0e6__section_nm1_ghy_mgc"/>

## Run a Direct Data Deletion Task

You can start an immediate task to delete the data:

1.  From the *Data Integration Monitor*, navigate to the *Local Tables \(File\)* monitor.
2.  Select the relevant local table \(file\) and click <span class="SAP-icons-V5"></span> \(Details\) to navigate to the details screen of the selected table.
3.  Click *Delete Records* and choose the desired option:
    -   *Delete All Records*: Records will not be physically deleted but marked as deleted and filtered out when accessing the active records of the local table. They will still consume storage, and they can still be processed by other apps that consume them.
    -   *Delete Filtered Records*: You define filter criteria, and the records will be marked as deleted according to this filter. They will be filtered out when accessing the active records of the local table. They will still consume storage, and they can still be processed by other apps that consume them.
    -   *Delete Previous Versions*: You delete previous versions, which are older than the number of days you have specified. Records that meet your defined criteria will be permanently deleted. Default value is 90 days. Minimum authorized value is 7 so that records from the last 7 days cannot be deleted. In addition, only records that have been fully processed can be deleted.

        > ### Note:  
        > 7 days means start time of the task - 169 hours \(7 days X 24 hours + 1hour\). For more information about the 7 retention days and vacuum, see [Remove files no longer referenced by a Delta table](https://docs.delta.io/latest/delta-utility.html#remove-files-no-longer-referenced-by-a-delta-table)


4.  \[Optional\] When you select one of these options, you can override the default *Apache Spark Application Settings* that were defined at space creation by your administrator:
    -   *Use Default*: The default application is the application selected in the table settings. If no default application is defined there, the application selected by an administrator during the file space creation is used.
    -   *Define New Setting for This Table*: Select another *Apache Spark Application* that fits your needs.

5.  Click *Delete* to start the deletion task.

    > ### Note:  
    > You can automate the deletion of data records using a task chain. For more information, see [Creating a Task Chain](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right:.




<a name="loio872ad509995a451890bf8b80b73ec0e6__section_rgv_wpy_mgc"/>

## Schedule a Data Deletion Task

You can automate your data deletion with a schedule to clean up your data on regular basis.

To create a data deletion schedule:

1.  From the *Data Integration Monitor*, navigate to the *Local Tables \(File\)* monitor.
2.  Select the relevant local table \(file\) and click <span class="SAP-icons-V5"></span> \(Details\) to navigate to the details screen of the selected table.
3.  Click *Schedule* \> *Create Deletion Schedule*.
4.  Define a business name and a technical name for your schedule, and choose the desired options to be used to delete your data:
    -   *Delete All Records*: Records will not be physically deleted but marked as deleted and filtered out when accessing the active records of the local table. They will still consume storage, and they can still be processed by other apps that consume them.
    -   *Delete Filtered Records*: You define filter criteria, and the records will be marked as deleted according to this filter. They will be filtered out when accessing the active records of the local table. They will still consume storage, and they can still be processed by other apps that consume them.
    -   *Delete Previous Versions*: You delete previous versions, which are older than the number of days you have specified. Records that meet your defined criteria will be permanently deleted. Default value is 90 days. Minimum authorized value is 7 so that records from the last 7 days cannot be deleted. In addition, only records that have been fully processed can be deleted.

        > ### Note:  
        > 7 days means start time of the task - 169 hours \(7 days X 24 hours + 1hour\). For more information about the 7 retention days and vacuum, see [Remove files no longer referenced by a Delta table](https://docs.delta.io/latest/delta-utility.html#remove-files-no-longer-referenced-by-a-delta-table)


5.  Click *Next* and define your schedule. For more information, see [Scheduling Data Integration Tasks](scheduling-data-integration-tasks-7fa0762.md).
6.  Click *Next* and review your settings.
7.  Click *Create Schedule*.

