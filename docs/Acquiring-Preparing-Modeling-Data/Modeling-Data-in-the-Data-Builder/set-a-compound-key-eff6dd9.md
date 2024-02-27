<!-- loioeff6dd97723d4a70bc7612554fef09e3 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Set a Compound Key

In some cases, key columns aren’t enough to ensure the uniqueness of records. Defining a compound key ensures that records are uniquely identified.



## Prerequisites

You must meet the following prerequisites to be able to set a compound key:

-   set the *Semantic Usage* of your entity as *Dimension*, *Text*, or *External Hierarchy*.
-   define at least two columns as key columns.



## Context

Setting a single key column might not always be enough to ensure the uniqueness of records, and the combination of two or more key columns may be necessary. In such cases, you may need to set a compound key \(also known as composite key\).

A compound key is a key that consists of two or more key columns, namely a key column and a representative key. The representative key is the key holding the most specific/granular level of data. Together, these keys uniquely identify rows.

> ### Example:  
> You have two tables, `CostArea` and `CostCenter`:
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> CostArea
> 
> </th>
> <th valign="top">
> 
> Description
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> A
> 
> </td>
> <td valign="top">
> 
> Cost area A
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> B
> 
> </td>
> <td valign="top">
> 
> Cost area B
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> C
> 
> </td>
> <td valign="top">
> 
> Cost area C
> 
> </td>
> </tr>
> </table>
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> CostCenter
> 
> </th>
> <th valign="top">
> 
> Description
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> 1
> 
> </td>
> <td valign="top">
> 
> Cost center for 1
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> 2
> 
> </td>
> <td valign="top">
> 
> Cost center for 2
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> 3
> 
> </td>
> <td valign="top">
> 
> Cost center for 3
> 
> </td>
> </tr>
> </table>
> 
> You need to compound these two keys to ensure that records are uniquely identified. Setting a compound key column allows analytical tools to combine the columns `CostArea` and `CostCenter` in order to uniquely represent records in analytical tool via the `CostCenter(Representative Key)`. The compound key doesn't exist as an entity, but more like a semantic instruction for analytical tools. You may notice that the cost centers B2 and C3 don't exist:
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> CostArea
> 
> </th>
> <th valign="top">
> 
> CostCenter
> 
> </th>
> <th valign="top">
> 
> CostCenter \(Representative Key\)
> 
> </th>
> <th valign="top">
> 
> Description
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> A
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> <td valign="top">
> 
> A\\1
> 
> </td>
> <td valign="top">
> 
> Cost center 1 for the area A
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> A
> 
> </td>
> <td valign="top">
> 
> 2
> 
> </td>
> <td valign="top">
> 
> A\\2
> 
> </td>
> <td valign="top">
> 
> Cost center 2 for the area A
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> A
> 
> </td>
> <td valign="top">
> 
> 3
> 
> </td>
> <td valign="top">
> 
> A\\3
> 
> </td>
> <td valign="top">
> 
> Cost center 3 for the area A
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> B
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> <td valign="top">
> 
> B\\1
> 
> </td>
> <td valign="top">
> 
> Cost center 1 for the area B
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> B
> 
> </td>
> <td valign="top">
> 
> 3
> 
> </td>
> <td valign="top">
> 
> B\\3
> 
> </td>
> <td valign="top">
> 
> Cost center 3 for the area B
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> C
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> <td valign="top">
> 
> C\\1
> 
> </td>
> <td valign="top">
> 
> Cost center 1 for the area C
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> C
> 
> </td>
> <td valign="top">
> 
> 2
> 
> </td>
> <td valign="top">
> 
> C\\2
> 
> </td>
> <td valign="top">
> 
> Cost center 2 for the area C
> 
> </td>
> </tr>
> </table>
> 
> In an analytical tool, when selecting *CostCenter* as an attribute, the results will automatically be compounded with *CostArea* because *CostCenter* was set as a representative key..



## Procedure

1.  You can access the *Compound Key* dialog via two entry points:

    -   In the *Table Editor*, in the *Attributes* table toolbar, select at least two columns and click <span class="SAP-icons-V5"></span> \(Edit Compound Key\).

    -   In the*Graphical View* editor and *E/R Model* editor, in the *Properties* panel, in the *Attributes* section, click <span class="SAP-icons-V5"></span> \(Edit Compound Key\).

2.  \[optional\] Reorder keys in the *Key Column\(s\)* section by clicking <span class="FPA-icons-V3"></span> \(Move Up\) and <span class="SAP-icons-V5"></span> \(Move Down\).

3.  Define a representative key by selecting a key in the*Key Column\(s\)* section and clicking *Add*. The key has been transferred to the *Representative Key* section.

    In the *Compound Key* section, you can see the name of the compound key made out of the names of the key columns and representative key composing it.

4.  Click *Close* to finish setting the compound key and close the dialog.

    > ### Note:  
    > Closing the dialog without setting or after removing a representative key deletes the compound key.


