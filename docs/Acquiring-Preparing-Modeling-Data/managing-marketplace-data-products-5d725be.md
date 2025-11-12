<!-- loio5d725beb848e432a91eb8de29875d7e2 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Managing Marketplace Data Products

Use the *Marketplace Data Products* page to keep track of and manage all your installed data products. You can also activate licenses without installing data products and join or leave contexts.



<a name="loio5d725beb848e432a91eb8de29875d7e2__prereq_fcb_p1y_tyb"/>

## Prerequisites

Marketplace data products and data providers are only available in the SAP Datasphere catalog.

To search for and evaluate objects in the *Data Products \(Marketplace\)* collection, you must have:

-   A global role that grants you the following privilege:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Catalog Asset* \(`–R–––--`\) - To access the catalog.

-   A scoped role that grants you access to the space or spaces to install to, with the following privileges:
    -   *Spaces* \(`–R–––--`\) - To access a space.
    -   *Space Files* \(`CRU––--`\) - To install data products to a space.
    -   *Data Warehouse Data Integration* \(`-RU––--`\) - To acquire data in the space where the data product is installed.
    -   *Data Warehouse Connection* \(`CRU––--`\) - To check the license of installed data products.


The *Catalog User* global role and the *DW Modeler* scoped role template, applied together for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

<a name="concept_szs_ztq_jdc"/>

<!-- concept\_szs\_ztq\_jdc -->

## Keeping Track of Marketplace Data Products

From the side navigation area, select <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\)** \> ** <span class="SAP-icons-V5"></span> \(*Marketplace Data Products*\) to access the *Marketplace Data Products page*. The top of the *Marketplace Data Products* page has interactive charts that give you a quick overview of the data products that you've installed.

-   *Installations by Month* shows the total number of data product installations for each month.
-   *Top Data Providers* shows the top data providers of the data products that you installed.
-   *License Validity* shows the number of licenses that will be expiring or have already expired.

On the *Data Products* tab, you'll see a list of your installed data products. Use the sort, group, and filter tools if you're looking for a specific data product.

**Installed Data Products**


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Displays the data product name. Select the link to open the data product details page.

</td>
</tr>
<tr>
<td valign="top">

Data Provider

</td>
<td valign="top">

Displays the name of the data provider.

</td>
</tr>
<tr>
<td valign="top">

Space

</td>
<td valign="top">

Displays the name of the SAP Datasphere space where the data product is installed.

</td>
</tr>
<tr>
<td valign="top">

Data Product Details

</td>
<td valign="top">

Displays details about the data product, which includes the provisioning and release statuses, delivery method, and license access type.

</td>
</tr>
<tr>
<td valign="top">

Installation Details

</td>
<td valign="top">

Displays the installation details, which includes the installation status and the last installation date.

For data products with the **Full Replication** delivery mode, you can select to automatically install updates when an update for the data product is available.

</td>
</tr>
<tr>
<td valign="top">

Actions

</td>
<td valign="top">

Displays the actions available for the data products. Select <span class="SAP-icons-V5"></span> \(Delivery Details\) to view the delivery details of the data product.

</td>
</tr>
</table>

<a name="task_etn_54y_jdc"/>

<!-- task\_etn\_54y\_jdc -->

## Viewing Marketplace Data Product Delivery Details



<a name="task_etn_54y_jdc__context_lll_v4y_jdc"/>

## Context

You can review the delivery details of a data product by selecting the <span class="SAP-icons-V5"></span> \(Delivery Details\) action. This information can help you understand why an installation might have failed.



<a name="task_etn_54y_jdc__steps_acq_bpy_jdc"/>

## Procedure

1.  In the side navigation area, click <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\)** \> ** <span class="SAP-icons-V5"></span> \(*Marketplace Data Products*\).

2.  In the *Data Products* tab, search for the data product that you want to review.

3.  Select <span class="SAP-icons-V5"></span> \(Delivery Details\).

    A dialog showing the delivery history of the data product appears.

4.  Review the installation history. To get more details for why a specific installation failed, select the row to view the details.

    -   The *Overview* section displays the details of the installation. If the installation failed, the status shows the failure message.
    -   The *Data Artifacts* section displays the details of the data artifacts that were updated. If the data artifacts failed to update, the status shows the failure message.


<a name="task_klk_j4d_f2c"/>

<!-- task\_klk\_j4d\_f2c -->

## Managing Installed Data Products



<a name="task_klk_j4d_f2c__context_usq_m4d_f2c"/>

## Context

After a data product has been installed, you'll want to check on its status to ensure that it was installed without issue. Also, during the time that you use the data product, you'll want to make sure that you have the most current version of it. When you no longer need it or a new major version is available, you can uninstall the data product. Use the actions in the toolbar to help you manage an installed data product.

**Installed Data Products Toolbar**


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

*Search*

</td>
<td valign="top">

Enter all or part of the characters a particular data product name to quickly find the data product you want to check. 

</td>
</tr>
<tr>
<td valign="top">

*Install*

</td>
<td valign="top">

Select to install a data product that has a status of uninstalled. 

</td>
</tr>
<tr>
<td valign="top">

*Update*

</td>
<td valign="top">

Select to manually update a data product to install the latest minor version. 

</td>
</tr>
<tr>
<td valign="top">

*Uninstall*

</td>
<td valign="top">

Select to uninstall a data product. You will want to uninstall a data product when it's no longer needed in the space that it was installed, a new major version of the data product is installed, or you want to terminate the subscription. 

</td>
</tr>
<tr>
<td valign="top">

*Reinitialize*

</td>
<td valign="top">

Select to reinitialize a data product to resolve connection issues. For example, a data product with connection issues will have a failed status instead of up-to-date. 

</td>
</tr>
<tr>
<td valign="top">

View options

</td>
<td valign="top">

Select the view options to sort, group, and filter the list of installed data products. You can also choose which columns you want to show or hide.

</td>
</tr>
</table>



## Procedure

1.  In the side navigation area, click <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\)** \> ** <span class="SAP-icons-V5"></span> \(*Marketplace Data Products*\).

2.  On the *Data Products* tab, search for the data product you want and review its product and installation details.

3.  Select what you want to do:

    -   If the data product has a failed status, select *Reinitialize*. A failed status can indicate connection issues. You can find out why the data product has a failed status by selecting <span class="SAP-icons-V5"></span> \(Delivery Details\).

        In this case, reinitializing the data product will reestablish the data connection. Keep in mind that within the existing license and version, the data model is not updated. If needed, you can uninstall and then reinstall the data product. However, when you do this, a new license is required.

    -   If an update to a data product is available, select *Update* to install the latest version.
    -   If you no longer need a data product in the space that it's installed in or no longer need the data product at all, or a new major version of the data product has been installed, select *Uninstall*.
    -   If you are having issues when using the data product, you can update it \(if a minor version is available\), reinitialize it, or uninstall and then reinstall it. If the issues with the data product continue, contact the data provider. Keep in mind that if you reinstall a data product, you need a new license.


<a name="task_rzp_3ms_jdc"/>

<!-- task\_rzp\_3ms\_jdc -->

## Activating a License



<a name="task_rzp_3ms_jdc__context_q5m_jms_jdc"/>

## Context

On the *Access* tab, you can review all your activated licenses. The information shown includes the data provider, activation status, valid until data, and more.

**Activated Licenses**


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Reference

</td>
<td valign="top">

Displays the reference information about the license.

</td>
</tr>
<tr>
<td valign="top">

Data Provider

</td>
<td valign="top">

Displays the data provider that issued the license key and has licensed the data products to you.

</td>
</tr>
<tr>
<td valign="top">

Data Products

</td>
<td valign="top">

Displays the number of data products covered by the license key. Select the number to see the activated data products for the license key. To learn more about a data product, select the name to open its details page.

</td>
</tr>
<tr>
<td valign="top">

Activation keys

</td>
<td valign="top">

Displays the number of activation keys available for the license. Select the number to see a list of the activation keys and the users who used them. An action is also available for copying the activation key.

</td>
</tr>
<tr>
<td valign="top">

Company

</td>
<td valign="top">

Displays the company that is registered to use the license.

</td>
</tr>
<tr>
<td valign="top">

Expiration Date

</td>
<td valign="top">

Displays the last date on which the license is valid. If the expiration date is one month or less, the number of days before expiry is also shown.

</td>
</tr>
</table>

If needed, you can activate the license key without installing the data product.



<a name="task_rzp_3ms_jdc__steps_gk3_mns_jdc"/>

## Procedure

1.  In the side navigation area, click <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\)** \> ** <span class="SAP-icons-V5"></span> \(*Marketplace Data Products*\).

2.  Select the *Access* tab, to see all your active licenses.

3.  To activate a license, select the *Activate* button.

4.  In the dialog, enter the license key and select *Activate*.




<a name="task_rzp_3ms_jdc__result_h1y_wns_jdc"/>

## Results

The license key is activated and appears in the tab, where you can review its details. When you install the data product, you won't have to enter the activation key since you already activated it.

<a name="task_zdf_3qy_jdc"/>

<!-- task\_zdf\_3qy\_jdc -->

## Joining or Leaving a Context



<a name="task_zdf_3qy_jdc__context_wgk_jqy_jdc"/>

## Context

On the *Visibility* tab, you can see an overview of all contexts you are a member of. Contexts help data providers differentiate between public and private data marketplaces.

-   SAP manages the public data marketplace. When a data provider lists their data product in the public data marketplace, all users of SAP Datasphere can find, evaluate, and acquire the data product.

    By default all users are members of the public data marketplace context and cannot leave.

-   A data provider manages the private data market place by creating and managing the contexts. When a data provider lists their data product in the private data marketplace under a certain context, only users who are members of that context can find, evaluate, and acquire the data product. For more information on managing contexts, see [Context Management App](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/2f3dbb9da8ae4b7a992c6358ab4fc2be.html "Get an overview of your existing contexts, manage them or create new ones.") :arrow_upper_right:.

    You can join new contexts or leave the ones you don't want to be member of.


**Context Membership**


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Displays the name of the context.

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Displays a description of the context.

</td>
</tr>
<tr>
<td valign="top">

Owner

</td>
<td valign="top">

Displays the name of the data provider who owns the context. You can select the data provider name to view the data provider details.

</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

Displays the type of context. A context can be one of the following types:

-   **Public Data Marketplace**, where all data providers can publish data products that are available to all consumers without restrictions. This context always appears at the top of the list.

-   **Data Shop**, where only one data provider can publish data products in the context for one or multiple consumers.

-   **Private Data Products**, where one or multiple consumers want to act as data providers to share internal reference data with the context owner that uses this data for the creation of data products.

-   **Private Data Exchange**, where a data exchange is built with multiple data providers and consumers \(from different companies\). All participants have the same rights.

-   **Internal Data Marketplace**, for the scenario where all the users of a system can acquire data products internally. By default, all the users of the system are automatically added to the context.


For more information about these context types and others, see [Context Management App](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/2f3dbb9da8ae4b7a992c6358ab4fc2be.html "Get an overview of your existing contexts, manage them or create new ones.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

Show in Search

</td>
<td valign="top">

Indicates whether data products that belong to the context appear in the catalog search results. You can turn off this option for a particular context if you want to hide data products from the search results.

</td>
</tr>
<tr>
<td valign="top">

Action

</td>
<td valign="top">

Displays actions available for the context. Select *Leave* if you want to leave a context.

</td>
</tr>
</table>

<a name="task_jws_kqy_jdc"/>

<!-- task\_jws\_kqy\_jdc -->

### Joining a Context



<a name="task_jws_kqy_jdc__context_g34_kks_jdc"/>

## Context

By joining contexts, you can find, evaluate, and acquire data products that are listed on the private data marketplace. Before joining a context, you must contact the data provider to get the context member activation key.



<a name="task_jws_kqy_jdc__steps_vb3_mks_jdc"/>

## Procedure

1.  In the side navigation area, click <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\)** \> ** <span class="SAP-icons-V5"></span> \(*Marketplace Data Products*\).

2.  Select the *Visibility* tab, to see all the contexts that you belong to.

3.  To join a context, select the *Join* button.

4.  In the dialog, enter the context member activation key and select *Join*.

    You have joined the context, and it appears in the tab, where you can review its details.

5.  \(Optional\) To hide data products of a specific context on the catalog search page, switch off the *Show in Search* option for that context. By default, this option is switched on.

    When you search for data products, the search results will show data products from the public data marketplace and the contexts \(private data marketplace\) that you are a member of. Data products that belong to contexts that you have switched off the *Show in Search* option for are hidden from the search.


<a name="task_lq1_mqy_jdc"/>

<!-- task\_lq1\_mqy\_jdc -->

### Leaving a Context



<a name="task_lq1_mqy_jdc__context_rpp_qls_jdc"/>

## Context

If you no longer want to be a member of a context, you can choose to leave it.



<a name="task_lq1_mqy_jdc__steps_zbx_rls_jdc"/>

## Procedure

1.  In the side navigation area, click <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\)** \> ** <span class="SAP-icons-V5"></span> \(*Marketplace Data Products*\)

2.  Select the *Visibility* tab, to see all the contexts that you belong to.

3.  Search for the context you want to leave and select *Leave*.




<a name="task_lq1_mqy_jdc__result_fgm_yls_jdc"/>

## Results

The context is no longer available in the tab.

When you search the catalog, data products that are listed in that context no longer appear in the search results. However, you can still see data products that you have purchased on the *Marketplace Data Products* page and you will continue to receive any available updates.

