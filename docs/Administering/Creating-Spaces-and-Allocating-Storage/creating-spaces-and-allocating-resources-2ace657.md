<!-- loio2ace657356d54199b0b87d2327b1a70b -->

# Creating Spaces and Allocating Resources

Users with an administrator role can create spaces and allocate resources to them.

All data acquisition, preparation, and modeling in SAP Datasphere happens inside spaces. A space is a secure area - space data cannot be accessed outside the space unless it is shared to another space or exposed for consumption.



You can create spaces with different types of storage:

-   *SAP HANA Database \(Disk and In-Memory\)* - You allocate disk and memory storage, set a priority, and can limit how much memory and how many threads its statements can consume.
-   *SAP HANA Data Lake Files* \(file spaces\) - You allocate compute resources. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area and are stored in the SAP Datasphere object store.

You can then assign one or more users to the space via scoped roles. The users can start acquiring and preparing data in the space.

If you assign users to a space with a space administrator role, they can manage users, create connections to source systems, secure data with data access controls, and manage other aspects of the space \(see [Managing Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/268ea7e3e8d448deaab420219477064d.html "Users with a space administrator role are responsible for controlling user access to their space, and monitoring and otherwise managing the space.") :arrow_upper_right:\).

