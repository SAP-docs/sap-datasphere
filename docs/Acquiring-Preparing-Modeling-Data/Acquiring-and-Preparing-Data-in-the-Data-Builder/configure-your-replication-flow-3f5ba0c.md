<!-- loio3f5ba0c5ae3944c1b7279bb989a2a5b5 -->

# Configure Your Replication Flow

Define general settings for your replication flow, such as the load type.



## Procedure

1.  Click *Settings*.

2.  Select the relevant load type for your replication flow:

    -   *Initial Only*: Load all selected data once.

    -   *Initial and Delta*: After the initial load, the system checks for source data changes \(delta\) once every 60 minutes and copies the changes to the target.

        For more information about using this load type in connection with local tables, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).


3.  The *Truncate* setting is relevant if the target structure already exists and contains data. Review the default setting and change it if required:

    -   If *Truncate* is marked for a **database table**, when you start the replication run, the system deletes the table content, but leaves the table structure intact and fills it with the relevant data from the source.

        If not, the system inserts new data records after the existing data in the target. For data records that already exist in the target and have been changed in the source, the system updates the target records with the changed data from the source using the UPSERT mode.

    -   For data store objects \(for example from the data lake component of SAP HANA Cloud\), *Truncate* must always be set. \(If you still try to run a replication flow for an existing target without the *Truncate* option, you get an error message.\) When you start the replication run, the system deletes the object completely \(data and structure\) and re-creates it based on the source data.

    If the target structure does not yet exist or is empty, you can ignore the *Truncate* setting.


