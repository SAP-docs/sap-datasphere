<!-- loio5bbd14a328b549b2b53fce830ea25c15 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Fact Model

Fact models are reusable models you can use to streamline the creation of other models within the same business context.



## Prerequisites

You already have analytical datasets, dimensions, or fact models defined.



## Context

Fact models let you predefine an array of measures, attributes, and filters that are relevant to a specific business context. Fact models can then be reused in several use cases within that business context.

As an example, you have five consumption models that require the same ten calculated attributes. Instead of defining each of the ten calculated attributes five times, you can create a single fact model that includes those calculated attributes you need and reuse it in each consumption model where it's relevant.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Business Builder*\), select a space if necessary, and click *New Fact Model* to open the editor.

2.  Enter a title for your fact model.

3.  Choose the initial fact source you want to use in your fact model: you can choose analytical datasets, dimensions or fact models.

4.  Enter an alias for your initial fact source and click *Create*.

    At this point, your fact model is ready to use. You can also choose to include or remove measures and attributes relevant to several use cases within a same business context.

5.  \[optional\] Select the package to which the object belongs.

    Packages are used to group related objects in order to facilitate their transport between tenants.

    > ### Note:  
    > Once a package is selected, it cannot be changed here. Only a user with the DW Space Administrator role \(or equivalent privileges\) can modify a package assignment in the *Packages* editor.

    For more information, see [Creating Packages to Export](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/24aba84ceeb3416881736f70f02e3a0a.html "Users with the DW Space Administrator role can create packages to model groups of related objects for transport between tenants. Modelers can add objects to packages via the Package field, which appears in editors when a package is created in their space. Once a package is complete and validated, the space administrator can export it to the Content Network. The structure of your package is preserved and, as the objects it contains evolve, you can easily export updated versions of it.") :arrow_upper_right:.

6.  Define the *Measures* of your fact model. For more information, see [Define Measures](define-measures-d430469.md).

7.  Define the *Attributes* of your fact model. For more information see [Define Attributes](define-attributes-1ac4502.md).

8.  Define the *Dimension Sources* which should be exposed for consumption. For more information see [Expose Dimension Sources](expose-dimension-sources-1326689.md).

9.  Define the *Filters* of your fact model. For more information see [Define Filters](define-filters-e8df759.md).


