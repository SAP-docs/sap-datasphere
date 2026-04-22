<!-- loioe533b154ed3e49ce9a03e4421a5296e7 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Merge or Optimize Your Local Tables \(File\)

Local Tables \(File\) can store large quantities of data in the object store. You can manage this file storage with merge or optimize tasks, and allocate the required amount of compute resources that the file space can consume when processing these tasks.



<a name="loioe533b154ed3e49ce9a03e4421a5296e7__section_jj5_ryf_s2c"/>

## Run an Optimize or Merge Task

You can optimize or update your local table \(file\) data:

1.  From the *Data Integration Monitor*, navigate to the *Local Tables \(file\)* Monitor.
2.  Select the relevant table
3.  Click:
    -   *Merge Table*: Add, update or delete data into the existing local table \(file\). Data updates are pushed by a replication flow or SAP BW to the inbound buffer \(specific folder in file storage\) of a target local table \(file\). To process data updates from this inbound buffer to the local table \(file\), and therefore make data visible, a merge task has to run.

        > ### Note:  
        > The *Merge Data Automatically* option is *disabled* by default when creating a new replication flow with SAP Datasphere as the target and the load type set to *Initial and Delta*. For replication flows created before the option was available, you can still manually enable it \(a redeployment will be needed\). In addition, it is possible to merge new data less frequently by either adjusting the delta load interval of a replication flow, or by leaving this setting disabled and running the merge task separately with a less frequent schedule. Note also that when the option *Merge Data Automatically* is enabled, an automatic task is started, therefore you must make sure that you have authorized SAP Datasphere to run tasks on your behalf. Go to your profile settings and give your consent under *Authorized Consent Settings*. For more information, see [Changing SAP Datasphere Settings](https://help.sap.com/viewer/d4f3c5a0bb074d09ae9b42b2b9bd7a08/cloud/en-US/1084796d09464e78870f32cab8584dfc.html "To view and edit your user profile settings, click your user icon in the shell bar and select Settings. You can control various aspects of the user experience of SAP Datasphere and set data privacy and task scheduling consent options.") :arrow_upper_right:.

    -   *Optimize Table*: Improve data access performance by optimizing the layout of data in file storage \(for example by grouping small files into larger files\).

        > ### Note:  
        > The frequency you use this option depends on how frequently the data are written, queried, and how critical query performance is. A common practice is to run it weekly \(for example, at weekends\). However, the best schedule depends on the workload.
        > 
        > Here are some best practices you can consider:
        > 
        > -   When data are written daily or hourly, it creates small files that can accumulate quickly. It is then better to consider running the optimize task daily or every few days.
        > -   If queries are read-heavy on the tables \(large scans\), more frequent optimization will improve the performance.
        > -   For very large tables \(TBs–PBs\), these can benefit from partition-level optimization on a schedule.
        > -   You must consider the cost behind the optimize task: Running off-peak \(nights/weekends\) helps reduce cluster costs.
        > 
        > An Optimize task can be coupled with the z-ordering feature.

    -   *Schedule*: Create, edit, or delete a schedule to automate, optimize, or merge tasks on regular basis. See [Scheduling Data Integration Tasks](scheduling-data-integration-tasks-7fa0762.md).


*Merge Table* or *Optimize Table* will launch the task in asynchronous mode and will use the settings defined by an administrator, while configuring the file space. You will be notified via the notification area once done.

> ### Note:  
> *Merge Table* and *Optimize Table* can also be run via a task chain. For more information, see [Creating a Task Chain](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right:.
> 
> *Merge Table* can also be automated at a replication flow creation level. For more information, see [Creating a Replication Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/25e2bd7a70d44ac5b05e844f9e913471.html "Create a replication flow to copy multiple data assets from a source to a target with support for delta loads.") :arrow_upper_right:

Note also that merge and optimize tasks will run with the default Apache Spark Application defined in space management or per local table \(file\) in the *Data Integration Monitor*. For optimizing the associated workload, please consider adjusting these defaults for your scenario \(see next paragraph\).



<a name="loioe533b154ed3e49ce9a03e4421a5296e7__section_add_rmf_g2c"/>

## Override Default Local Tables \(file\) Optimize and Merge Tasks Resources

When creating a file space, administrators have defined the maximum amount of compute resources that the file space can consume when processing statements in its Apache Spark instance. In the Workload management, they have defined default Apache Spark Applications to run tasks, including merge and optimize tasks. For more information see [Create a File Space to Load Data in the Object Store](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/947444683e524cfd9169d7671b72ba0c.html "Create a file space and allocate compute resources to it. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area and are stored in the SAP Datasphere object store.") :arrow_upper_right:.

However, you can change the maximum amount of compute resources that can be consumed specifically by a local table \(file\):

1.  From the *Local Tables \(file\)* Monitor, select the relevant table.
2.  Click <span class="SAP-icons-V5"></span> \(Details\) to navigate to the details screen of the table.



### Override Resources for all Future Runs

Go to the *Settings* tab and change the default settings of Apache Spark application for next runs:

-   *Use Default*: The default application is the application selected in the table settings. If no default application is defined there, the application selected by an administrator during the file space creation is used..
-   *Define New Setting for This Table*: Select another *Apache Spark Application* that fits your needs..



### Override Resources for a Single Run

Navigate to the local table \(files\) run details screen, click *Merge Table* or *Optimize Table*, and then override the default settings, which are provided by the space properties or the current table defaults, if you have set them.



<a name="loioe533b154ed3e49ce9a03e4421a5296e7__section_jyg_xh2_ngc"/>

## Canceling a Running Merge Task

If you have started a merge task, you can cancel it if needed.

From the details screen of the relevant local table \(file\), in the *Logs* section, select the running task and click *Cancel*. The task will stop the merge action, but it will stop it without rolling back the data that has already been processed. The status of the task will be changed to *Failed \(Canceled\)*.



## Resolving Failed Merged Tasks

If you have scheduled regular merge tasks or if you have used the *Merge Data Automatically* option in your replication flows, you can overload the system with many failed merge tasks. Therefore, a threshold of 10 consecutive failed merge runs for local tables \(file\) has been implemented: After reaching that threshold, any further run of a merge task for that Local Table \(File\) will fail immediately \(before creating any Apache Spark workload\) with the status FAILED \(TOO\_MANY\_FAILURES\). To solve the issue, you will have to:

-   Run a direct merge task \(not through a schedule\) either in the *Local Tables \(File\)* monitor or run a manual task chain containing the merge task. For more information, see [Monitoring Local Tables \(File\)](monitoring-local-tables-file-6b2d007.md)
-   Wait until the next available complete merge task is run. The merge is paused for a specified amount of time to prevent system overload. The threshold will be reset, and a new merge action will restart after 100 minutes, following the "too many errors" situation. The next runs will happen after 200 minutes, 300 minutes, 500 minutes, 800 minutes, 1300 minutes, etc.



## Define Z-Order Columns While Running an Optimize Task

While running an optimize task for your local table \(file\), you define z-order columns to use the z-order clustering technique to co-locate the data by columns. This operation does not make data-related changes to the delta table, so a read before and after this operation has the same results. The co-locality is used to reduce the amount of data that needs to be read. You can specify multiple columns for Z-ORDER BY as a comma-separated list. However, the effectiveness of the locality decreases with each additional column.

To define Z-order columns,

1.  From the *Local Tables \(file\)* Monitor, select the relevant table.
2.  Click <span class="SAP-icons-V5"></span> \(Details\) to navigate to the details screen of the table.
3.  Go to the *Settings* tab
4.  Navigate to *Optimize Settings*
5.  Click *Define Z-Order Columns* \(multiple selection is possible\)
6.  Select the relevant columns
7.  Click *OK*

When using z-order columns in the optimize task, it is advised to run an optimize after every merge run of that same local table \(file\). You can for example, modeling this as part of a task chain.

