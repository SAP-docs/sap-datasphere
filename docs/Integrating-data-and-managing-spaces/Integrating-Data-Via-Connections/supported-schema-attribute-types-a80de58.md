<!-- loioa80de58e5171460b9f2b72c829f7a61a -->

# Supported Schema Attribute Types

Review which JSON/OpenAPI schema attribute types and format values are supported for custom connection types, and how each maps to a column type in the target local table on files.



> ### Caution:  
> Attribute types marked as not supported are skipped during replication.




<table>
<tr>
<th valign="top">

Schema Attribute Type

</th>
<th valign="top">

Supported

</th>
<th valign="top">

Target Column Type

</th>
<th valign="top">

Notes

</th>
</tr>
<tr>
<td valign="top">

number

</td>
<td valign="top">

Yes

</td>
<td valign="top">

DOUBLE

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

number, format: double

</td>
<td valign="top">

Yes

</td>
<td valign="top">

DOUBLE

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

number, format: float

</td>
<td valign="top">

No

</td>
<td valign="top">

\-

</td>
<td valign="top">

Will cause replication failure. Do not use.

</td>
</tr>
<tr>
<td valign="top">

integer

</td>
<td valign="top">

Yes

</td>
<td valign="top">

BIGINT

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

integer, format: int32

</td>
<td valign="top">

Yes

</td>
<td valign="top">

INTEGER

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

integer, format: int64

</td>
<td valign="top">

Yes

</td>
<td valign="top">

BIGINT

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

string

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

string, format: date

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Format annotation is used for format validation during runtime.

</td>
</tr>
<tr>
<td valign="top">

string, format: date-time

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Format annotation is used for format validation during runtime.

</td>
</tr>
<tr>
<td valign="top">

string, format: uuid

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(36\)

</td>
<td valign="top">

Format annotation is used for format validation during runtime.

</td>
</tr>
<tr>
<td valign="top">

string, format: hostname

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Format annotation is used for format validation during runtime.

</td>
</tr>
<tr>
<td valign="top">

string, format: ipv4

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Format annotation is used for format validation during runtime.

</td>
</tr>
<tr>
<td valign="top">

string, format: ipv6

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Format annotation is used for format validation during runtime.

</td>
</tr>
<tr>
<td valign="top">

string, format: password

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Format annotation is ignored; treated as a plain string.

</td>
</tr>
<tr>
<td valign="top">

string, format: byte

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Format annotation is ignored; treated as a plain string.

</td>
</tr>
<tr>
<td valign="top">

string, format: time

</td>
<td valign="top">

No

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Will cause replication failure. Do not use.

</td>
</tr>
<tr>
<td valign="top">

string, format: timestamp

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

The format annotation is not enforced or validated by the runtime. Values are stored as plain strings with no format validation.

</td>
</tr>
<tr>
<td valign="top">

string with minLength/maxLength

</td>
<td valign="top">

Yes

</td>
<td valign="top">

VARCHAR\(5000\)

</td>
<td valign="top">

Can only be set by importing an OpenAPI schema. Values that don't meet the constraints are ignored during the replication.

</td>
</tr>
<tr>
<td valign="top">

boolean

</td>
<td valign="top">

Yes

</td>
<td valign="top">

BOOLEAN

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

array

</td>
<td valign="top">

No

</td>
<td valign="top">

\-

</td>
<td valign="top">

Simple array attributes are not replicated.

</td>
</tr>
</table>

