<!-- loiode1ed4742dec44088236131e239df8b9 -->

# Create a Structure for an Analytic Model

In order to create restrictions and calculations across all measures of an analytic model, you can create structures.



## Context

Structures help you to save time and ensure consistency in your calculations, as you don’t need to create a formula/calculation for each measure. In the data preview, the structure members are displayed in their own section. When you use a structure member in the drill-down of a preview, the restriction and calculations defined in the structure member will be applied to each measure. Structures can also be used and enhanced in SAP Analytics Cloud. See

-   [Add Structures/Cross Calculations to Charts](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/154158a69a6e4dbb9695e4944a9c8d40.html)
-   [Create Restricted Accounts in Charts \(Optimized\)](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/4966dd9e4aea4182ad4aa3ee3e511489.html)
-   [Use Input Controls: Dimension, Account, Measure, or Structure](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/90e079eac7ff416daaab96346d830c48.html)

You can create one structure with multiple members for one analytic model.

In case the analytic model has measures and a structure, and both contain calculations or formulas, you can define how the calculations should be prioritized.

> ### Example:  
> You can restrict the country to Germany for all measures in the analytic model with a restricted structure member. If you want to easily apply the same restriction \(like attribute *Country* = Germany\) to all measures \(like value, volume, price, tax amount etc.\) in a table, you can proceed as follows:
> 
> 1.  Create a structure.
> 2.  Add a restricted member with the restriction expression `Country = Germany`.
> 3.  Open the preview.
> 4.  Select all measures for display, and use the structure members in the drill-down.

**Related Information**  


[Create a Calculated Structure Member](create-a-calculated-structure-member-0c30366.md "With a calculated structure member, you can create calculations across all measures of an analytic model.")

[Create a Restricted Structure Member](create-a-restricted-structure-member-1896990.md "With a restricted structure member, you can restrict available dimensions.")

[Configure Collision Handling](configure-collision-handling-025ba2d.md "When the analytic model has measures and at least one structure you need to define how the calculations should be prioritized.")

