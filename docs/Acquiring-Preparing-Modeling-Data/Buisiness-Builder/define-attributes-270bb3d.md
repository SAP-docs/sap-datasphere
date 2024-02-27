<!-- loio270bb3d19df04d96adca12d182bafdfb -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Attributes

An Attribute is a descriptive element of a business entity.



## Context

It provides meaningful business insight into corresponding measures.



## Procedure

1.  Go to the *Attributes* tab.

2.  To define one attribute: Choose <span class="FPA-icons-V3"></span> *New attribute*.

    To define multiple attributes: Choose <span class="FPA-icons-V3"></span> *Add Attributes*. Select your attributes and choose *Apply*. To define the details for an attribute, choose <span class="FPA-icons-V3"></span> *Details*.

3.  Select the attribute type. More information: [Attribute Types](attribute-types-bc16160.md)

4.  You can define an identifier for an attribute.

    An identifier is an attribute which is closely connected to the attribute. Usually its the technical identifier.When you have an identifier defined, all the filters on this attribute will be applied to the indentifier, so that non-unique texts or texts, which are changing are filtered out.

    > ### Example:  
    > For the attribute *Customer Name* you define *Customer ID* as identifier. In the data preview, you can then choose if it should be displayed as <customer name\> \(<customer ID\>\), as <customer name\>, or as <customer ID\>.

5.  You can define attributes with texts and language dependent texts. This enables you to display your data with ID and text, or with a language dependent text, when you preview or analyze your data. For language dependent texts, the language in the user settings is taken.

    -   To display a text: Select Text. Then select the text attribute.
    -   To display a language dependent text: Select Language Dependent Text. Select the text table. The text table has to be defined in the Data Builder.

6.  Decide whether your attribute should be an *Auxiliary Attribute* meaning an attribute which can be used further within the business entity, but is not exposed to consumption models.

7.  Save your entries.


