<!-- loioe533b154ed3e49ce9a03e4421a5296e7 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Merge or Optimize Your Local Tables \(File\)

Local Tables \(File\) can store large quantities of data in the object store. You can manage this file storage with merge or optimize tasks, and allocate the required amount of compute resources that the file space can consume when processing these tasks.



<a name="loioe533b154ed3e49ce9a03e4421a5296e7__section_jj5_ryf_s2c"/>

## Run an Optimize or Merge Task

You can optimize or update your local table \(file\) data:

1.  From the Data Integration Monitor, navigate to the *Local Tables \(file\)* Monitor.
2.  Select the relevant table
3.  Click:
    -   *Merge Table*: Add, update or delete data into the existing local table \(file\). Data updates are pushed by a replication flow or SAP BW to the inbound buffer \(specific folder in file storage\) of a target local table \(file\). To process data updates from this inbound buffer to the local table \(file\), and therefore make data visible, a merge task has to run.

        > ### Note:  
        > The *Merge Data Automatically* option is enabled by default when creating a new replication flow with SAP Datasphere as the target and the load type set to *Initial and Delta*. For replication flows that don’t support this option, you can still manually enable it \(a redeployment will be needed\). In addition, it is possible to merge new data less frequently by either adjusting the delta load interval of a replication flow or by disabling this setting and running the merge task separately with a less frequent schedule.

    -   *Optimize Table*: Improve data access performance by optimizing the layout of data in file storage \(for example by grouping small files into larger files\).

        > ### Note:  
        > The frequence you use this option depends on how frequently the data are written, queried, and how critical query performance is. A common practice is to run it weekly \(for example, at weekends\). However, the best schedule depends on the workload.
        > 
        > Here are some best practices you can consider:
        > 
        > -   When data are written daily or hourly, it creates small files that can accumulate quickly. It is then better to consider running the optimize task daily or every few days.
        > -   If queries are read-heavy on the tables \(large scans\), more frequent optimization will improve the performance.
        > -   For very large tables \(TBs–PBs\), these can benefit from partition-level optimization on a schedule.
        > -   You must consider the cost behind the optimize task: Running off-peak \(nights/weekends\) helps reduce cluster costs.

    -   *Schedule*: Create, edit, or delete a schedule to automate, optimize, or merge tasks on regular basis. See [Scheduling Data Integration Tasks](scheduling-data-integration-tasks-7fa0762.md).


*Merge Table* or *Optimize Table* will launch the task in asynchronous mode and will use the settings defined by an administrator, while configuring the file space. You will be notified via the notification area once done.

> ### Note:  
> *Merge Table* and *Optimize Table* can also be run via a task chain. For more information, see [Creating a Task Chain](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right:.
> 
> *Merge Table* can also be automated at a replication flow creation level. For more information, see [Creating a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/25e2bd7a70d44ac5b05e844f9e913471.html "Create a replication flow to copy multiple data assets from a source to a target.") :arrow_upper_right:

Note also that merge and optimize tasks will run with the default Apache Spark Application defined in space management or per local table \(file\) in the *Data Integration Monitor*. For optimizing the associated workload, please consider adjusting these defaults for your scenario \(see next paragaph\).



<a name="loioe533b154ed3e49ce9a03e4421a5296e7__section_add_rmf_g2c"/>

## Override Default Local Tables \(file\) Optimize and Merge Tasks Resources

When creating a file space, administrators have defined the maximum amount of compute resources that the file space can consume when processing statements in its Apache Spark instance. In the Workload management, they have defined default Apache Spark Applications to run tasks, including merge and optimize tasks. For more information see [Create a File Space to Load Data in the Object Store](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/947444683e524cfd9169d7671b72ba0c.html "Create a file space and allocate compute resources to it. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area and are stored in the SAP Datasphere object store.") :arrow_upper_right:.

However, you can change the maximum amount of compute resource that can get consumed specifically by a local table \(file\):

1.  From the *Local Tables \(file\)* Monitor, select the relevant table.
2.  Click <span class="SAP-icons-V5"></span> \(Details\) to navigate to the details screen of the table.



### Override Resources for all Future Runs

Go to the *Setting* tab and change the default settings of Apache Spark application for next runs:

-   *Use Default*: The default application is the application selected in the table settings. If no default application is defined there, the application selected by an administrator during the file space creation is used..
-   *Define New Setting for This Table*: Select another *Apache Spark Application* that fits your needs..



### Override Resources for a Single Run

Navigate to the local table \(files\) run details screen, click *Merge Table* or *Optimize Table*, and then override the default settings, which are provided by the space properties or the current table defaults, if you have set them.

