<!-- loio4d96a8aac2424680ad15e3c78c7beffe -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Exclude Non-Navigable Dimension Attributes

Optimize your analytic model's performance by including only the attributes on which you want to be able to navigate. Other dimension attributes that you do not select can still be accessed and displayed in story tables via the SAP Analytics Cloud *Set Visible Properties* dialog.

> ### Note:  
> The modeler creating facts and dimensions can decide, for each measure and attribute, whether to make it available for inclusion in analytic models via the *Show* property \(see [Specify Attributes as Keys, Units, and Other Characteristics](specify-attributes-as-keys-units-and-other-characteristics-cedc59c.md)\). Measures excluded from an analytic model in this way cannot be accessed and displayed in SAP Analytics Cloud.
> 
> As dimension attributes that are excluded from analytic models can always be accessed as properties, the only way to prevent them from being exposed to SAP Analytics Cloud is to deselect the *Show* property at the dimension level.

1.  Click a dimension symbol in the diagram to show its properties in the side panel.
2.  Deselect one or more attributes that you will not need to navigate on to exclude them from the model.

    For example, customer `URL` or `Logo` columns will probably not be used for drill down or other navigation. By excluding them from the dimensions of your analytic model, you can improve its performance, and still have them available for display in tables in SAP Analytics Cloud.

3.  Deploy your model to make the change available to SAP Analytics Cloud.
4.  In your SAP Analytics Cloud story, add a table to your canvas and add one or more of your included dimension attributes to the table.
5.  In the *Builder* panel, find your dimension and then select <span class="FPA-icons-V3"></span> \(More\) *Properties* to open the *Set Visible Properties* dialog \(see [Modify Tables](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/92b95e9aeb404b7d9b550e0d5a774f5b.html) in the *SAP Analytics Cloud* documentation\).
6.  Select the properties you want to display, and then click *OK*.

    Each property is displayed in the table with its column header italicized. No menu is available when clicking on non-navigable property column headers.


