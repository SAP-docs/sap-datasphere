<!-- loio7e258a7554f84bf386c1bb029df5413f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Replicate Remote Table Data

By default, when you import a remote table, its data is not replicated and must be accessed via federation each time from the remote system. You can improve performance by replicating the data to SAP Datasphere and you can schedule regular updates \(or, for many connection types, enable real-time replication\) to keep the data fresh and up-to-date.



## Context



## Procedure

1.  Open your remote table in the table editor and scroll to the *Remote* section.

2.  Use the following tools to enable replication:

    -   Click *Table Replication* to:

        -   *Load New Snapshot*:

            Directly start a copy of the full set of data from the source in the background.

            For more information, see [Replicate Full Set of Data](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/35632cd706474d9796fa5da56ba15c6b.html "Use snapshot replication to copy the full set of data from your source object (usually a database table or view) into SAP Datasphere.") :arrow_upper_right:.

        -   *Remove Replicated Data*:

            Stop replication and delete data from replica table.

        -   *Enable Real-Time Access*:

            Start replication of data changes in the source in real-time.

            For more information, see [Replicate Data Changes in Real-Time](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/441d327ead5c49d580d8600301735c83.html "Use real-time replication to copy the data changes from your source object in real-time into SAP Datasphere.") :arrow_upper_right:.


    -   Click *Schedule Replication* to:
        -   *Create Schedule*:

            Create a schedule to run snapshot replication in the background according to the settings defined in the schedule.

            For more information, see [Scheduling Data Integration Tasks](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/7fa07621d9c0452a978cb2cc8e4cd2b1.html "Schedule data integration tasks to run periodically at a specified date or time.") :arrow_upper_right:.

        -   *Edit Schedule*:

            Change how the schedule is specified, or change the owner of the schedule.

            For more information, see [Take Over the Ownership of a Schedule](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4b660c0395454bd0923f732eef4ee4b2.html "Per default, the user who creates a task schedule owns the schedule which means that the job scheduling component runs the task on the owner&apos;s behalf according to the defined schedule. You can assign the ownership of the schedule to yourself.") :arrow_upper_right:.

        -   *Delete Schedule*:

            Delete the schedule if required.



3.  \[optional\] You may need to click the *Refresh* tool to refresh the properties in the *Remote* section see [Process Source Changes in the Table Editor](process-source-changes-in-the-table-editor-622328b.md)\). You can, at any time, click <span class="SAP-icons"></span> \(Open Monitor\) and, either navigate to the *Remote Table Monitor* to review details of recent replication runs \(see [Replicating Data and Monitoring Remote Tables](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html "In the Data Integration Monitor, you can find a remote table monitor per space. Here, you can copy data from remote tables that have been deployed in your space into SAP Datasphere, and you can monitor the replication of the data. You can copy or schedule copying the full set of data from the source, or you can set up replication of data changes in real-time via change data capturing (CDC).") :arrow_upper_right:\), or navigate to *Remote Table Statistics* to create or review existing statistics for the remote table \(see [Creating Statistics for Your Remote Tables](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e4120bbb98e44994aa1e0b32ff3f209d.html "Create statistics for your remote tables to improve federated query execution.") :arrow_upper_right:\).


