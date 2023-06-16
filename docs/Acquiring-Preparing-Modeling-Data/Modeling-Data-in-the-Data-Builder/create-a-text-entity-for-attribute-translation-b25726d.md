<!-- loiob25726df116b463e97435ba720e48ac9 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Text Entity for Attribute Translation

Select a *Semantic Usage* of *Text* to indicate that your entity contains strings with language identifiers to translate text attributes in other entities.



## Context

You have a dimension that has an attribute that contains data that needs to be translated. For example, a date dimension refers to months with numbers: `01` for January, `02` for February, `03` for March, and so on. The text entity can be used to translate these numbers into any language.



## Procedure

1.  In the table editor or view editor output node side panel, set the *Semantic Usage* property to *Text*.

2.  Specify your attributes \(see [Specify Attributes](specify-attributes-cedc59c.md)\).

    You must specify at least the following attributes:


    <table>
    <tr>
    <th valign="top">

    Content


    
    </th>
    <th valign="top">

    Key


    
    </th>
    <th valign="top">

    Semantic Type


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
        Identifier

    Identifies the master data member for which the text is provided.

    Example: `01`


    
    </td>
    <td valign="top">
    
        Yes


    
    </td>
    <td valign="top">
    
        None


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        Language Identifier

    Identifies the language in which the text is provided.

    Example: `en`


    
    </td>
    <td valign="top">
    
        Yes


    
    </td>
    <td valign="top">
    
        *Language*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        Validity Start Date

    \[optional\] For time-dependent text entities, specifies the date from which the text is valid \(see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md)\).

    Example: `01/01/2022`


    
    </td>
    <td valign="top">
    
        Yes


    
    </td>
    <td valign="top">
    
        *Business Date - From*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        Validity End Date

    \[optional\] For time-dependent text entities, specifies the date until which the text is valid.

    Example: `31/12/2022`


    
    </td>
    <td valign="top">
    
        No


    
    </td>
    <td valign="top">
    
        *Business Date - To*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        Text

    Provides the text in the appropriate language.

    Example: `January`


    
    </td>
    <td valign="top">
    
        No


    
    </td>
    <td valign="top">
    
        *Text*


    
    </td>
    </tr>
    </table>
    
3.  Set attributes as keys to indicate that the data they contain can uniquely identify records.

    > ### Note:  
    > You must set two or three key attributes for a *Text Entity*:
    > 
    > -   Identifier
    > -   Language Identifier
    > -   Validity Start Date - if time-dependency is required \(see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md)\)

    To set an attribute as a key column, select the checkbox in the *Key* column or hover over the attribute in the side panel and click <span class="FPA-icons"></span> \(Menu\)** \> *Set as Key*.

4.  Click <span class="FPA-icons"></span> \(Save\) to save your entity:

    -   *Save* to save your object.
    -   *Save As* to create a local a copy of the object you're working on. The object must have been previously saved at least once. The *Save* dialog opens. Enter new business and technical names and click *Save*.

    Click <span class="SAP-icons"></span> \(Deploy\) to deploy your entity.


