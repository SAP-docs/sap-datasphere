<!-- loio40ec77ec24f244279a81448969a7e769 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Exposing a View For Consumption

To make a view available for consumption in SAP Analytics Cloud and other clients, tools, and apps \(including via the public ODATA API\), enable the *Expose for Consumption* switch.



## Context

Views can be accessed outside SAP Datasphere only if they have the *Expose for Consumption* switch enabled.

> ### Note:  
> You can also expose data as an analytic model \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\) or as a perspective \(see [Define Perspectives](../Buisiness-Builder/define-perspectives-ce26fd3.md)\).

For information about consuming data, see [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users of SAP Datasphere with any of the standard roles can consume data exposed by spaces of which they are a member. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the DW Consumer role.") :arrow_upper_right:.



<a name="loio40ec77ec24f244279a81448969a7e769__steps_qfj_h5c_2sb"/>

## Procedure

1.  Open the view in the graphical view or SQL view editor.

2.  In the output node properties side panel, enable the *Expose for Consumption* switch.

    > ### Note:  
    > To make your view consumable by SAP Analytics Cloud, you must set its *Semantic Type* to *Analytical Dataset* and enable the *Expose for Consumption* switch. SAP Analytics Cloud can access dimensions, hierarchies and other entities to which your analytical dataset points via associations, even if they have not themselves been exposed. Other BI clients, tools, and apps can consume views of any type that have the *Expose for Consumption* switch enabled.

3.  Click <span class="SAP-icons"></span> \(Deploy\) to save and deploy the view.


