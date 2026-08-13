<!-- loio0cbcc49d36f345208ffd97d3695a141e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Resolving Erroneous Records Using the Data Remediation Table

Automatically identify and flag erroneous records without stopping your transformation flow with the *Data Remediation* table.

Data quality issues can create problems after running a transformation flow. Common errors include negative or invalid values \(e.g., negative ages\), null or missing values, inconsistent data \(e.g., admission dates after discharge dates\), and business logic violations. Enabling *Support Data Validation* and using the *Data Remediation* table help you correct these erroneous records in future runs.

The *Data Remediation* table is a read-only system-managed local table \(file\) owned by the transformation flow when *Support Data Validation* is enabled. Its schema mirrors the incoming records of the associated Python operator, with two additional technical columns:

-   *\_DRT\_Status*: Tracks record state:
    -   0 = erroneous record.
    -   1 = corrected and ready for reprocessing.

-   *\_DRT\_MESSAGE*: Holds a user-defined error description set at capture time.

The *Data Remediation* table functions as a source or target in other transformation flows and supports standard table lifecycle operations. Corrected records are integrated during the subsequent transformation flow execution. The merge behavior varies based on load type:

-   *Initial and Delta*: Corrected records merge only when the next run detects source changes.
-   *Initial*: Corrected records in the Data Remediation table override incoming source data. Clear the Data Remediation table before initiating an initial load to avoid overwriting valid records with erroneous data.
-   *Delta*: If a corrected record in the Data Remediation table has been subsequently updated or deleted at the source, the more recent source state is preserved rather than being overridden.

> ### Note:  
> -   *Data Remediation* tables cannot be used as a source or target table in a replication flow.
> -   Resetting the transformation flow watermark deletes all records from the *Data Remediation* table. See [Watermarks](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/890897f00a4944c7a6f90d3816a8d4c6.html "When you run a transformation flow that loads delta changes to a target table, the system uses a watermark (a timestamp) to track the data that has been transferred.") :arrow_upper_right:.
> -   Only one *Data Remediation* table can be created per Python node and per transformation flow.



## Correction for Few Records

1.  Click the run status *Completed \(with Flagged Records\)* to open the transformation flow in the *Data Integration* monitor.
2.  In the *Data Validation* tab, select the Python operator *Python1* to view flagged records. The flagged records are shown on the *Data Remediation* table.
3.  In the *Data Remediation* table, you can click:
    -   *Resolve All* to mark all flagged records as resolved without making corrections. To use only if the flagged records are valid.
    -   *Edit* to manually correct erroneous values.
    -   *Save* to save your changes.
    -   *Cancel* to discard unsaved changes.
    -   <span class="SAP-icons-V5"></span> \(Refresh\) to refresh the data displayed in the panel.
    -   :gear: to open the *Settings* dialog \(see [Choose Columns to Display](../viewing-object-data-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_columns)\).

4.  \[optional\] You can remove unnecessary records from the *Data Remediation* table by deleting them in the *Local Table \(File\)* monitor in the *Data Integration Monitor*. See [Delete Data From Your Local Tables (File)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/872ad509995a451890bf8b80b73ec0e6.html "Delete records or versions of a local table (File), creating a direct task or using a schedule, and free up storage by allocating the required amount of compute resources that the file space can consume when processing these tasks.") :arrow_upper_right:.
5.  Save changes and run the flow again. The corrected records are merged into the target table during the next run.



## Mass Correction for Many Records

For large volumes of flagged records, create a secondary transformation flow with correction logic:

1.  Create a new transformation flow. See [Creating a Transformation Flow in a File Space](creating-a-transformation-flow-in-a-file-space-b917baf.md).
2.  Use the *Data Remediation* table as both source and target.
3.  Add a Python operator between them. Keep the *Support Data Validation* toggle disabled in the Python node properties side panel.
4.  Click *Edit* in the *Script* section and implement your correction code.

    You must explicitly set the value of the`_DRT_STATUS` to `1` in the Python code to mark the records as resolved.

    > ### Example:  
    > For example, you can fix negative values, standardize formats, correct dates - EXAMPLE REQUIRED FROM DEV

    Corrected records are stored in the *Data Remediation* table and automatically included in the next main flow run.

5.  Save and run the flow.



Check the transformation flow's *Run Details* in the *Data Integration* monitor to see how many records were written to the target table.



## Data Remediation Table Deletion

The *Data Remediation* table is automatically deleted:

-   Turning off the *Support Data Validation* toggle on a Python operator deletes the *Data Remediation* table during the next deployment of the transformation flow.
-   Removing the Python operator from your transformation flow deletes its associated *Data Remediation* table.
-   Deleting a transformation flow that has *Support Data Validation* enabled also deletes the *Data Remediation* table.

If the *Data Remediation* table to be deleted is consumed in other flows or views, disable or remove those dependencies first to prevent downstream failures. Before the deletion of the table, ensure that:

-   The table is not being used as a source or target in any other transformation flows.
-   The table is not referenced in any views or reports.
-   The flagged records have been corrected or resolved and aren't required anymore.

> ### Note:  
> If you plan to disable *Support Data Validation* temporarily, consider exporting or backing up corrected records before.

