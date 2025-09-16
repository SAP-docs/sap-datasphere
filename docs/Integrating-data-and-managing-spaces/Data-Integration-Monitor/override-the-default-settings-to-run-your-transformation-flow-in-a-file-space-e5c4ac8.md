<!-- loioe5c4ac8ab3bf4573b86cd4f4f3118c16 -->

# Override the Default Settings to Run Your Transformation Flow \(in a File Space\)

Update the maximum amount of compute resources that the file space can consume to run a transformation flow.

When creating a file space, administrators have defined the maximum amount of compute resources that the file space can consume when processing statements in its Apache Spark instance. In the *Workload Management*, they have defined default Apache Spark Applications to run tasks, including transformation flow runs. For more information see [Create a File Space to Load Data in the Object Store](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/947444683e524cfd9169d7671b72ba0c.html "Create a file space and allocate compute resources to it. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area and are stored in the SAP Datasphere object store.") :arrow_upper_right:.

However, you can change the maximum amount of compute resources that can get consumed specifically by one transformation flow.

From the details screen of the relevant transformation flow, go to the *Apache Spark Application Settings* tab and update the settings that must be used to run your transformation flow:

-   *Use Default*: The default application is the application selected by an administrator during the file space creation.
-   *Define New Setting for This Flow*: Select another *Apache Spark Application* that fits your needs.

For more information on transformation flow in a file space, see [Creating a Transformation Flow in a File Space](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/b917baf0431343bea8381fa37e12eeb8.html "Create transformation flows with local tables (file) as sources, apply various transformations, and store the resulted dataset into another local table (file).") :arrow_upper_right:

