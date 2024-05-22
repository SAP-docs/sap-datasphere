<!-- loio414df15a2e65402f9e133d89b343eb2e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Text Association

Create a text association to link your entity to a text entity, which will provide text in one or more languages for an attribute.



## Procedure

1.  In the *Associations* section of your entity, click:arrow_right: \> *Text Association* to open the *Select Object* dialog listing available text entities.

    Alternatively, in a view side panel, in the *Attributes* section, hover over an attribute and click <span class="FPA-icons-V3"></span> \(More\) \> *Add Text Association*.

2.  Select a target entity and click *OK*.

    Find available objects by entering the object's name in the search bar or click <span class="FPA-icons-V3"></span> \(Show filters\) and filter by *Semantic Usage* or other criteria.

3.  In the *Mappings* section, map the appropriate attributes from your entity to those in the text entity:

    -   A default mapping is automatically created by matching a selected element to the first key element whose *Semantic Type* is *None*.
    -   To delete a mapping, select the link and then click <span class="FPA-icons-V3"></span> \(Delete\).
    -   To manually map columns, drag a column from the left list and drop it onto a column in the right list.
    -   You can filter the *Mappings* section to show all, mapped, or unmapped pairs of columns.
    -   You can filter or sort the left or right column lists independently

    > ### Note:  
    > When you have defined a compound key for a dimension, you must map all key columns to the text entity. You can only provide translations for the representative key column. Other key columns cannot be translated. See [Compound Keys and Representative Keys](set-key-columns-to-uniquely-identify-records-d9ef2c9.md#loiod9ef2c91f6d647e584bad51999e441cd__section_compound_keys).

    The icon <span class="FPA-icons-V3"></span> signals that an attribute is mapped to a text entity.

4.  Click <span class="FPA-icons-V3"></span> \(Save\)** \> *Save* to save your entity or click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy it immediately.

    For more information, see [Saving and Deploying Objects](../saving-and-deploying-objects-7c0b560.md).


