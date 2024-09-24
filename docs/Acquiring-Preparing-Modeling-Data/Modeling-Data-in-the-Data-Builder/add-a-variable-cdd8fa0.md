<!-- loiocdd8fa0fd74b495584dca343432f2814 -->

# Add a Variable

Add variables to your analytic model.

When you add a variable, the user will be prompted to enter a value in the data preview or when the analytic model is consumed in a story in SAP Analytics Cloud.

There are different types of variables to choose from:

-   standard variable: A standard variable is used in a fact source to map it to input parameters of the fact.
-   restricted measure variable: A restricted measure variable is used in the filter condition of a restricted measure \(e.g. “Revenue of selected country” with `country = <user input>`\). It can be applied only in restricted measures, and they do not filter the entire data.
-   filter variable: A filter variable refers to an attribute. When a story is opened, the variable dialog shows a filter for the attribute.
-   reference date variable: When the analytic model has associations to a time-dependent dimension or text table, you can define a reference date variable. With a reference data variable, you can filter the data using a specific date. This allows SAP Analytics Cloud users to enter a date of their choice for their story and show dimension members based on that date. For more information on time-dependent dimensions, see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md).



<a name="loiocdd8fa0fd74b495584dca343432f2814__section_lym_3ss_hvb"/>

## Use Variables in the Analytic Model

You must use each of the variables that you create in your analytic model or you will receive an error instructing you to use or delete them.

If an analytic model has more than one variable defined, you can change the order of variables in the editor by drag&drop. This order will be taken into account in the data preview and in the prompt in SAP Analytics Cloud.

