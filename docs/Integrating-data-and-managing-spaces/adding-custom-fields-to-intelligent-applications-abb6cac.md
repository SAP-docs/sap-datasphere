<!-- loioabb6cac0b5b940dc9f74edf753751bc6 -->

# Adding Custom Fields to Intelligent Applications

The data products installed via SAP Business Data Cloud as part of an intelligent application do not include any custom fields that are defined in your source system. However, you can add the custom fields to the analytic model.



## Context

Adding custom fields to the analytic model ensures that these fields are visible and accessible to business users. Any custom fields added to the analytic model are also added to the relevant dimension or fact.

The data products installed via SAP Business Data Cloud as part of an intelligent application are delivered via SAP-managed spaces. In SAP-managed spaces, SAP determines which custom fields contained within a data product can be added to the analytic model, thus which entities are displayed in the *Extensions for <Analytic Model\>* dialog.

> ### Note:  
> To do any form of extension other than adding custom fields defined in the source system, you must copy the preparation and application spaces, and create the extensions manually. For more information, see [Extending Intelligent Applications](extending-intelligent-applications-3c15868.md).



## Add Custom Fields

1.  In the side navigation area, click *Data Builder* and select the space you want to work in.

2.  Open the analytic model to which you want to add custom fields.

3.  Click *Extensions* in the editor toolbar to open the *Extensions* dialog. In SAP-managed read-only spaces, modifying extensions is the only change you can make to an analytic model.

    The *Extensions* dialog displays all custom fields available in data product entities that the intelligent application developers have authorized to extend the delivered analytic model. The *Status* column shows, for each custom field, whether it is currently *Enabled* or *Not Enabled* in your analytic model.

    > ### Note:  
    > The *Extensions* dialog is only available for analytic models in SAP-managed spaces.

4.  Select the custom fields you want to add to the model, then select *Enable* on the toolbar. Selected fields display the asterisk \(\*\).

    At any moment, you can click *Reset* to undo all your changes.

5.  Once ready, click *Save and Deploy* to:

    1.  Add the selected custom fields to the underlying fact or dimension,
    2.  Add the selected custom fields to the analytic model,
    3.  Redeploy the affected dimensions, fact and the analytic model.

    While the model deploys, its status is shown as "Deploying" and the *Extensions* dialog is unavailable.

    Once done, the custom fields are visible in the side panel, in the appropriate *Attribute* or *Measure* section.




## Remove Custom Fields

If needed, custom fields can be removed from the analytic model. In this case, they are also removed from the underlying dimension or fact.

1.  In the side navigation area, click *Data Builder* and select the space you want to work in.

2.  Open the analytic model from which you want to remove custom fields.

3.  Click *Extensions* in the editor toolbar to open the *Extensions* dialog. In SAP-managed read-only spaces, modifying extensions is the only change you can make to an analytic model.

    The *Extensions* dialog displays all custom fields available in data product entities that the intelligent application developers have authorized to extend the delivered analytic model.

4.  Select the enabled custom fields you want to remove from the model, then select *Disable* on the toolbar. Selected fields display the asterisk \(\*\).

    At any moment, you can click *Reset* to undo all your changes.

5.  Once ready, click *Save and Deploy* to:

    1.  Remove the selected custom fields from the underlying fact or dimension,
    2.  Remove the selected custom fields from the analytic model,
    3.  Redeploy the affected dimensions, fact and the analytic model.

    While the model deploys, its status is shown as "Deploying" and the *Extensions* dialog is unavailable.

    Once done, the removed custom fields are no longer visible in the side panel. The remaining enabled custom fields continue to be visible, in the appropriate *Attribute* or *Measure* section.


