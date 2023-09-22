<!-- loio328ab99609354bf2a2007c8181fa0f6a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Replace a Source

Drag a source from the *Source Browser*, hover over an existing source, and click *Replace*. You are guided through mapping the columns from the old source to the new source.



<a name="loio328ab99609354bf2a2007c8181fa0f6a__context_dbb_q21_w4b"/>

## Context

For example, you may want to replace a local table containing sample data from a CSV file, with a different table containing current data from a source system.

The output structure of the view is preserved as far as possible, and any impacts caused by the replacement of the source are indicated by validation messages.



<a name="loio328ab99609354bf2a2007c8181fa0f6a__steps_gqn_wbl_qyb"/>

## Procedure

1.  If the *Source Browser* panel is not visible on the left of the screen, click *Source Browser* in the toolbar to show it.

2.  Select the new source and drag it over the source you want to replace in the diagram. Wait for the context menu to appear, slide your cursor over the *Replace* option and then release the mouse button.

    The *Replace Source* dialog opens, showing the old source and its columns on the left side and the new source and its columns on the right side, with mappings proposed, where possible between them.

    > ### Note:  
    > Only the columns used in the current view are listed on the left side. Any columns that are excluded in your view are not used, and therefore do not need to be remapped.

3.  Review the proposed mappings and try to map any unmapped old source columns if possible.

    > ### Note:  
    > You are not required to map all the columns from the old source, but any you leave unmapped will generate validation warnings or errors. Any new source columns you leave unmapped will be excluded by default.

4.  Click *Replace* to close the dialog and confirm the replacement. SAP Datasphere performs the following actions:

    -   Replace the old source by the new source in your view.
    -   If any old source columns were left unmapped, generate warning and error messages for each node that is impacted.
    -   If any new source columns were left unmapped, insert a projection node after the source \(if one is not already present\) and exclude these new columns so that they do not modify the output columns.
    -   Update the *Status* of your view.

5.  \[if new source columns were left unmapped\] Review the projection node and restore any new columns that you want to make available \(see [Reorder, Rename, and Exclude Columns](../reorder-rename-and-exclude-columns-b846d0d.md)\)

6.  \[if old source columns were left unmapped\] Review each of the validation warnings and errors and correct them as appropriate.

7.  Click the *Back* button to return to the *Transformation Flow Editor*, and then save the transformation flow.

    > ### Note:  
    > If you have not resolved all the validation errors, then you can still save your view, but you will not be allowed to deploy it.

8.  If your view is itself used as a source by other views, then review the *Dependent Objects* section in the side panel to see if your change has impacted any of them. You can click on an object in the list to navigate to it and review any errors and warnings.

9.  When appropriate, click <span class="SAP-icons"></span> \(Deploy\)to deploy your transformation flow.


