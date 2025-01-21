<!-- loioe4cc3e8d37d9457bab52e42da00ded9f -->

# Create a Measure in an Analytic Model

You can create and add different types of measures to your analytic model.



## Context

Measures contain numerical values that you want to analyze.

There are different types of measures to choose from:

-   fact source measure: You can select any measure that is part of the fact source and add it to your analytic model.
-   calculated measure: A calculated measure references other measures and allows the combination of measures with elementary arithmetic \(operations of addition, subtraction, multiplication, and division\), and also more complex functions like maximum/minimum, IF \(as function\), mathematical functions like round, and conversion functions like convert to decfloat.
-   restricted measure: A restricted measure refers to another measure and allows restrictions on available dimensions.
-   count distinct measure: A count distinct measure counts unique occurrences of attributes \(e.g. in case multiple rows contain the country "Germany", it is counted only once\).
-   Currency conversion measure: With a currency conversion measure, you can convert currencies.
-   Non-cumulative measure: With non-cumulative measures, you can model cases where measure values describe a state that is not changing every day.

