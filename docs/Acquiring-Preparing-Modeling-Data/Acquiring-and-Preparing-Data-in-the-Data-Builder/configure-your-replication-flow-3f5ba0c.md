<!-- loio3f5ba0c5ae3944c1b7279bb989a2a5b5 -->

# Configure Your Replication Flow

Define general settings for your replication flow, such as the load type.



## Procedure

1.  Click *Settings*.

2.  Select the relevant load type for your replication flow:

    -   *Initial Only*: Load all selected data once.

    -   *Initial and Delta*: After the initial load, the system checks for source data changes \(delta\) once every 60 minutes and copies the changes to the target.


3.  The *Truncate* setting is relevant if the target structure already exists and contains data. Review the default setting and change it if required:

    -   If *Truncate* is marked for a **database table**, when you start the replication run, the system deletes the table content, but leaves the table structure intact and fills it with the relevant data from the source.

        If not, the system tries to insert the data from the source after the existing data in the target, which can lead to issues with duplicate values in key fields.

    -   If *Truncate* is marked for a **data store table** \(such as SAP HANA Cloud, Data Lake\), when you start the replication run, the system deletes the table completely \(data and structure\) and re-creates it based on the source data.

        If not, the system inserts the data from the source after the existing data in the target, which is the desired behavior for these tables in the majority of cases.


    If the target structure does not yet exist or is empty, you can ignore the *Truncate* setting.


