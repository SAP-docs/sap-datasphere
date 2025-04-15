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
    -   *Optimize Table*: Improve data access performance by optimizing the layout of data in file storage \(for example by grouping small files into larger files.
    -   *Schedule*: Create, edit, or delete a schedule to automatize, optimize, or merge tasks on regular basis. See [Scheduling Data Integration Tasks](scheduling-data-integration-tasks-7fa0762.md).


*Merge Table* or *Optimize Table* will launch the task in asynchronous mode and will use the settings defined by an administrator, while configuring the file space. You will be notified via the notification area once done.

> ### Note:  
> *Merge Table* and *Optimize Table* can also be run via a task chain. For more information, see [Creating a Task Chain](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right:.
> 
> *Merge Table* can also be automated at a replication flow creation level. For more information, see [Creating a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/25e2bd7a70d44ac5b05e844f9e913471.html "Create a replication flow to copy multiple data assets from a source to a target.") :arrow_upper_right:



<a name="loioe533b154ed3e49ce9a03e4421a5296e7__section_add_rmf_g2c"/>

## Override Default Local Tables \(file\) Optimize and Merge Tasks Resources

When creating a file space, administrators have defined the maximum amount of compute resources that the file space can consume when processing statements in its Apache Spark instance. In the Workload management, they have defined default Apache Spark Applications to run tasks, including merge and optimize tasks. For more information see [Create a File Space to Load Data in the Object Store](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/947444683e524cfd9169d7671b72ba0c.html "Create a file space and allocate compute resources to it. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area and are stored in the SAP Datasphere object store.") :arrow_upper_right:.

However, you can change the maximum amount of compute resource that can get consumed specifically by a local table \(file\):

1.  From the *Local Tables \(file\)* Monitor, select the relevant table.
2.  Click <span class="SAP-icons-V5"></span> \(Details\) to navigate to the details screen of the table.



### Override Resources for all Future Runs

Go to the *Setting* tab and change the default settings of Apache Spark application for next runs:

-   *Use Default*: The default application is the application selected by an administrator during the file space creation..
-   *Define New Setting for This Table*: Select another *Apache Spark Application* that fits your need..



### Override Resources for a Single Run

Navigate to the local table \(files\) run details screen, click *Merge Table* or *Optimize Table*, and then override the default settings, which are provided by the space properties or the current table defaults, if you have set them.

