<!-- loiof0a0e4cace7c4ebd8fabd036638e0f9d -->

# Object Lifecycles and Dependencies

In SAP Datasphere, data is loaded via flows or other methods into tables and then consumed in views and other types of objects, before being exposed for consumption in clients, tools, and apps. We provide various tools to help you ensure that your objects are valid and correctly deployed, and to understand and manage the dependencies between them.

This topic contains the following sections:

-   [Save, Validate, and Deploy Objects](object-lifecycles-and-dependencies-f0a0e4c.md#loiof0a0e4cace7c4ebd8fabd036638e0f9d__section_save_validate_deploy)
-   [Understand and Manage Object Dependencies](object-lifecycles-and-dependencies-f0a0e4c.md#loiof0a0e4cace7c4ebd8fabd036638e0f9d__section_dependencies)



<a name="loiof0a0e4cace7c4ebd8fabd036638e0f9d__section_save_validate_deploy"/>

## Save, Validate, and Deploy Objects

Any object can be saved, but only valid objects can be deployed for use in your run-time environment. See:

-   [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md)
-   [Validating Objects](validating-objects-685b1e0.md)



<a name="loiof0a0e4cace7c4ebd8fabd036638e0f9d__section_dependencies"/>

## Understand and Manage Object Dependencies

Objects depend on their sources and on other objects they are associated with. Changing an object that is consumed by other objects may break those consumer objects. Be aware of object dependencies and ensure that changes you make can be communicated to and managed by consumers. See:

-   [Packages](packages-a806c67.md)
-   [Impact and Lineage Analysis](impact-and-lineage-analysis-9da4892.md)
-   [Modifying Objects That Have Dependent Objects](modifying-objects-that-have-dependent-objects-f315863.md)
-   [Deleting Objects](deleting-objects-1e69cbb.md)

