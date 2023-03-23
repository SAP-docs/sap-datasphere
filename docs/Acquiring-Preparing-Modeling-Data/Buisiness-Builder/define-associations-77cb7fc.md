<!-- loio77cb7fc523d54747ba8e9ecb928d493e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Define Associations

An association describes the relation between business entities.



## Context

The associated business entities will be available as dimensions when you create a consumption model.



## Procedure

1.  Go to the *Associations* tab.

2.  Choose <span class="FPA-icons"></span> *Create*.

3.  Select your target business entity. The information *Referential Integrity Ensured* is used for performance optimizations during querying. If switched on, it indicates that each data record of the currently opened business entity finds a match in the selected target business entity with the configured key mapping. If there is no match found for every data record but *Referential Integrity Ensured* is switched on, it can impact the result during querying.

4.  Define which fields of the business entity shall function as keys.

    1.  Select a key offered by the target business entity via the drop-down menu.
    2.  Map the corresponding target key field to the corresponding field of the current business entity.
    3.  You get a message on the key mapping validation: This provides you feedback on how many entries within the current business entity there are and how many of them match to entries of the target business entity. This information shall help you evaluate whether the set configuration makes sense.

5.  Via *Association Context* you can provide information on the context of the association within the business entity. This allows for multiple associations between the same business entities \(in different contexts\) and provides additional business meaning to the association. The context will be available as additional information on every usage of the association, e.g. in a consumption model. To define a context, you can provide:

    -   a title \(max. 120 characters & special characters allowed\)
    -   a description \(max. 5000 characters & special characters allowed\)


