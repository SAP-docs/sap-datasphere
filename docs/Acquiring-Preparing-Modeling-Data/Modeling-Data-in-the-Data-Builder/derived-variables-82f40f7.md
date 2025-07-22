<!-- loio82f40f73bbbf42a283648fa312a5aec2 -->

# Derived Variables

The value of a variable can be derived through a lookup entity.

The lookup entity can be any table or view. Derivation will always derive a single variable value only. Derived variables are not shown in the variable screen, as the value is retrieved by the system.

You can use the derivation, for example, to look up the currency for a respective country. The lookup entity provides the data for country/currency.

Using derived variables has the following advantages:

-   It can make it easier for the end user to enter a value in the variable prompt, e.g. it is easier to choose a country rather than a currency code.

-   You can reuse the variable within the analytic model:

    For example; the same currency conversion variable can be used for other currency conversion measures within the same analytic model.

-   You can reuse the lookup entity in other analytic models.
-   Changes can be governed centrally in the lookup entity.

