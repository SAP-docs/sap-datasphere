<!-- loio982f9a30d4ab49c8b019cfaf3dc08391 -->

# Rules for Technical Names

Rules and restrictions apply to the technical names of objects that you create in SAP Datasphere. The technical name by default is synchronized with the business name by using rules to automatically replace invalid characters.



When specifying the technical name of an object, bear in mind the following rules and restrictions:


<table>
<tr>
<th valign="top">

Object Type

</th>
<th valign="top">

Rule

</th>
<th valign="top">

Maximum Length

</th>
</tr>
<tr>
<td valign="top">

Space

</td>
<td valign="top">

The space ID can only contain uppercase letters, numbers, and underscores \(\_\). Reserved keywords, such as SYS, CREATE, or SYSTEM, must not be used. Unless advised to do so, the ID must not contain prefix \_SYS and should not contain prefixes: DWC\_, SAP\_. The maximum length is 20 characters.

Reserved keywords: SYS, PUBLIC, CREATE, SYSTEM, DBADMIN, MONITORING, PAL\_STEM\_TFIDF, SAP\_PA\_APL, DWC\_USER\_OWNER, DWC\_TENANT\_OWNER, DWC\_AUDIT\_READER, DWC\_GLOBAL, and DWC\_GLOBAL\_LOG.

Also, the keywords that are reserved for the SAP HANA database cannot be used in a space ID. See [Reserved Words](https://help.sap.com/docs/SAP_HANA_PLATFORM/4fe29514fd584807ac9f2a04f6754767/28bcd6af3eb6437892719f7c27a8a285.html) in the *SAP HANA SQL Reference Guide for SAP HANA Platform*.

</td>
<td valign="top">

20

</td>
</tr>
<tr>
<td valign="top">

Elastic Compute Node

</td>
<td valign="top">

The elastic compute node technical name can only contain lowercase letters \(a-z\) and numbers \(0-9\). It must contain the prefix: ds. The minimum length is 3 and the maximum length is 9 characters.

</td>
<td valign="top">

9

</td>
</tr>
<tr>
<td valign="top">

SAP BW bridge instance

Remote table generated during the import of analysis authorizations from a SAP BW or SAP BW∕4HANA system

</td>
<td valign="top">

The technical name can contain any characters except for the asterisk \(\*\), colon \(:\), and hash sign \(\#\). Also, tab, carriage return, and newline must not be used, and space must not be used at the start of the name. The maximum length is 50 characters.

</td>
<td valign="top">

50

</td>
</tr>
<tr>
<td valign="top">

Object created in the Data Builder, for example a table, view, or E/R model

</td>
<td valign="top">

The technical name can only contain alphanumeric characters and underscores \(\_\). The maximum length is 50 characters.

</td>
<td valign="top">

50

</td>
</tr>
<tr>
<td valign="top">

Element in the Data Builder, for example a column, or a join, projection, or aggregation node

</td>
<td valign="top">

The technical name can only contain alphanumeric characters and underscores \(\_\). The maximum length is 30 characters.

</td>
<td valign="top">

30

</td>
</tr>
<tr>
<td valign="top">

Object created in the Business Builder, for example a fact, dimension, fact model, consumption model, or authorization scenario

</td>
<td valign="top">

The technical name can only contain alphanumeric characters and underscores \(\_\). The maximum length is 30 characters.

</td>
<td valign="top">

30

</td>
</tr>
<tr>
<td valign="top">

Association

</td>
<td valign="top">

The technical name can only contain alphanumeric characters, underscores \(\_\), and dots \(.\). The maximum length is 10.

</td>
<td valign="top">

10

</td>
</tr>
<tr>
<td valign="top">

Input parameter

</td>
<td valign="top">

The technical name can only contain uppercase letters, numbers, and underscores \(\_\). The maximum length is 30 characters.

</td>
<td valign="top">

30

</td>
</tr>
<tr>
<td valign="top">

Database analysis user

</td>
<td valign="top">

The user name suffix can only contain uppercase letters, numbers, and underscores \(\_\). The maximum length is 41 characters. This suffix is added to the default prefix DWCDBUSER\# to create your full user name. Note that you cannot change the prefix as it is a reserved prefix.

</td>
<td valign="top">

31 \(40 minus prefix\)

</td>
</tr>
<tr>
<td valign="top">

Database user group user

</td>
<td valign="top">

The user name suffix can only contain uppercase letters, numbers, and underscores \(\_\). The maximum length is 41 characters. This suffix is added to the default prefix DWCDBGROUP\# to create your full user name. Note that you cannot change the prefix as it is a reserved prefix.

</td>
<td valign="top">

30 \(40 minus prefix\)

</td>
</tr>
<tr>
<td valign="top">

Database user \(Open SQL schema\)

</td>
<td valign="top">

The user name suffix can only contain uppercase letters, numbers, and underscores \(\_\). The maximum length is 41 characters. This suffix is added to the default prefix <space ID\>\# to create your full user name. Note that you cannot change the prefix.

</td>
<td valign="top">

40 minus space name \(or 41 minus prefix\)

</td>
</tr>
<tr>
<td valign="top">

Connection

</td>
<td valign="top">

The technical name can only contain alphanumeric characters and underscores \(\_\). Underscore \(\_\) must not be used at the start or end of the name. The maximum length is 40 characters.

</td>
<td valign="top">

40

</td>
</tr>
<tr>
<td valign="top">

Data access control

</td>
<td valign="top">

The technical name can only contain alphanumeric characters, and underscores \(\_\). The maximum length is 50 characters.

</td>
<td valign="top">

50

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

