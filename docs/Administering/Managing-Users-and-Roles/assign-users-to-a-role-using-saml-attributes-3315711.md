<!-- loio33157115bac34f9b8e96dc0797969387 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Assign Users to a Role Using SAML Attributes

You can create a SAML role mapping to automatically assign users to a specific role based on their SAML attributes.

For example, you want to give a specific role to all employees that are assigned to a specific cost center. Once you've done the role mapping, if new users are assigned to the cost center in the SAML identity provider \(IdP\), the users will be automatically assigned to the role when logging onto SAP Datasphere via SAML authentication.



<a name="loio33157115bac34f9b8e96dc0797969387__section_nd2_qzf_tyb"/>

## Prerequisites

Your custom SAML Identity Provider \(IdP\) must be configured and the authentication method selected must be *SAML Single Sign-On \(SSO\)* in <span class="FPA-icons-V3"></span> \(*System*\) → <span class="Belize-icons"></span> \(*Administration*\) →*Security*. See [Enabling a Custom SAML Identity Provider \(Legacy Custom IdP\)](enabling-a-custom-saml-identity-provider-legacy-custom-idp-9b26536.md).



<a name="loio33157115bac34f9b8e96dc0797969387__section_fkm_4zf_tyb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Security*\) ** \> ** <span class="FPA-icons-V3"></span> \(*Roles*\).
2.  Select a role \(or open the role\) and click ![](images/SAMLRoleMapping_Button_4b6783e.jpg) \(*Open 'SAML Role Mapping'*\).

3.  Under *Conditions*, select a *SAML Attribute*, select a *Condition*, and enter a *Value* if required.

4.  \(Optional\) Select **\+** \(*New mapping definition*\) to add additional mappings to the role assignment.

    For each additional mapping, under *Conditions*, select a *SAML Attribute*, select a *Condition*, and enter a *Value* if required.

    Under *Conditions Logic*, select *AND* or *OR*.

    If *AND* is selected, the conditions for all attributes must be met for the mapping to be applied. If *OR* is selected, the conditions for only one of the attributes must be met for the mapping to be applied.

    The selected role will be applied to all users who meet the specified conditions when logging onto SAP Datasphere via SAML authentication. If the selected role was previously assigned to a user, but the user does not meet the specified conditions, the role will be revoked when the user logs in.

    > ### Note:  
    > If a user is assigned to a scoped role via SAML attributes, the user is automatically assigned to all the spaces included in the scoped role.

    In the *Roles* page, a dedicated icon in the role tile is displayed, indicating that the users are assigned to the role via SAML attributes. When you hover over the icon, the conditions defined for the role are displayed.


