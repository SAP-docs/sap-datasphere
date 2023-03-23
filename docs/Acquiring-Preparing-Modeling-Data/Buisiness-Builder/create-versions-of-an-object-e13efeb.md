<!-- loioe13efeb33e8940e89acd5d088244d8e8 -->

# Create Versions of an Object

You can create different versions of an object in the Business Builder.



## Context

To guarantee a smooth roll-out of updates to any object without immediately affecting or even breaking fact models, consumption models, or perspectives, you can derive versions of objects.

The versions exist in parallel and are mostly independent from each other. The definition gets cloned once a new version is derived. As a consequence, changes in the new version have no impact on older versions. Older versions can still be adjusted, but likewise, changes to these are not automatically carried over to newer versions.

When several versions of an object exist, you are informed which properties are version-specific, which means that they apply only to the current version, e.g. the mapping of fields for the key definition, or if they are cross-version, which means that they are valid across all version, e.g. the title.

When you add an object to a model, a selection for the version is offered.

There is no activation process for versions which means that models are not auto-upgraded to a newly created version. Instead, you can decide whether and when a model adopts the new version.

Each version has its own life-cycle depicted by a status. This status in combination with the version's description indicates if a version is recommended for usage and signals the user to switch to another version. A wizard assists you in the migration process.



## Procedure

1.  Provide an easy-to-understand title for the new version.

2.  Describe the updates that have been applied in comparison to the former version.

3.  Select the status of the current version:

    -   In Process: The object is being created.
    -   In Validation: The object is being validated.
    -   Ready to Use: The object is validated and ready-to-use.
    -   Deprecated: The object is deprecated.
    -   Discontinued: The object shall not be used any more. Nevertheless, it will be technically available as long as it is in use.


