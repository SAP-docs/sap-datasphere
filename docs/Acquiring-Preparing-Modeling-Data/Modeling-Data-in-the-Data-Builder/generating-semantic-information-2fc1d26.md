<!-- loio2fc1d26ebff748e4905d724247d33531 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Generating Semantic Information

Use the *Generate Semantics* command to request SAP Datasphere to suggest a *Semantic Usage* for your entity, identify measures and attributes, and apply appropriate semantic types to them.

1.  Open your table or view in its editor, and click <span class="SAP-icons-V5"></span> \(Generate\)** \> *Generate Semantics*.
2.  In the dialog, select options as appropriate:


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Select Semantic Usage \(Fact, Dimension, Text\)
    
    </td>
    <td valign="top">
    
    Instruct SAP Datasphere to select the appropriate *Semantic Usage* for your entity.

    > ### Note:  
    > SAP Datasphere will choose from among `Fact`, `Dimension`, and `Text`. It cannot identify hierarchies or other semantic usages.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Identify Measures and Attributes and Set Keys and Semantic Types
    
    </td>
    <td valign="top">
    
    Instruct SAP Datasphere to:

    -   Sort columns into measures and attributes.
    -   Set keys where appropriate.
    -   Apply the necessary semantic type to each column to allow it to be used in analytics.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Do Not Override Existing Column Metadata
    
    </td>
    <td valign="top">
    
    Instruct SAP Datasphere to ignore any column that already has a semantic type applied.
    
    </td>
    </tr>
    </table>
    
3.  Click *Generate*.

    When generation is complete, your entity's properties will be updated to reflect the new semantic usage. Changes may be made to the following properties:

    -   Entity *Semantic Usage* property.
    -   Movement of items from the *Columns* or *Attributes* list to the *Measures* list.
    -   Column *Key* property.
    -   Column *Semantic Type* property.

4.  Review the changes to ensure that they are appropriate. Changes are highlighted in blue, and next to each is a <span class="SAP-icons-V5"></span> \(Review\) button, which you can click to see the reasoning behind the change and the previous values

    If you do not agree with a change, you can click *Revert Changes* to undo it.

5.  Click <span class="FPA-icons-V3"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy it immediately. 

    For more information, see [Saving and Deploying Objects](../saving-and-deploying-objects-7c0b560.md).


