<!-- loio3c158685865d4b408938a148e828e21f -->

# Extending Intelligent Content

The data products installed via SAP Business Data Cloud as part of intelligent content do not include any extensions defined in your source system. However, you can update the data products in SAP Datasphere to include any required custom fields, and adjust the delivered views and analytic models to consume them.



<a name="loio3c158685865d4b408938a148e828e21f__section_czq_q33_hdc"/>

## Context

If your organization has extended the SAP source system with custom fields in this way, then you will need to copy the preparation and model spaces in order to modify the SAP-managed content and consume the updated data products in your intelligent content.

> ### Note:  
> You must always copy both the preparation and model spaces and complete the entire extension process, so that your copied spaces are entirely independent of the intelligent content's preparation and model spaces. A situation, for example, where objects in a copied content space depend on objects in the intelligent content preparation space, is not supported.

> ### Note:  
> If SAP updates the data products and content, these updates are not made available automatically to your copied space and, therefore, you would need to repeat this process for any updated data products.



## Procedure

1.  Identify all the preparation and model spaces that contain your data product or depend on it.

    In this example, two data products are consumed by views and eventually exposed via analytic models:

    ![](images/Extending_Data_Products_-_first_step_e3a9436.png)

2.  Request a user with the **DW Administrator** role \(or equivalent privileges\) to copy the model space using the *Copy Spaces* wizard, and to select the preparation space as a Source Space in the wizard to ensure that the copied model space will correctly consume data from the copied preparation space.

    > ### Note:  
    > The ingestion space is not intended to be copied, but the copied preparation space will be granted access to the same data products during the space copy process.

    The copied spaces will contain editable versions of all objects by removing them from the protective namespace, transforming `sap.s4.entity` technical names to `sap_s4_entity`.

    For more information, see [Copy Spaces and their Contents](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/73068ac8e1934615b419d8c6c4095a9a.html "You can copy related spaces and the Data Builder objects they contain into new spaces. When selecting a space to copy you can also select some or all of its source spaces (which share data to it), and some or all of its consumer spaces (to which it shares data), in order to create a new stack of spaces sharing data between them, independently of the original spaces.") :arrow_upper_right:.

    In our example, the model and preparation spaces are copied together and the copied model space correctly consumed data from the copied preparation space, while the copied preparation space continues to consume data from the original ingestion space. 

    ![](images/Extending_insight_applications_diagram_-_4_step_3210b62.png)

3.  Request a user with the **DW Administrator** role \(or equivalent privileges\) to add the necessary Modeler users to the new preparation and model spaces.
4.  A user with the *DW Modeler* role \(or equivalent privileges\) reinstalls the data products in the copied preparation space. This updates the data products in the ingestion space to include the custom fields.

    For more information, see [Reinstalling Data Products with Custom Fields](reinstalling-data-products-with-custom-fields-e150cae.md)\).

5.  Modify the objects in the preparation and model spaces, to take into account the new extension fields.

    For more information, see [Process Source Changes in the Graphical View Editor](https://help.sap.com/docs/SAP_DATASPHERE/c8a54ee704e94e15926551293243fd1d/702350c755d24d629545de04673acb1b.html) or [Process Source Changes in the SQL View Editor](https://help.sap.com/docs/SAP_DATASPHERE/c8a54ee704e94e15926551293243fd1d/f7e43ced828940178efb3143c2956d9d.html).

6.  Ensure that the data access controls applied to the fact views are still protecting data appropriately.

    For more information, see [Applying Row-Level Security to Data Delivered through Intelligent Content](applying-row-level-security-to-data-delivered-through-intelligent-content-c83225f.md).

7.  Communicate the new models and fields to the business analyst working in SAP Analytics Cloud. See [Modifying and Sharing Intelligent Content](https://help.sap.com/docs/business-data-cloud/viewing-insight-apps/modifying-and-sharing-insight-apps) for the next steps.

