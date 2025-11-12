<!-- loiobbedad63821443518fcd8fe56f7d26f7 -->

# Folders

You can create folders to organize the objects in your spaces.

This topic contains the following sections:

-   [Introduction to Folders](folders-bbedad6.md#loiobbedad63821443518fcd8fe56f7d26f7__section_intro)
-   [Create a Folder](folders-bbedad6.md#loiobbedad63821443518fcd8fe56f7d26f7__section_create)
-   [Move Objects into a Folder](folders-bbedad6.md#loiobbedad63821443518fcd8fe56f7d26f7__section_move)
-   [Delete a Folder](folders-bbedad6.md#loiobbedad63821443518fcd8fe56f7d26f7__section_delete)



<a name="loiobbedad63821443518fcd8fe56f7d26f7__section_tdy_tjz_wgc"/>

## Prerequisites

To create folders in the *Repository Explorer*, *Data Builder*, or *Business Builder* to organize the objects in their spaces, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Folder* \(`C-UD----`\) - To create, manage and delete folders.
-   *Spaces Files* \(`-R------`\) - To access objects in a space.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, move and delete folders in the *Data Builder*.
-   *Data Warehouse Business Builder* \(`CRUD----`\) - To create, move and delete folders in the *Business Builder*.

    > ### Note:  
    > You can create, move or delete a folder in the *Repository Explorer*, *Data Builder*, or *Business Builder* and it is immediately taken into account across each of these apps even if the scoped role does not grant access to all of these apps.


The *DW Modeler* role template, for example, grants these privileges \(see [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right: and [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right:\).



<a name="loiobbedad63821443518fcd8fe56f7d26f7__section_intro"/>

## Introduction to Folders

Folders help to organize objects in your space. You can create a folder in the *Repository Explorer*, *Data Builder*, or *Business Builder* and it is immediately available across each of these apps.

![](images/Folders_Example_a96c940.png)

Once a folder is created, you can move objects to it or create objects in it. You can create as many levels of folder as necessary.

> ### Note:  
> Each object in a space must have a unique technical name. You may not create two views with the name *Sales\_US* in the *Sales* space, even if they are saved in different folders.



<a name="loiobbedad63821443518fcd8fe56f7d26f7__section_create"/>

## Create a Folder

You can create folders:

-   In the *Repository Explorer*, click *Create* \> *Folder*, select a space if necessary, enter a name, and click *Create*.
-   In the *Data Builder*, click *Create* \> *Folder*, enter a name, and click *Create*.
-   In the *Business Builder*, click *Folder* \> *New Folder*, enter a name, and click *Create*.



<a name="loiobbedad63821443518fcd8fe56f7d26f7__section_move"/>

## Move Objects into a Folder

You can move objects into folders:

-   In the *Repository Explorer*, select the objects you want to move, click *Move To*, select your target folder, and click *Move*.
-   In the *Data Builder*, select the objects you want to move, click *Move To*, select your target folder, and click *Move*.
-   In the *Business Builder*, select the objects you want to move, click *Folder* \> *Move*, select your target folder, and click *Apply*.

> ### Note:  
> You cannot move objects that are shared to your space into folders.



<a name="loiobbedad63821443518fcd8fe56f7d26f7__section_delete"/>

## Delete a Folder

You can delete folders:

-   In the *Repository Explorer*, select the folders you want to delete, click *Delete*, and then click *Delete* again to confirm the deletion.
-   In the *Data Builder*, select the folders you want to delete, click *Delete*, and then click *Delete* again to confirm the deletion..
-   In the *Business Builder*, select the folders you want to delete, click *Delete*, and then click *Delete* again to confirm the deletion.

> ### Note:  
> Deleting a folder will delete all its contents. This action cannot be undone.

