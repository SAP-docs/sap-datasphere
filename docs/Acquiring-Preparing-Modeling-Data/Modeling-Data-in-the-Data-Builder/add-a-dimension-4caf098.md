<!-- loio4caf0987e7c7460e878fb574f04bd6a4 -->

# Add a Dimension

You can add dimensions to your analytic model.



## Context

The source of your analytic model can contain associations to dimensions, texts, and hierarchies. Dimensions contain attributes that can be used to analyze and categorize measures defined in other entities. Attributes are used as dimensions in the analytic model. When you take over associated dimensions from your source, the object type is also taken over. Thus, you can easily build a multidimensional model in a star schema with the fact source in the center and the dimensions as direct associations.

These associations are supported:

-   Associations to dimensions \(associations to a table or a view with semantic usage Dimension\)
-   Associations to a text table \(associations to a table or a view with semantic usage Text\). They are automatically used by the analytic model if a dimension has a text association.
-   Association from a dimension to a hierarchy table. They are automatically used by the analytic model if a dimension has a hierarchy association.

You can also add dimensions of dimensions.

The graphic shows the star schema of the analytic model: the fact source is in the center and the dimensions are surrounding it. The dimension *Product ID* also has a dimension: *Product Category*.

![The analytic model is a multidimensional model in a star schema with the fact source in the center and the dimensions surrounding it.](images/DWC_-_Analytic_model_star_1587456.png)

Here, you can see that the same dimension can be included more than once. To be able to distiguish between the different roles of the dimension in the data preview and the story in SAP Analytics Cloud, you can give the dimensions different aliases. The alias enables you to give a dimension a more specific name for a field than the source provides.

> ### Example:  
> The dimension V\_Employees is included twice, but can be distiguished by the aliases *Responsible Manager*and *Product Manager*.

![The graphic has explanatory text.](images/DWC_-_analytic_model_dimensions_8e178de.png)



## Procedure

There are different ways to add dimensions:

1.  When you select your source, you can select the dimensions that you want to copy from the source.

2.  When you click on your fact source on the canvas, you can select associated dimensions and attributes in the properties panel on the right. The attributes are also treated as dimensions in the analytic model.

3.  When you click on a dimension on the canvas, you can select associated dimensions of the dimension in the properties panel on the right.

4.  To edit the properties of a dimension: Click on the dimension of the canvas to show its properties in the side panel. You can make the following changes here:

    -   You can change the alias of this item in the properties panel. The alias is the name that is shown in the story in SAP Analytics Cloud.
    -   You can add or deselect associated dimensions.
    -   You can add or deselect attributes.
    -   You can specify a custom prefix or suffix for the technical name of attributes. For more information, see [Add a Prefix or a Suffix](add-a-prefix-or-a-suffix-0373c60.md).


