<!-- loiocdd8fa0fd74b495584dca343432f2814 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add a Variable

Add variables to your analytic model.

When you add a variable, the user will be prompted to enter a value in the data preview or when the analytic model is consumed in a story in SAP Analytics Cloud.

There are different types of variables to choose from:

-   source variable: A source variable is used in a fact source to map it to input parameters of the fact.
-   restricted measure variable: A restricted measure variable is used in the filter condition of a restricted measure \(e.g. “Revenue of selected country” with ***country = <user input\>***\). It can be applied only in restricted measures, and they do not filter the entire data.
-   filter variable: A filter variable refers to an attribute. When a story is opened, the variable dialog shows a filter for the attribute.
-   reference date variable: When the analytic model has associations to a time-dependent dimension or text table, you can define a reference date variable. With a reference data variable, you can filter the data using a specific date. This allows SAP Analytics Cloud users to enter a date of their choice for their story and show dimension members based on that date. For more information on time-dependent dimensions, see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md).



<a name="loiocdd8fa0fd74b495584dca343432f2814__section_cyh_jps_hvb"/>

## Create Source Variable

1.  You can create a new source variable by clicking the background of the canvas and choosing <span class="FPA-icons"></span> Add Variable in the properties panel. Choose *Source Variable*.
2.  Enter a name for your variable.
3.  You can set a default value.



<a name="loiocdd8fa0fd74b495584dca343432f2814__section_c1g_kps_hvb"/>

## Create Restricted Measure Variable

1.  You can create a new source variable by clicking the background of the canvas and choosing <span class="FPA-icons"></span> Add Variable in the properties panel. Choose *Restricted Measure Variable*.
2.  Choose the dimension for which the variable should be created.
3.  Choose the *Filter Type*. The filter can be
    -   a single value: The user should enter a single value to filter on. You can optionally specify a default value.
    -   multiple single values: Allows the user to enter more than one value to filter on.
    -   an interval: Allows the user to enter an interval of values to filter on.
    -   a range of values: Allows the user to enter a range of values to filter on.

4.  You can select *Mandatory*, if the user has to enter a value in the prompt in the preview or the story in SAC.



<a name="loiocdd8fa0fd74b495584dca343432f2814__section_w1s_3fx_gwb"/>

## Create a Filter Variable

You can create only one filter variable for each dimemsion.

1.  You can create a new filter variable by clicking the background of the canvas and choosing <span class="FPA-icons"></span> Add Variable in the properties panel. Choose *Filter Variable*.
2.  Choose the dimension for which the variable should be created.
3.  Choose the *Filter Type*. The filter can be
    -   a single value: The user should enter a single value to filter on. You can optionally specify a default value.
    -   multiple single values: Allows the user to enter more than one value \(or range of values\) to filter on.
    -   an interval: Allows the user to enter an interval of values to filter on.
    -   a range of values: Allows the user to enter a range of values to filter on.

4.  You can set a default value.
5.  You can select *Mandatory*, if the user has to enter a value in the prompt in the preview or the story in SAP Analytics Cloud.



<a name="loiocdd8fa0fd74b495584dca343432f2814__section_fkr_wfx_gwb"/>

## Create a Reference Date Variable

1.  You can create a new reference date variable by clicking the background of the canvas and choosing <span class="FPA-icons"></span> Add Variable in the properties panel. Choose *Reference Date Variable*.
2.  You can set a single value as a default value. The variable is always mandatory.



<a name="loiocdd8fa0fd74b495584dca343432f2814__section_lym_3ss_hvb"/>

## Use Variables in Analytic Model

You must use each of the variables that you create in your analytic model or you will receive an error instructing you to use or delete them.

