<!-- loio982f9a30d4ab49c8b019cfaf3dc08391 -->

# Rules for Technical Names

Rules and restrictions apply to the technical names of objects that you create in SAP Datasphere. The technical name by default is synchronized with the business name by using rules to automatically replace invalid characters.



When specifying the technical name of an object, bear in mind the rules and restrictions listed below:

> ### Note:  
> The technical names that you create can be displayed both within SAP Datasphere and in other SAP products that integrate with SAP Datasphere. We recommend that you do not include any sensitive business or personal data in technical names.


<table>
<tr>
<th valign="top">

Object Type

</th>
<th valign="top">

Rule

</th>
</tr>
<tr>
<td valign="top">

Spaces

</td>
<td valign="top">

The space ID can only contain uppercase letters, numbers, and underscores \(\_\). Reserved keywords, such as SYS, CREATE, or SYSTEM, must not be used. Unless advised to do so, the ID must not contain prefix \_SYS and should not contain prefixes: DWC\_, SAP\_. 

The maximum length is 20 characters.

Reserved keywords: SYS, PUBLIC, CREATE, SYSTEM, DBADMIN, MONITORING, PAL\_STEM\_TFIDF, SAP\_PA\_APL, DWC\_USER\_OWNER, DWC\_TENANT\_OWNER, DWC\_AUDIT\_READER, DWC\_GLOBAL, and DWC\_GLOBAL\_LOG.

Also, the keywords that are reserved for the SAP HANA database cannot be used in a space ID. See [Reserved Words](https://help.sap.com/docs/SAP_HANA_PLATFORM/4fe29514fd584807ac9f2a04f6754767/28bcd6af3eb6437892719f7c27a8a285.html) in the *SAP HANA SQL Reference Guide for SAP HANA Platform*.

</td>
</tr>
<tr>
<td valign="top">

Elastic Compute Nodes

</td>
<td valign="top">

The elastic compute node technical name can only contain lowercase letters \(a-z\) and numbers \(0-9\). It must contain the prefix: ds.

The minimum length is 3 and the maximum length is 9 characters.

</td>
</tr>
<tr>
<td valign="top">

SAP BW bridge instance

Remote tables generated during the import of analysis authorizations from a SAP BW or SAP BW∕4HANA system

</td>
<td valign="top">

The technical name can contain any characters except for the asterisk \(\*\), colon \(:\), and hash sign \(\#\). Also, tab, carriage return, and newline must not be used, and space must not be used at the start of the name. 

The maximum length is 50 characters.

</td>
</tr>
<tr>
<td valign="top">

Tables, views, or E/R models

</td>
<td valign="top">

The technical name can only contain alphanumeric characters and underscores \(\_\). 

The maximum length is 50 characters. 

</td>
</tr>
<tr>
<td valign="top">

Analytic models

</td>
<td valign="top">

The technical name can only contain alphanumeric characters and underscores \(\_\). 

The maximum length is 50 characters. 

</td>
</tr>
<tr>
<td valign="top">

Flows, intelligent lookups, task chains, or data access controls

</td>
<td valign="top">

The technical name can only contain alphanumeric characters and underscores \(\_\).

The maximum length is 50 characters.

</td>
</tr>
<tr>
<td valign="top">

Elements in the Data Builder \(column, join, projection, or aggregation nodes, for example\)

</td>
<td valign="top">

The technical name can only contain alphanumeric characters and underscores \(\_\).

The maximum length is 50 characters. 

</td>
</tr>
<tr>
<td valign="top">

Hierarchies created inside a dimension view

</td>
<td valign="top">

The technical name can only contain alphanumeric characters and underscores \(\_\). 

The maximum length is 10 characters. 

</td>
</tr>
<tr>
<td valign="top">

Associations

</td>
<td valign="top">

The technical name can only contain alphanumeric characters, underscores \(\_\), and dots \(.\).

The maximum length is 20 characters.

</td>
</tr>
<tr>
<td valign="top">

Input parameters

</td>
<td valign="top">

The technical name can only contain uppercase letters, numbers, and underscores \(\_\). 

The maximum length is 30 characters. 

</td>
</tr>
<tr>
<td valign="top">

Objects created in the Business Builder \(facts, dimensions, fact models, consumption models, or authorization scenarios, for example\)

</td>
<td valign="top">

The technical name can only contain alphanumeric characters and underscores \(\_\).

The maximum length is 30 characters.

</td>
</tr>
<tr>
<td valign="top">

Database analysis users

</td>
<td valign="top">

The user name suffix can only contain uppercase letters, numbers, and underscores \(\_\). This suffix is added to the default prefix DWCDBUSER\# to create your full user name. Note that you cannot change the prefix as it is a reserved prefix.

The maximum length of the user name suffix is 31 characters.

</td>
</tr>
<tr>
<td valign="top">

Database user groups

</td>
<td valign="top">

The user name suffix can only contain uppercase letters, numbers, and underscores \(\_\). This suffix is added to the default prefix DWCDBGROUP\# to create your full user group name. Note that you cannot change the prefix as it is a reserved prefix.

The maximum length of the user group name suffix is 30 characters.

</td>
</tr>
<tr>
<td valign="top">

Database users \(Open SQL schemas\)

</td>
<td valign="top">

The user name suffix can only contain uppercase letters, numbers, and underscores \(\_\). This suffix is added to the default prefix *<space ID\>*\# to create your full user name. Note that you cannot change the prefix.

The maximum length of the full database user name \(including the prefix\) is 41 characters.

</td>
</tr>
<tr>
<td valign="top">

Connections

</td>
<td valign="top">

The technical name can only contain alphanumeric characters and underscores \(\_\). Underscore \(\_\) must not be used at the start or end of the name.

The maximum length is 40 characters.

</td>
</tr>
</table>

The technical name by default is synchronized with the business name. While entering the business name, invalid characters are replaced in the technical name as follows:


<table>
<tr>
<th valign="top">

Rule

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

Reserved keywords which are not allowed are removed.

</td>
<td valign="top">

" `SYS`" ** \> ** ""

</td>
</tr>
<tr>
<td valign="top">

Leading underscores \(\_\) are removed.

</td>
<td valign="top">

"`_NAME`" ** \> ** "`NAME`"

</td>
</tr>
<tr>
<td valign="top">

Leading and trailing whitespaces \(" "\) are removed.

</td>
<td valign="top">

"`NAME` " ** \> ** "`NAME`"

</td>
</tr>
<tr>
<td valign="top">

Whitespaces \(" "\) within a name are replaced with underscores \(\_\).

</td>
<td valign="top">

"`NA ME`" ** \> ** "`NA_ME`"

</td>
</tr>
<tr>
<td valign="top">

Characters with diacritical signs are replaced with their basic character.

</td>
<td valign="top">

"`Namé`" ** \> ** "`Name`"

</td>
</tr>
<tr>
<td valign="top">

Non-alphanumeric characters are removed.

</td>
<td valign="top">

"`N$ME`" ** \> ** "`NME`"

</td>
</tr>
<tr>
<td valign="top">

Dots \(.\) and double quotes \("\) are replaced with underscores \(\_\).

</td>
<td valign="top">

"`N.AM"E`" ** \> ** "`N_AM_E`"

</td>
</tr>
<tr>
<td valign="top">

Leading dots \(.\) are removed.

</td>
<td valign="top">

"`.NAME`" ** \> ** "`NAME`"

</td>
</tr>
</table>

