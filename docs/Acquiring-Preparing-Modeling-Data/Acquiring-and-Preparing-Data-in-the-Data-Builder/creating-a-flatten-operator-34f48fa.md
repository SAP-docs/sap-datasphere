<!-- loio34f48faf744a429f9db581e5b43b920a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Flatten Operator

Learn how to create a *Flatten* operator in Apache Spark transformation flows to simplify complex star-schema data models. The operator automatically joins tables to create flattened tables for machine learning, AI, and analytics use cases.

The *Flatten* operator is a specialized feature in transformation flow on file that enables data scientists and analysts to create simplified, flattened tables from complex star-schema data models. This operator streamlines data preparation for machine learning, AI use cases, and analytics by automatically joining tables using a left join. Flattened tables can be used to create data products and be consumed in SAP Databricks for machine learning scenarios.

The creation of the *Flatten* operator is only available in *Apache Spark* runtime, but the flattened table can be shared to an *SAP HANA* space. There, you'll be able to use it as a base for analytics scenarios by layering a view and analytical model on the flattened table.



1.  Drag and drop a table with associations onto the source operator, select it to show its context menu, and click the <span class="SAP-icons-V5"></span> Flatten operator to create the flattening operator.

    > ### Note:  
    > The *Flatten* operator:
    > 
    > -   can only be added directly after a source table, and before a *Python* operator or *Remove Duplicate Records* operator.
    > -   prevents the deletion of the source table once the *Flatten* operator is added.
    > -   can only be used once per transformation flow.
    > -   only displays associations with a target entity that's also shared to the current space when used with a shared source.

2.  Select the *Flatten* operator to display its properties in the side panel.
3.  \[optional\] In the *Settings* section, prevent duplicate records in joins by defining a language filter and a key date filter:
    -   Under *Language*, select a value to filter the text association selected in the *Flatten* dialog. You can either select an *Input Parameter* \(`String` data type\) or enter a fixed value \(such as `EN` for English\). This field is required when a text association is selected.
    -   Under *Key Date*, select a value to filter time-dependent data from the association selected in the *Flatten* dialog. You can either select an *Input Parameter* \(*Date* data type\) or use the date selector with one of these options:

        -   *Date*: uses a fixed date from the calendar and runs with the same date every time.
        -   *Today*: uses the current server date during each run.
        -   *Yesterday*: uses the current server date minus one day during each run.

        This field is required when a time-dependent association is selected.


4.  In the *Attributes and Columns* section, you can see the columns coming from the source table. They are shown below their parent table and can be collapsed by clicking <span class="SAP-icons-V5"></span> Expand Node.

    Add or remove columns from associations and the source table by clicking *Edit*. The *Select Associations and Columns* dialog opens:

    -   In the table's *Attributes/Columns* section, you can select or deselect attributes and columns.
    -   In the table's *Association/Dimension* section, you can see all associations and dimensions. This is especially important for shared tables used as a source to know which entities are shared in the space you are currently working on. Click <span class="SAP-icons-V5"></span> Expand Node and see:
        -   In the *Attributes/Columns* section, select or deselect attributes and columns.
        -   In the *Associations/Dimensions* section, expand the entity's associations and dimensions to find related attributes and columns. You can select or deselect them.


    > ### Note:  
    > -   Hierarchical associations and cyclic associations aren't supported and aren't shown.
    > -   The *Association/Dimension* section only shows associations up to five levels.

    Click *Save* to save your changes. The list of columns selected in the *Flatten* operator is updated.

5.  \[optional\] Click <span class="FPA-icons-V3"></span> \(Impact and Lineage Analysis\) to see the lineage of columns selected for your *Flatten* operator.
6.  \[optional\] Edit column names in the source object and in the *Flatten* operator. *Business Names* and *Technical Names* are automatically generated using the column’s path and are shown in the panel. Click *Edit Column* to open the *Edit Column* dialog. You can change the *Business Name* and *Technical Name*, and click *Save*.
7.  \[optional\] You can add a *Python* operator or *Remove Duplicate Records* operator. See [Creating a Python Operator](creating-a-python-operator-a747acf.md) and [Removing Duplicate Records](removing-duplicate-records-d4b2df0.md).
8.  Add a target table by selecting the *Target* node and clicking *Create New Target Table*. The flattened data will be written to this table Provide a technical name for your flattened output.
9.  Click <span class="FPA-icons-V3"></span> \(Save\), <span class="SAP-icons-V5"></span> \(Deploy\), and <span class="FPA-icons-V3"></span> \(Run\) for your transformation flow. You can monitor execution status and verify the output in the target table.
10. After the *Flatten* operator, you can add a *Remove Duplicate Records* operator and a *Python* operator. See [Removing Duplicate Records](removing-duplicate-records-d4b2df0.md) and [Creating a Python Operator](creating-a-python-operator-a747acf.md).
11. \[optional\] After deployment and execution, verify the flattened results:
    -   In the transformation flow side panel, in the *Run Status* section, click *Open in Transformation Flow Monitor* to open the transformation flow in the *Data Integration* monitor. In the flow’s metrics, the type `FLATTEN_OPERATOR_COUNT` has a value set to `1`. See [Metrics for Transformation Flows](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/b42fa5b6f4e04a9491efa9bf7dab0929.html "View metrics for completed transformation flow runs.") :arrow_upper_right:
    -   Navigate to the target table and open *Data Preview* to verify the flattened results. Check that:
        -   All expected columns are present
        -   Language filters are applied correctly
        -   Time-dependent data shows the correct key date values
        -   Joins created a complete left outer join with the main fact table


12. \[optional\] To delete a *Flatten* operator, select the operator and click <span class="FPA-icons-V3"></span> \(Delete\) in its context menu. Deleting the operator allows you to delete the source table again.

