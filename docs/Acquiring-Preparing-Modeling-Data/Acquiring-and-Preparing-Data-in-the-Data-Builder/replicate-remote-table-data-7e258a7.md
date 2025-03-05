<!-- loio7e258a7554f84bf386c1bb029df5413f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Replicate Remote Table Data

By default, when you import a remote table, its data is not replicated and must be accessed via federation each time from the remote system. You can improve performance by replicating the data to SAP Datasphere and you can schedule regular updates \(or, for many connection types, enable real-time replication\) to keep the data fresh and up-to-date.



## Context

SAP Datasphere is using two types of adaptors to connect to remote tables:

-   SAP HANA smart data integration \(used in connections with *Data Provisioning* option = *Data Provisioning Agent*\).

-   SAP HANA smart data access adaptors \(used in connections with no *Data Provisioning* option or *Data Provisioning* option = *Cloud Connector* or *Direct*\).

> ### Note:  
> If your source data comes from an SAP HANA On-Premise system, select the adaptor following your use case:
> 
> -   You want to access the data remotely: SAP HANA smart data access \(Data Provisioning Option: Direct\) would be the recommended adaptor to read the data. It allows higher degree of query pushdown to the remote database, leading to better response times and less resource consumption.
> -   You want to replicate the data into SAP Datasphere: The preferred option for this is to use Replication Flows, see [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md). In case you require replication for remote tables, SAP HANA smart data integration \(Data Provisioning Option: Data Provisioning Agent\) is the recommended adaptor to push the data. It offers more options when loading the data, such as applying filter conditions or data partitioning.
> 
> For more information on these adaptors, see [Connecting SAP HANA Cloud, SAP HANA Database to Remote Data Sources](https://help.sap.com/docs/HANA_CLOUD/db19c7071e5f4101837e23f06e576495/afa3769a2ecb407695908cfb4e3a9463.html).



## Procedure

1.  Open your remote table in the table editor and scroll to the *Remote* section.

2.  Use the following tools to enable replication:

    -   Click *Table Replication* to:

        -   *Start Data Replication*

            Directly start a copy of the full set of data from the source in the background.

            > ### Note:  
            > If you start data replication on a remote table whose data access is Replicated \(Real-time\), you’ll remove the real-time replication for this table. Your data will no longer be updated in real-time and you’ll have to start a new data replication or create a schedule to get your data updated.

            For more information, see [Replicate Full Set of Data](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/35632cd706474d9796fa5da56ba15c6b.html "Start a data replication to copy the full set of data from your source object (usually a database table or view) into SAP Datasphere.") :arrow_upper_right:.

        -   *Remove Replicated Data*

            Stop replication and delete data from replica table.

            > ### Note:  
            > If you need to remove the replicated data for a remote table whose data access is *Replicated \(Real-time\)*, you must ensure that the following requirements are met to allow a proper deletion:
            > 
            > -   The data provisioning agent is not disconnected.
            > -   The real-time replication is not paused at connection level and is working properly.
            > 
            > If one of the requirement is not met, some objects won't be deleted and you'll have to delete them manually. See [3307334](https://me.sap.com/notes/3307334) for more information.

        -   *Enable Real-Time Data Replication*

            Start replication of data changes in the source in real-time.

            > ### Note:  
            > When enabling the replication in real-time, the data is updated in real-time. You don’t need to start a new data replication or to create a schedule to update your data

            For more information, see [Replicate Data Changes in Real-Time](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/441d327ead5c49d580d8600301735c83.html "Use real-time replication to copy the data changes from your source object in real-time into SAP Datasphere.") :arrow_upper_right:.

        -   *Disable Real-Time Data Replication*

            Disable real-time data replication even if your source system is unreachable and switch the data access from *Replicated \(Real-time\)* to *Replicated \(snapshot\)*. It preserves the replica table and its replicated data to allow further actions on the remote table such as deleting or changing the properties of the connection. For more information, see [Disabling Real-Time Data Replication](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/82380e6f01c84fac898a285ac40a1e50.html "Disable real-time data replication even if your source system is unreachable, and switch the data access from Replicated (Real-time) to Replicated (Snapshot).") :arrow_upper_right:.

            > ### Note:  
            > The remote table must be connected via SAP HANA smart data integration, and must not be connected via SAP HANA smart data access.


    -   Click *Schedule Replication* to:
        -   *Create Schedule*

            Create a schedule to start a data replication in the background according to the settings defined in the schedule.

            > ### Note:  
            > If you create a schedule for a remote table whose data access is *Replicated \(Real-time\)*, the replication type will change from real-time replication to batch replication at the next run of the schedule. The data will no longer be updated in real-time

            For more information, see [Scheduling Data Integration Tasks](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/7fa07621d9c0452a978cb2cc8e4cd2b1.html "Schedule data integration tasks to run periodically at a specified date or time.") :arrow_upper_right:.

        -   *Edit Schedule*

            Change how the schedule is specified, or change the owner of the schedule.

            For more information, see [Take Over the Ownership of a Schedule](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4b660c0395454bd0923f732eef4ee4b2.html "Per default, the user who creates a task schedule owns the schedule which means that the job scheduling component runs the task on the owner's behalf according to the defined schedule. You can assign the ownership of the schedule to yourself.") :arrow_upper_right:.

        -   *Delete Schedule*

            Delete the schedule if required.



3.  \[optional\] You may need to click the *Refresh* tool to refresh the properties in the *Remote* section see [Process Source Changes in the Table Editor](process-source-changes-in-the-table-editor-622328b.md)\). You can, at any time, click <span class="SAP-icons-V5"></span> \(Open Monitor\) and, either navigate to the *Remote Tables* monitor to review details of recent replication runs \(see [Replicating Data and Monitoring Remote Tables](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html "In the Remote Tables monitor, you can find a remote table monitor per space. Here, you can copy data from remote tables that have been deployed in your space into SAP Datasphere, and you can monitor the replication of the data. You can copy or schedule copying the full set of data from the source, or you can set up replication of data changes in real-time via change data capturing (CDC).") :arrow_upper_right:\), or navigate to *Remote Table Statistics* to create or review existing statistics for the remote table \(see [Creating Statistics for Your Remote Tables](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e4120bbb98e44994aa1e0b32ff3f209d.html "Create statistics for your remote tables to improve federated query execution.") :arrow_upper_right:\).


