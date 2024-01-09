<!-- loio3f5ba0c5ae3944c1b7279bb989a2a5b5 -->

# Configure Your Replication Flow

Define general settings for your replication flow, such as the load type.



## Procedure

1.  Click *Settings*.

2.  Select the relevant load type for your replication flow:

    -   *Initial Only*: Load all selected data once.

    -   *Initial and Delta*: After the initial load, the system checks for source data changes \(delta\) at regular intervals and copies the changes to the target. The default value for the delta load interval is 60 minutes. You can change it in the *Details* side panel by entering an integer between 0 and 24 for hours and 0 and 59 for minutes, respectively. The maximum allowed value is 24 hours 0 minutes. If you enter 0 hours and 0 seconds, the system replicates any source changes immediately.

        > ### Note:  
        > -   The system load caused by the delta load operations can vary substantially depending on the frequency of changes in your data source in combination with the interval length you define. Make sure that your tenant configuration supports your settings. For more information, see [Configure the Size of your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).
        > 
        > -   The next interval starts after all changes from the previous interval have been replicated. For example, if replicating a set of changes starts at 10:30 a. m. and takes until 10:45 a. m., and you have defined one-hour intervals, the next delta replication starts at 11:45 a. m.

        For more information about using this load type in connection with local tables, see [Capturing Delta Changes in Your Local Table](https://help.sap.com/docs/SAP_DATASPHERE/c8a54ee704e94e15926551293243fd1d/154bdffb35814d5481d1f6de143a6b9e.html).


3.  The *Truncate* setting is relevant if the target structure already exists and contains data. Review the default setting and change it if required:

    -   If *Truncate* is marked for a **database table**, when you start the replication run, the system deletes the table content, but leaves the table structure intact and fills it with the relevant data from the source.

        If not, the system inserts new data records after the existing data in the target. For data records that already exist in the target and have been changed in the source, the system updates the target records with the changed data from the source using the UPSERT mode.

    -   For data store objects \(for example from the data lake component of SAP HANA Cloud\), *Truncate* must always be set. \(If you still try to run a replication flow for an existing target without the *Truncate* option, you get an error message.\) When you start the replication run, the system deletes the object completely \(data and structure\) and re-creates it based on the source data.

    If the target structure does not yet exist or is empty, you can ignore the *Truncate* setting.


