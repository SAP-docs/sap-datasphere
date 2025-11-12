<!-- loiofe829debe389450394cf7a15860e2caa -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Translating Metadata for SAP Analytics Cloud

Users with a scoped role containing the *Translation* privilege can translate metadata such as business names and column names for dimensions and analytic models, and hierarchy dimension labels for SAP Analytics Cloud stories.

This topic contains the following sections:

-   [Prerequisites](translating-metadata-for-sap-analytics-cloud-fe829de.md#loiofe829debe389450394cf7a15860e2caa__section_privileges)
-   [Enable Translation](translating-metadata-for-sap-analytics-cloud-fe829de.md#loiofe829debe389450394cf7a15860e2caa__section_activatingtranslation)
-   [Select Objects to Translate](translating-metadata-for-sap-analytics-cloud-fe829de.md#loiofe829debe389450394cf7a15860e2caa__section_addobjects)
-   [Translate Metadata via XLIFF Files](translating-metadata-for-sap-analytics-cloud-fe829de.md#loiofe829debe389450394cf7a15860e2caa__section_translatexliff)
-   [Translate Metadata Manually](translating-metadata-for-sap-analytics-cloud-fe829de.md#loiofe829debe389450394cf7a15860e2caa__section_translatemanually)
-   [Delete Translations](translating-metadata-for-sap-analytics-cloud-fe829de.md#loiofe829debe389450394cf7a15860e2caa__section_deletetranslations)
-   [Manage Translation](translating-metadata-for-sap-analytics-cloud-fe829de.md#loiofe829debe389450394cf7a15860e2caa__section_tooldesc)



<a name="loiofe829debe389450394cf7a15860e2caa__section_privileges"/>

## Prerequisites

To enable translation for your space, and to manage translation in the *Translation* tool, you must have a scoped role that grants you access to your space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-R------`\) - To enable translation and select the source language for your space.
-   *Space Files* \(`-R------`\) - To view objects in your space.
-   *Translation* \(`CR-D----`\) - To access the *Translation* tool, select objects to translate, manage and delete translations.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loiofe829debe389450394cf7a15860e2caa__section_xxd_zxm_q2c"/>

## Introduction

For example, you may have stories that have column names in a default language, but you'd like to have those names displayed in other languages so that your SAP Analytics Cloud story can be viewed in the language of your choice.

To translate objects' metadata, you can have it translated into multiple target languages using third-party translation tools or you can have those descriptions translated in-line using the *Translation* tool. You can use the tool to review translations, and edit or add translations from scratch for some or all languages.

To manage translation, you must be assigned to a scoped role that inherits a template \(such as DW Space Administrator\), which grants the Translation privilege \(see [Create a Scoped Role to Assign Privileges to Users in Spaces](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/b5c4e0b6c462414783ebbfc053815521.html "A scoped role inherits a set of scoped privileges from a standard or custom role and grants these privileges to users for use in the assigned spaces.") :arrow_upper_right:\).



<a name="loiofe829debe389450394cf7a15860e2caa__section_activatingtranslation"/>

## Enable Translation

DW Space Administrators can turn on the toggle to enable content translation for a space:

1.  In the *Main Menu*, click ![](Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\).

2.  Select a space.

3.  In the *Overview* tab, in the *General Settings* \> *Translation* sections, select a language as *Source Language*. For more information on available languages, see [Learn About the Translation Process](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/8310076258a94a4194a926506b80c390.html) in SAP Analytics Cloud.




<a name="loiofe829debe389450394cf7a15860e2caa__section_addobjects"/>

## Select Objects to Translate

You can add objects to *Translation* tool:

1.  Click <span class="FPA-icons-V3"></span> \(Add\). The *Add Objects* dialog opens.
2.  Select the objects you want to translate.

    > ### Note:  
    > Only Analytic Models can be selected in the *Add Objects* dialog, but the dimensions and hierarchies attached to added Analytic Models are automatically selected to the Translation tool.

3.  Click *Add Objects*. The selected Analytic Models and their dependencies are added to the tool.



<a name="loiofe829debe389450394cf7a15860e2caa__section_translatexliff"/>

## Translate Metadata via XLIFF Files

You can translate large amounts of metadata with the help of XLIFF files. The <span class="SAP-icons-V5"></span> \(Download\) button in the *Translation* tool allows you to download the strings to be translated to a XLIFF file, which can be used to translate the content. Then, the translated strings must be uploaded back to the *Translation* tool in the XLIFF file format with the <span class="FPA-icons-V3"></span> \(Upload\) button.

1.  In the *Translation* tool, select at least one entity that you want to translate.
2.  Click <span class="SAP-icons-V5"></span> \(Download\) to download the XLIFF files. If one object is selected to be downloaded, the corresponding XLIFF file can be downloaded as a .zip file.
3.  You can choose to select *All Strings* or *Outstanding Strings* while exporting the XLIFF file\(s\). The Outstanding Strings option is enabled only for partially translated objects.

    The XLIFF file is downloaded to the default location in your system.

    > ### Note:  
    > The downloaded XLIFF file contains the source locale and the list of text that needs translation. You can use this XLIFF file in any external translation tool to generate the translated content as a separate XLIFF file per locale.

4.  Once the translation is done, click <span class="FPA-icons-V3"></span> \(Upload\) to open the *Import Translations* dialog.
5.  Click *Upload Files* to upload the translated XLIFF files back into the *Translation* tool.
6.  Click *Import* to upload the XLIFF files.

> ### Note:  
> You can import multiple XLIFF files. Each XLIFF file contains the translated content in one language, which is automatically fetched from the language code embedded in the name of the uploaded XLIFF files. These XLIFF files can be uploaded together since they belong to one object. The *Import* option is disabled if more than one object is selected.



<a name="loiofe829debe389450394cf7a15860e2caa__section_translatemanually"/>

## Translate Metadata Manually

You can view the source and the translated text in the *Translation* tool, and add or edit the translated text in-line.

1.  Select the object you want to translate manually and click <span class="FPA-icons-V3"></span> \(Edit\). The list of source text appears.
2.  Choose the *Target Language* and start adding the translated text in the empty field.
3.  Select *Save*. The message *Translation updated successfully* appears, and the user who had marked the model or dimension for translation is notified.

You have now successfully saved the newly translated text.



<a name="loiofe829debe389450394cf7a15860e2caa__section_deletetranslations"/>

## Delete Translations

To delete translations, select one or more objects in the *Translation* tool and click <span class="FPA-icons-V3"></span> \(Delete\).

> ### Note:  
> Deleting translations removes the object and attached translated strings from the *Translation* tool. You'll be able to add the object back to the tool, but no translation will be attached to it any longer.



<a name="loiofe829debe389450394cf7a15860e2caa__section_tooldesc"/>

## Manage Translation

The *Translation* tool shows the spaces you are assigned to with enabled translation. Each space contains entities that are selected for translation. The tool allows you to perform and manage these translations.

From the side navigation, choose <span class="SAP-icons-V5"></span> \(*Translation*\) and select a space. The spaces available here are the ones enabled for translation. For more information, see [Enable Translation](translating-metadata-for-sap-analytics-cloud-fe829de.md#loiofe829debe389450394cf7a15860e2caa__section_activatingtranslation).

> ### Note:  
> -   If the model has changed, new strings will automatically appear in the translation tool as *Not Translated*. Expired strings will still be available in the *Translation* tool.
> -   You can upload the XLIFF files even if there is a mismatch in the HTML tags between the source and target language strings.

The *Translation* tool displays the following buttons and fields:

**Toolbar**


<table>
<tr>
<th valign="top">

Tool

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons-V3"></span> \(Add\)

</td>
<td valign="top">

Adds objects to the *Translation* tool. Only Analytic Models can be selected in the *Add Objects* dialog, but the dimensions and hierarchies attached to selected Analytic Models are automatically added to the *Translation* tool. See [Select Objects to Translate](translating-metadata-for-sap-analytics-cloud-fe829de.md#loiofe829debe389450394cf7a15860e2caa__section_addobjects).

</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons-V5"></span> \(Refresh\)

</td>
<td valign="top">

Refreshes the list of objects.

</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons-V3"></span> \(Edit\)

</td>
<td valign="top">

Open the selected object for manual in-line translation. Users with the *Create* permission can access this functionality. See [Translate Metadata Manually](translating-metadata-for-sap-analytics-cloud-fe829de.md#loiofe829debe389450394cf7a15860e2caa__section_translatemanually).

</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons-V3"></span> \(Delete\)

</td>
<td valign="top">

Deletes translations for the selected objects. See [Delete Translations](translating-metadata-for-sap-analytics-cloud-fe829de.md#loiofe829debe389450394cf7a15860e2caa__section_deletetranslations).

</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons-V5"></span> \(Download\) <span class="FPA-icons-V3"></span> \(Upload\)

</td>
<td valign="top">

Downloads translatable \(source\) XLIFF files and uploads the translated XLIFF files. See [Translate Metadata via XLIFF Files](translating-metadata-for-sap-analytics-cloud-fe829de.md#loiofe829debe389450394cf7a15860e2caa__section_translatexliff).

</td>
</tr>
<tr>
<td valign="top">

:eye:

</td>
<td valign="top">

Specifies the fields to display for the tool objects:

-   path of the object
-   description of the object
-   type of the object
-   name of the object's creator
-   source language from which the object has been created
-   *Requested On*: date when the translation was requested
-   *Changed On*: date when the translation strings have been updated
-   *Status*: status of the translation. These status buttons are clickable and you can view the status of translations uploaded for each language.



</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons-V3"></span> \(Filter\)

</td>
<td valign="top">

Filters translated, not translated, and expired objects.

</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons-V3"></span> \(Search\)

</td>
<td valign="top">

Searches objects based on Name, Description, Translated by, Translated Language, Requested on, Changed on, Status, and Owner.

</td>
</tr>
</table>

**Tool Fields**


<table>
<tr>
<th valign="top">

Title

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Technical Name/Business Name*

</td>
<td valign="top">

Names of the object requiring translation.

</td>
</tr>
<tr>
<td valign="top">

*Type*

</td>
<td valign="top">

Object type requiring translation. It can be a:

-   remote table
-   local table
-   view
-   analytic model
-   hierarchy



</td>
</tr>
<tr>
<td valign="top">

*Creator*

</td>
<td valign="top">

Name of the person who seletected the object for translation

</td>
</tr>
<tr>
<td valign="top">

*Requested On*

</td>
<td valign="top">

When the translation was requested

</td>
</tr>
<tr>
<td valign="top">

*Changed On*

</td>
<td valign="top">

When the strings or translations for strings were last updated

</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

Status of the translation per object:

-   *Translated*: Once all strings are translated completely, the status is shown as *Translated*.
-   *Not Translated*: For a new object, or for objects whose translation is expired or deleted completely, the status is shown as *Not Translated*.
-   *Partially Translated*: When the strings in an object are not translated completely, the status is shown as *Partially Translated*. Once it is translated again, the status changes back to *Translated*.

To see the status of the translation of an object per language, click on the object. A dialog appears with the list of translated languages and corresponding status in which the object was translated.

</td>
</tr>
</table>

