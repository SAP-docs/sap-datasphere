<!-- loio589908814adc4f16bb2e158794f9a96a -->

# Non-Cumulative Measures

Non-cumulative measures are processed in a specific way. In order to get the results you need, you need to understand the concepts used.



<a name="loio589908814adc4f16bb2e158794f9a96a__section_yhs_zjs_51c"/>

## Exception Aggregation

A non-cumulative measure cannot be aggregated over time as this would not lead to the expected result. Time-based aggregation is performed using "exception aggregation", which for example calculates the first, last, maximum or average value across a time period.

The standard aggregation specifies how non-time dimensions are aggregated, whereas the exception aggregation specifies how the time dimension is aggregated.

> ### Example:  
> In order to calculate the stock amount per week, you can specify exception aggregation type *First* to get the stock from the end of the first day of the week, and *Last* to get the stock of the last day of the week. Note that aggregation type *First* calculates the stock value at the end of the first day of the week.



<a name="loio589908814adc4f16bb2e158794f9a96a__section_wzd_cks_51c"/>

## Time Reference Dimension

You need a time reference dimension in the analytic model to be used for non-cumulative measures. In the underlying fact source the time dimension requires an attribute with data type *Date*. The attribute needs an association to a dimension. This time dimension is used to calculate the exception aggregation for a given time interval. This interval is defined by the earliest reporting start date and the latest reporting end date. When the earliest start and end dates are set, dimension values are filled up only for the specified interval. Without an interval all values in the time dimension table are used. It is essential to define this interval for a better performance, so that the calculation engine doesn't have to calculate using too many time values.

> ### Example:  
> When you are using SAPs day dimension generated using the *Create Time Tables and Dimensions* function in a space as time dimension and the data is generated for 1900 to 2050, then the drill down by date should show a value for each date through all the years \(approximately 150 years \* 365 days = 53400\). This master data table has too many values. Use the start/end time to reduce the master data values for which data is filled up.



<a name="loio589908814adc4f16bb2e158794f9a96a__section_kgy_rzv_y1c"/>

## Record Type

Inventory records need to have have additional information of the handling of the record. The allowed values for this column are `0` \(delta\), `1` \(reference point\), or `2` \(delta included in reference point\).

The data type of the record type column has to be *Integer*. In a simple scenario without reference point data the value should be 0 in all data rows.

The dimension containing the record type will always be auxiliary, and can not be removed from the analytic model when the analytic model contains a non-cumulative measure.



<a name="loio589908814adc4f16bb2e158794f9a96a__section_isn_2ks_51c"/>

## Reference Point

Using non-cumulative measures means that a reference point can be saved for every characteristic combination \(in addition to the posted data\). In this way, the retention and volume of data in the data load process is optimized.

Only one reference point is supported per dimension value combination without time, and for each fact delta record it can be specified whether this delta is contained in the reference point or not. The data contains details about the reference point. These are those that have a record type = 1.

