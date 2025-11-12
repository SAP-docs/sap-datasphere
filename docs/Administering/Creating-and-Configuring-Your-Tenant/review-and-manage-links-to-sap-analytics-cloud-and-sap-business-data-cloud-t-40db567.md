<!-- loio40db56764bff4f9ab7eace16ac8e7e67 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Review and Manage Links to SAP Analytics Cloud and SAP Business Data Cloud Tenants

You can link your SAP Datasphere tenant to a SAP Analytics Cloud tenant accessible in the <span class="SAP-icons-V5"></span> \(*Product Switch*\) in the top right of the shell bar, to help your users easily navigate between them. In addition, your tenant can be linked to by SAP Analytics Cloud and SAP Business Data Cloud administrators.



<a name="loio40db56764bff4f9ab7eace16ac8e7e67__section_ugk_bkk_m2c"/>

## Prerequisites

To view the *Administration* page containing the *Tenant Links* tab, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To acces the *Administration* area.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md).

> ### Note:  
> To select an SAP Analytics Cloud tenant to make available via the <span class="SAP-icons-V5"></span> \(*Product Switch*\), you must have the *System Owner* role.



<a name="loio40db56764bff4f9ab7eace16ac8e7e67__section_tmv_1kk_m2c"/>

## Product Switch Tenant Links

In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *Tenant Links*.

The following properties are available in the *Product Switch* section:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

SAP Datasphere URL

</td>
<td valign="top">

\[read-only\] Displays the URL for the current SAP Datasphere tenant.

</td>
</tr>
<tr>
<td valign="top">

SAP Analytics Cloud URL

</td>
<td valign="top">

Displays the URL for the SAP Analytics Cloud selected by the *System Owner* to be accessible via the <span class="SAP-icons-V5"></span> \(*Product Switch*\).

</td>
</tr>
</table>

If your tenant is included in an SAP Business Data Cloud formation, then the following links are also displayed:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

SAP Business Data Cloud Cockpit URL

</td>
<td valign="top">

\[read-only\] Displays the URL of the SAP Business Data Cloud Cockpit tenant.

</td>
</tr>
<tr>
<td valign="top">

SAP Analytics Cloud URL \(SAP Business Data Cloud Formation\)

</td>
<td valign="top">

\[read-only\] Displays the URL of the SAP Analytics Cloud tenant in the formation.

</td>
</tr>
</table>

In this situation, both the SAP Business Data Cloud Cockpit and the SAP Analytics Cloud tenants are shown as tiles when users click the <span class="SAP-icons-V5"></span> \(*Product Switch*\) and, if they have a user in the relevant target tenant, they can click the tile to navigate there.

For more information about SAP Business Data Cloud, see:

-   [Integrating Data from SAP Business Data Cloud](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/8f9c3725cfe84e08b3e951e7af06ce57.html "Users with an SAP Business Data Cloud administrator role can install intelligent applications to SAP Datasphere and activate data packages to allow modelers to work with data products.") :arrow_upper_right:
-   [Integrate SAP Business Data Cloud Provisioned Systems](https://help.sap.com/docs/SAP_BUSINESS_DATA_CLOUD/f7acf8c9dad54e99b5ce5ebc633ed8e1/d6ec89febd8a40dbb7fb461b60bef289.html) \(in the *SAP Business Data Cloud* documentation\)



<a name="loio40db56764bff4f9ab7eace16ac8e7e67__section_product_switch"/>

## Specify an SAP Analytics Cloud Tenant to Access via the Product Switch

You can link your SAP Datasphere tenant to a SAP Analytics Cloud tenant accessible in the <span class="SAP-icons-V5"></span> \(*Product Switch*\) in the top right of the shell bar, to help your users easily navigate between them.

To select an SAP Analytics Cloud tenant to make available via the <span class="SAP-icons-V5"></span> \(*Product Switch*\), you must have the *System Owner* role.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *Tenant Links*.
2.  Enter the URL of your SAP Analytics Cloud tenant.

    > ### Note:  
    > You must select an SAP Analytics Cloud tenant hosted in a Cloud Foundry environment. Linking to NEO tenants is not supported.

3.  Click *Save* to confirm the connection.

    The selected SAP Analytics Cloud tenant tile is shown when users click the <span class="SAP-icons-V5"></span> \(*Product Switch*\) and, if they have a user with an appropriate role in the SAP Analytics Cloud system, they can click the tile to navigate there.

    > ### Note:  
    > An SAP Analytics Cloud user must create a live connection before they can consume data from SAP Datasphere.
    > 
    > Multiple SAP Analytics Cloud tenants can create live connections to your SAP Datasphere tenant, but only one SAP Analytics Cloud tenant can be accessed via the <span class="SAP-icons-V5"></span> \(*Product Switch*\).
    > 
    > For more information, see [Consume Data in SAP Analytics Cloud via a Live Connection](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/a2c5486c03174620be9de3c8c769ce54.html "You can create a live connection from SAP Analytics Cloud to SAP Datasphere and consume data exposed as analytic models and perspectives to create stories and analytic applications.") :arrow_upper_right:.




<a name="loio40db56764bff4f9ab7eace16ac8e7e67__section_cmg_fkp_m2c"/>

## Data Storage for Planning

If your SAP Datasphere tenant has been selected to store planning data for an SAP Analytics Cloud tenant, then the following information is displayed:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

SAP Datasphere URL

</td>
<td valign="top">

\[read-only\] Displays the URL for the current SAP Datasphere tenant.

</td>
</tr>
<tr>
<td valign="top">

SAP Analytics Cloud URL

</td>
<td valign="top">

\[read-only\] Displays the URL of the SAP Analytics Cloud tenant storing planning data in the current SAP Datasphere tenant.

</td>
</tr>
<tr>
<td valign="top">

Tenant Link Artifacts

</td>
<td valign="top">

\[read-only\] Displays the name of the OAuth client the SAP Analytics Cloud tenant uses to connect to SAP Datasphere.

</td>
</tr>
</table>

For more information about storing SAP Analytics Cloud planning data in SAP Datasphere, see:

-   [Integrate with SAP Analytics Cloud for Planning](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/f589cdea41674badaecfa1bf02571b6f.html "SAP Datasphere integrates with SAP Analytics Cloud to act as a data source for loading actuals or external data into a planning model, and can also persist your planning data and combine it with live actuals or other data as appropriate.") :arrow_upper_right:
-   [Configure Data Storage for Planning](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/b103a251020746f786ec0860fa51a63a/658629503d5049e794ddd809ee554853.html) \(in the *SAP Analytics Cloud* documentation\)

