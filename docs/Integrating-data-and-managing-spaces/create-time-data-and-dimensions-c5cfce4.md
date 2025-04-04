<!-- loioc5cfce4d22b04650b2fd6078762cdeb9 -->

# Create Time Data and Dimensions

Create a time table and dimension views in your space to provide standardized time data for your analyses. The time table contains a record for each day in the specified period \(by default from 1900 to 2050\), and the dimension views allow you to work with this date data at a granularity of day, week, month, quarter, and year, and to drill down and up in hierarchies.



<a name="loioc5cfce4d22b04650b2fd6078762cdeb9__prereq_xfq_31j_42c"/>

## Prerequisites

To work with the time table and dimensions in your space, you must have a scoped role that grants you access to your space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-R------`\) - To open your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.
-   *Data Warehouse Data Builder* \(`-RUD----`\) - To read, update and delete objects in the *Data Builder*.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

> ### Note:  
> Relevant only for spaces with a storage type *SAP HANA Database \(Disk and In-Memory\)*, and not for *SAP HANA Data Lake Files* spaces.



## Procedure

1.  In the side navigation area, click ![](Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.

2.  In the *Time Data* section, click *Create Time Tables and Dimensions* to open the dialog.

    The dialog lists all the objects that will be created:

    -   *Time Table* - A table containing one record for each day from, by default, the year 1900 to the year 2050.
    -   Four views with a semantic usage of *Dimension*:
        -   *Time Dimension - Day* - Suitable for an association from a column containing dates in the form `Dec 31, 2020`, and providing hierarchies with levels:

            -   Year, Quarter, Month, Day
            -   Year, Month, Day
            -   Year, Week, Day

            > ### Note:  
            > Monday is identified as `00` in the *Day of Week* column.

        -   *Time Dimension - Month* - Suitable for an association from a column containing months in the form `202012` \(for December 2020\), and providing hierarchies with levels:
            -   Year, Quarter, Month
            -   Year, Month

        -   *Time Dimension - Quarter* - Suitable for an association from a column containing quarters in the form `20204` \(for the fourth quarter of 2020\), and providing one hierarchy with levels:
            -   Year, Quarter

        -   *Time Dimension - Year* - Suitable for an association from a column containing years in the form `2020`.

    -   Three translation tables - which contain the names of days, months, and quarters in English, French, German, and Spanish.

3.  \[optional\] Modify the values in any of the following fields:

    -   Enter different years in the *From Year* and *To Year* fields to expand or reduce the scope of the time table data.

        > ### Note:  
        > The *To Year* cannot be more than 100 years later than the current year.

    -   Edit any of the proposed business names for the tables and views to be created. The technical names cannot be modified.

4.  Click *Create*.

    When creation is complete, the content of the section changes to show that the objects are now present in the space. You can use the tools to edit the *Time Table* values, refresh the time data, or delete these entities.

    > ### Note:  
    > From v2023.08, we use the `ISOWEEK()` function to generate ISO-standard year and week numbers \(see [ISOWEEK Function \(Datetime\)](https://help.sap.com/docs/SAP_HANA_PLATFORM/4fe29514fd584807ac9f2a04f6754767/20e23edc7519101482eae3271722de36.html) in the *SAP HANA Platform* documentation. To regenerate time data generated before this version, click *Edit*, modify your *From Year* or *To Year*, and click *Save*.

    The tables and views are listed with your other space objects and can be opened \(in read-only form\) from the *Data Builder* and *Repository Explorer*.

    Users assigned to your space can now use the views as dimensions by creating associations to them from their entities containing time data.


