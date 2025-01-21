<!-- loio27075eeeba634f55be0b52e92cf88159 -->

# Add a Fact to an Analytic Model

As a source for your analytic model, you need an object of type fact.



## Context

The data type and semantic type information is inherited from the fact, as well as the standard aggregation behaviour for a measure. For fields with semantic type *Amount with Currency* and *Quantity with Unit* you only need to add the measure in the analytic model, the quantity or unit are added automatically.



## Procedure

1.  Browse or search for the object you want to add. The repository shows only the objects which can be used in an analytic model: facts.

2.  Drag your source from the Repository and drop it onto the canvas.

3.  Select the properties you want to copy from the source. You can still take over properties into your analytic model later.

4.  If the source is a view containing one or more input parameters, you must decide how each input parameter will be processed:

    -   *Map To*: Map the source input parameter to a variable in your analytic model. Users of this view will need to provide a value for the variable.
    -   *Set Value*: Enter a value to resolve the variable. The variable is resolved and users of this analytic model will no longer need to provide a value for it. If a value is already set by default, you can either set it or edit it by clicking the value and selecting another one in the list of available values of the *Select Member* dialog. The *Select Member* dialog is available only if a predefined default value has been defined in the input parameter.


