<!-- loio0373c60d7e614dd5b5189de767bb672b -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add a Prefix or a Suffix to Dimension Attributes

You can specify a custom prefix or suffix for the technical name of attributes.



## Context

The suffix/prefix is a dimension property that is added to all attributes of that dimension. This helps you to identify where an attribute originates from when your analytic model contains a dimension multiple times, as the attribute name is be taken from the source dimension and would be the same in each dimension.

> ### Example:  
> An analytic model contains the dimension *Employee* three times, as *Product Manager*, *Responsible* and *Changed By*. You can add the prefix PM for *Employee* in *Product Manager*, the prefix RESP for *Employee* in *Responsible*, and CB for the *Employee* in *Changed By*.



## Procedure

1.  Click on a dimension of the canvas to show its properties in the side panel.

2.  Choose <span class="FPA-icons-V3"></span> Edit to edit the prefix or suffix for the technical name of attributes. Note that prefixes cannot start with an underscore.

3.  You can reset the technical names of attributes.

    When you select *Reset all attributes to the original source names*, you can reset the technical names. When an attribute's technical name is renamed with a counter because of conflicts, this function removes that counter by resetting the technical name to match the source. This does not affect prefixes and suffixes.


