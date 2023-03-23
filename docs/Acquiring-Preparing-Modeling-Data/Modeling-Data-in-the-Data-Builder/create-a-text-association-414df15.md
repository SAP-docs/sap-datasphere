<!-- loio414df15a2e65402f9e133d89b343eb2e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Text Association



## Context

You need to link a text dependent dimension to a text entity thanks to a text association.



## Procedure

1.  Select your text dependent dimension to show its side panel. In the *Attributes* section, hover over an attribute and click <span class="FPA-icons"></span> \(More\) \> *Add Text Association*. The *Select Text Association Target* dialog opens and text entities available for association are listed.

2.  Select a target entity and click *OK*.

3.  Specify the text association mapping of attributes in the *Mappings* section:

    -   A default mapping is automatically created by matching a selected element to the first key element whose *Semantic Type* is *None*.
    -   To delete a mapping, select the link and then click <span class="FPA-icons"></span> \(Delete\).
    -   To manually map columns, drag a column from the left list and drop it onto a column in the right list.
    -   You can filter the *Mappings* section to show only all, mapped, or unmapped pairs of columns.
    -   You can filter or sort the left or right column lists independently

    The text dependent dimension is associated to the *Text* entity's attribute. The icon <span class="FPA-icons"></span> signals which attributes and associations are related to the dimension.

    > ### Note:  
    > You can also create a *Text Association* by going to the dimension's *Associations* section and clicking :arrow_right: \> *Text Association*.

4.  Click <span class="FPA-icons"></span> \(Save\) to save your entity:

    -   *Save* to save your object.
    -   *Save As* to create a local a copy of the object you're working on. The object must have been previously saved at least once. The *Save* dialog opens. Enter new business and technical names and click *Save*.

    Click <span class="SAP-icons"></span> \(Deploy\) to deploy your entity.


