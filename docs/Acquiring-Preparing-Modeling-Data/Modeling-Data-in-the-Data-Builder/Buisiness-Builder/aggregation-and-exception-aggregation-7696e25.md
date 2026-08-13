<!-- loio7696e2565f4f46eab42a91476526dfae -->

# Aggregation and Exception Aggregation

For measures, you can define a standard aggregation and an exception aggregation.

The aggregation behavior determines how measure values are aggregated in perspectives that use different attributes. In order to calculate the values of measures, the data from the perspective has to be aggregated to the detail level of the query. Now we take a look at the diffenrences between standard aggregation and an exception aggregation



<a name="loio7696e2565f4f46eab42a91476526dfae__section_lpb_fqk_4tb"/>

## Standard Aggregation

The basic form of aggregation is standard aggregation. When performing standard aggregation, the system can aggregate measures according to the following rules: SUM \(calculate the total value\), MIN \(calculate the minimum value\), MAX \(calculate the maximum value \), AVG \(calculate the average value\), and COUNT \(calculate the number of distinct values\). The standard aggregation is independent from a specific attribute. The system performs standard aggregation over all attributes that are not in the filter, irrespective of their sequence. This is the most well-known aggregation behavior.



<a name="loio7696e2565f4f46eab42a91476526dfae__section_shr_fqk_4tb"/>

## Exception Aggregation

In addition to standard aggregation, there is also exception aggregation. The aggregation rules for exception aggregation depend on an attribute. You specify how a measure is aggregated with regard to one or more attribute. An attribute is needed for exception aggregation in order to define the granularity with which the aggregation rule is applied. The system aggregates the measure to this detail level according to the rules of standard aggregation.

Exception aggregation is also always performed in addition to standard aggregation. It is not an alternative to standard aggregation.

> ### Caution:  
> Be aware that the settings in the consumption model or fact model concerning aggregation override the settings in the layer below. This means, that settings in the business entity will be overridden by the settings in the consumption model, and also settings in the fact model will be overridden by the settings in the consumption model.



<a name="loio7696e2565f4f46eab42a91476526dfae__section_pss_fqk_4tb"/>

## Example

Let us take aggregation rule \(AVG\) as an example: The system calculates the average from the sum of all values divided by the number of entries. To define the number of entries, a granularity of data must be defined to which the system is to aggregate the multi-dimensional data according to the rules of standard aggregation. The result of the standard aggregation is the starting point of the exception aggregation, as the basis for the calculation according to the *Average of All Values* rule.

From a business point of view for example, exception aggregation arises if warehouse stock cannot be totaled up at the time, or if counters count the number of characteristics for a specific characteristic.

