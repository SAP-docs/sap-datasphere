<!-- loio40f493f922f24663aa8191ad1e79cb77 -->

# Use Identity Provider Attributes as Identifiers in Data Access Controls

You can use values in custom application attributes provided by your identity provider as identifiers in your data access controls and define conditions that apply to users with these values. Using attributes in this way allows you to apply a single condition to all users whose accounts contain the specified attribute value.

This topic contains the following sections:

-   [Prerequisites](use-identity-provider-attributes-as-identifiers-in-data-access-controls-40f493f.md#loio40f493f922f24663aa8191ad1e79cb77__section_prerequisites)
-   [Configure Custom Application Attributes](use-identity-provider-attributes-as-identifiers-in-data-access-controls-40f493f.md#loio40f493f922f24663aa8191ad1e79cb77__section_configure)
-   [Use Attributes as Identifiers in Permissions Entities](use-identity-provider-attributes-as-identifiers-in-data-access-controls-40f493f.md#loio40f493f922f24663aa8191ad1e79cb77__section_use)
-   [Enable Attributes as Identifiers in Data Access Controls](use-identity-provider-attributes-as-identifiers-in-data-access-controls-40f493f.md#loio40f493f922f24663aa8191ad1e79cb77__section_enable)
-   [Example: Using Country Identifiers in a Hierarchy with Directory Permissions Table](use-identity-provider-attributes-as-identifiers-in-data-access-controls-40f493f.md#loio40f493f922f24663aa8191ad1e79cb77__section_example_hwd)
-   [Example: Combining Identifier Types in an Operator and Values Permissions Table](use-identity-provider-attributes-as-identifiers-in-data-access-controls-40f493f.md#loio40f493f922f24663aa8191ad1e79cb77__section_example_operator_and_values)



<a name="loio40f493f922f24663aa8191ad1e79cb77__section_prerequisites"/>

## Prerequisites

Your identity provider must be able to provide appropriate values in one or more of the following custom application attributes:

-   `custom1`
-   `custom2`
-   `custom3`
-   `custom4`
-   `custom5`

SAP Cloud Identity Services, for example, supports configuration of these attributes. If you are using a custom IDP, you must map your SAML IdP user attributes and roles to these attributes \(see [Configure Your Bundled SAP Cloud Identity Services Tenant](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/fac3155d77154775b919ceba36ffc325.html "Provision and configure your bundled SAP Cloud Identity Services tenant to authentication to SAP Datasphere.") :arrow_upper_right: or [Enabling a Custom SAML Identity Provider (Legacy Custom IdP)](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/9b26536159354aea9024a99cbbe60b4e.html "By default, SAP Cloud Identity is used by SAP Datasphere. SAP Datasphere also supports single sign-on (SSO), using your custom identity provider.") :arrow_upper_right:\).



<a name="loio40f493f922f24663aa8191ad1e79cb77__section_configure"/>

## Configure Custom Application Attributes

SAP Cloud Identity Services allows you to populate custom application attributes with values from standard or custom user attributes, including concatenating multiple user attributes together in a single application attribute.

For example, you could populate a custom application attribute with the value of:

-   The standard `City`, `Country`, `Company`, `Cost Center`, `Department`, or `Manager ID` user attribute.
-   Any of the ten custom user attributes.
-   An attribute coming from your corporate identity provider.

To review and modify your custom application attributes in SAP Cloud Identity Services:

1.  Select *Applications & Resources* \> *Applications*.
2.  Select your tenant in the list and then select *Attributes* on the *Trust* tab.
3.  Use the tools to configure one or more of the five custom attributes.

For detailed information, see [User Attributes](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/user-attributes?version=Cloud) in the *SAP Cloud Identity Services* documentation.



<a name="loio40f493f922f24663aa8191ad1e79cb77__section_use"/>

## Use Attributes as Identifiers in Permissions Entities

When using attributes to construct the criteria in your permissions entities, you must:

-   Have a column to specify the type of identifier to use:
    -   0 - Standard User Identifier
    -   1, 2, 3, 4, or 5 - `custom1` to `custom5` respectively.

-   Know the user attributes and possible values that are present in each of the configured custom application attributes.
-   Construct criteria to test against the values in those attributes.

For more details, see:

-   [Example: Using Country Identifiers in a Hierarchy with Directory Permissions Table](use-identity-provider-attributes-as-identifiers-in-data-access-controls-40f493f.md#loio40f493f922f24663aa8191ad1e79cb77__section_example_hwd)
-   [Example: Combining Identifier Types in an Operator and Values Permissions Table](use-identity-provider-attributes-as-identifiers-in-data-access-controls-40f493f.md#loio40f493f922f24663aa8191ad1e79cb77__section_example_operator_and_values)



<a name="loio40f493f922f24663aa8191ad1e79cb77__section_example_hwd"/>

## Example: Using Country Identifiers in a *Hierarchy with Directory* Permissions Table

In this example:

-   `custom1` is configured to contain the standard `Country` user attribute.
-   The permissions table is configured to support data access controls of type *Hierarchy with Directory*.


<table>
<tr>
<th valign="top">

Permission ID

</th>
<th valign="top">

ID Type

</th>
<th valign="top">

ID

</th>
<th valign="top">

Restriction Column

</th>
<th valign="top">

Target Node Type Column

</th>
<th valign="top">

Root Node Type Column

</th>
<th valign="top">

Root Values Column

</th>
<th valign="top">

Hierarchy Identifiers Column

</th>
</tr>
<tr>
<td valign="top">

`1`

</td>
<td valign="top">

1

</td>
<td valign="top">

`France`

</td>
<td valign="top">

`0`

</td>
<td valign="top">

`Employee`

</td>
<td valign="top">

`Country`

</td>
<td valign="top">

`France`

</td>
<td valign="top">

`1\1`

</td>
</tr>
<tr>
<td valign="top">

`2`

</td>
<td valign="top">

1

</td>
<td valign="top">

`Germany`

</td>
<td valign="top">

`0`

</td>
<td valign="top">

`Employee`

</td>
<td valign="top">

`Country`

</td>
<td valign="top">

`Germany`

</td>
<td valign="top">

`1\1`

</td>
</tr>
<tr>
<td valign="top">

`3`

</td>
<td valign="top">

1

</td>
<td valign="top">

`USA`

</td>
<td valign="top">

`0`

</td>
<td valign="top">

`Employee`

</td>
<td valign="top">

`Country`

</td>
<td valign="top">

`USA`

</td>
<td valign="top">

`1\1`

</td>
</tr>
</table>

Based on these records:

-   All users with the attribute `custom1` containing the value `France`, `Germany`, or `USA` will be granted access to records belonging to the respective country in hierarchy `1\1`.



<a name="loio40f493f922f24663aa8191ad1e79cb77__section_example_operator_and_values"/>

## Example: Combining Identifier Types in an *Operator and Values* Permissions Table

In this example:

-   `custom2` is configured to contain country codes from a custom user attribute.
-   `custom3` is configured to contain the standard `Department` user attributes
-   The permissions table is configured to support data access controls of type *Operator and Values*:


<table>
<tr>
<th valign="top">

Permission ID

</th>
<th valign="top">

ID Type

</th>
<th valign="top">

ID

</th>
<th valign="top">

Restriction

</th>
<th valign="top">

Criterion

</th>
<th valign="top">

Operator

</th>
<th valign="top">

First Value

</th>
<th valign="top">

Second Value

</th>
</tr>
<tr>
<td valign="top">

`1`

</td>
<td valign="top">

2

</td>
<td valign="top">

`FR`

</td>
<td valign="top">

`0`

</td>
<td valign="top">

`Country`

</td>
<td valign="top">

`EQ`

</td>
<td valign="top">

`FR`

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`2`

</td>
<td valign="top">

2

</td>
<td valign="top">

`DE`

</td>
<td valign="top">

`0`

</td>
<td valign="top">

`Country`

</td>
<td valign="top">

`EQ`

</td>
<td valign="top">

`DE`

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`3`

</td>
<td valign="top">

3

</td>
<td valign="top">

`Legal`

</td>
<td valign="top">

`0`

</td>
<td valign="top">

`Department`

</td>
<td valign="top">

`EQ`

</td>
<td valign="top">

`Legal`

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`4`

</td>
<td valign="top">

3

</td>
<td valign="top">

`Finance`

</td>
<td valign="top">

`0`

</td>
<td valign="top">

`Department`

</td>
<td valign="top">

`EQ`

</td>
<td valign="top">

`Finance`

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

5

</td>
<td valign="top">

0

</td>
<td valign="top">

`bob@acme.com`

</td>
<td valign="top">

`200`

</td>
<td valign="top">

`Admin`

</td>
<td valign="top">

`ALL`

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
</table>

Based on these records:

-   The common Restriction ID, 0, means that lines 1-4 work together to restrict data based on the combined values of `custom2` \(`Country`\) and `custom3` \(`Department`\) to ensure that each user is granted access only to the records for her department in her country.
-   Bob has access to all records thanks to the `ALL` operator.

    > ### Note:  
    > There are no restrictions for mixing criteria for user IDs \(0\) and user attributes \(1-5\) in a permissions table. However, you must be careful when setting restriction IDs to ensure that combinations are intentional:
    > 
    > -   To control access based on combinations of identifier types, you can share restriction identifiers as we do for restriction 0 above.
    > -   If you want to store multiple identifier types in a single permissions table but you want to control access based on a single identifier type at a time, you could reserve separate ranges of restriction IDs for each ID Type to avoid creating unwanted implicit ANDs. For example, the following ranges of restriction identifiers would help make the restrictions by country separate from the restrictions by department:
    >     -   0-99 - Reserved for Type 2 \(`Country`\)
    >     -   100-199 - Reserved for Type 3 \(`Department`\)
    >     -   200+ - Reserved for Type 0 \(`User ID`\)




<a name="loio40f493f922f24663aa8191ad1e79cb77__section_enable"/>

## Enable Attributes as Identifiers in Data Access Controls

When you create a data access control, user attributes are not supported by default. To enable this feature:

-   Click the *Allow IdP User Attributes as Identifiers* switch.
-   Select a permissions entity column for *Identifier Type Column*, which must contains only the values 0-5.
-   Select a permissions entity column for *Identifier Column*, which can contain user IDs and user attribute values.

