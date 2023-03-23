<!-- loio73e8ba1a69cd4eeba722b458a253779d -->

# Script Operator Python Reference

Learn about the Python support offered by the data flow script operator.

This topic contains the following sections:

-   [Support for builtins, Numpy, and Pandas Modules](script-operator-python-reference-73e8ba1.md#loio73e8ba1a69cd4eeba722b458a253779d__section_modules)
-   [Support for builtins Exception Types](script-operator-python-reference-73e8ba1.md#loio73e8ba1a69cd4eeba722b458a253779d__section_exception_types)
-   [Data Mapping](script-operator-python-reference-73e8ba1.md#loio73e8ba1a69cd4eeba722b458a253779d__section_data_mapping)
-   [Basic Examples](script-operator-python-reference-73e8ba1.md#loio73e8ba1a69cd4eeba722b458a253779d__section_examples)
-   [Handling Decimal Types](script-operator-python-reference-73e8ba1.md#loio73e8ba1a69cd4eeba722b458a253779d__section_decimal_types)



<a name="loio73e8ba1a69cd4eeba722b458a253779d__section_modules"/>

## Support for builtins, Numpy, and Pandas Modules

The script operator offers support for data manipulation and vector operations via support for the `builtins` \(version 3.9\), `NumPy` \(version 1.21.5\), and `Pandas` \(version 1.2.5\) modules. In order to achieve a safe execution environment, some restrictions are applied.

> ### Note:  
> Use of the unsupported functions or objects listed here triggers an internal exception, resulting in a runtime data flow execution failure.


<table>
<tr>
<th valign="top">

Builtin Module \(version 3.9\)



</th>
<th valign="top">

NumPy Module \(version 1.21.5\)



</th>
<th valign="top">

Pandas Module \(version 1.2.5\)



</th>
</tr>
<tr>
<td valign="top">

All constants and functions in the Python `builtins` module are supported except the following:

-   eval
-   exec
-   compile
-   classmethod
-   staticmethod
-   breakpoint
-   memoryview
-   \_\_import\_\_\(\) i.e. import statement
-   input
-   open
-   dir
-   object
-   print
-   id
-   vars
-   hasattr
-   getattr and \_\_getattribute\_\_
-   setattr and \_\_setattr\_\_
-   delattr and \_\_delattr\_\_



</td>
<td valign="top">

All objects and functions in the `NumPy` module are supported \(using the standard `np` alias\) except the following:

-   load
-   save
-   savez
-   savez\_compressed
-   loadtxt
-   savetxt
-   genfromtxt
-   fromregex
-   fromfile
-   memmap
-   DataSource
-   ndarray.tofile
-   ndarray.dump



</td>
<td valign="top">

All objects and functions in the `Pandas` module are supported \(using the standard `pd` alias\) except the following:

-   read\_pickle
-   read\_table
-   read\_csv
-   read\_fwf
-   read\_clipboard
-   read\_excel
-   read\_json
-   read\_html
-   read\_hdf
-   read\_feather
-   read\_parquet
-   read\_sas
-   read\_spss
-   read\_gbq
-   read\_stata
-   read\_sql\_table
-   read\_sql\_query
-   io.excel.ExcelFile
-   io.excel.ExcelWriter
-   io.stata.StataReader
-   io.sql.SQLDatabase
-   io.sql.SQLiteDatabase
-   io.pytables.HDFStore
-   DataFrame.to\_pickle
-   DataFrame.to\_csv
-   DataFrame.to\_hdf
-   DataFrame.to\_sql
-   DataFrame.to\_excel
-   DataFrame.to\_html
-   DataFrame.to\_feather
-   DataFrame.to\_stata
-   DataFrame.to\_gbq
-   DataFrame.to\_clipboard
-   DataFrame.to\_json
-   DataFrame.to\_latex
-   DataFrame.to\_markdown
-   Series.to\_pickle
-   Series.to\_csv
-   Series.to\_excel
-   Series.to\_hdf
-   Series.to\_sql
-   Series.to\_clipboard
-   Series.to\_json
-   Series.to\_latex
-   Series.to\_markdown



</td>
</tr>
</table>

> ### Note:  
> These lists are subject to change.



<a name="loio73e8ba1a69cd4eeba722b458a253779d__section_exception_types"/>

## Support for builtins Exception Types

The following builtin exception types are supported for use in error handling.

-   ArithmeticError
-   AssertionError
-   AttributeError
-   BufferError
-   FloatingPointError
-   IndexError
-   KeyError
-   LookupError
-   NameError
-   NotImplementedError
-   OverflowError
-   RuntimeError
-   StopIteration
-   TypeError
-   UnboundLocalError
-   UnicodeDecodeError
-   UnicodeEncodeError
-   UnicodeError
-   UnicodeTranslateError
-   ValueError
-   ZeroDivisionError

> ### Note:  
> This list is subject to change.



<a name="loio73e8ba1a69cd4eeba722b458a253779d__section_data_mapping"/>

## Data Mapping

The incoming table from the input port is converted to a **Pandas** DataFrame before being passed as the `data` parameter to the transform function. Similarly, the table returned from the user code is converted from a **Pandas** DataFrame to the data types common to all the operators.

You can find the correspondence between the supported column data types and Python objects in the table below.


<table>
<tr>
<th valign="top">

Column Data Type



</th>
<th valign="top">

Python Class



</th>
<th valign="top">

dtype



</th>
<th valign="top">

Restrictions



</th>
<th valign="top">

Observation



</th>
</tr>
<tr>
<td valign="top">

Binary



</td>
<td valign="top">

byte



</td>
<td valign="top">

object



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Boolean



</td>
<td valign="top">

numpy.bool



</td>
<td valign="top">

bool



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Date



</td>
<td valign="top">

pandas.Timestamp



</td>
<td valign="top">

datetime64\[ns\]



</td>
<td valign="top">

Can only represent range: `1677-09-21` to `2262-04-11`



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

DateTime



</td>
<td valign="top">

pandas.Timestamp



</td>
<td valign="top">

datetime64\[ns\]



</td>
<td valign="top">

Can only represent range: `1677-09-21 00:12:43.145225` to `2262-04-11 23:47:16.854775807`



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Decimal



</td>
<td valign="top">

decimal.Decimal



</td>
<td valign="top">

object



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

DecimalFloat



</td>
<td valign="top">

decimal.Decimal



</td>
<td valign="top">

object



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Integer



</td>
<td valign="top">

int



</td>
<td valign="top">

int64\*



</td>
<td valign="top">

 



</td>
<td valign="top">

\*The smallest possible between uint8, uint16, uint32, and uint64 that can hold all values.



</td>
</tr>
<tr>
<td valign="top">

Integer64



</td>
<td valign="top">

int



</td>
<td valign="top">

int64



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

LargeBinary



</td>
<td valign="top">

bytes



</td>
<td valign="top">

object



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

LargeString



</td>
<td valign="top">

string



</td>
<td valign="top">

object



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

String



</td>
<td valign="top">

string



</td>
<td valign="top">

object



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Time



</td>
<td valign="top">

pandas.Timestamp



</td>
<td valign="top">

datetime64\[ns\]



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

TimeStamp



</td>
<td valign="top">

pandas.Timestamp



</td>
<td valign="top">

datetime64\[ns\]



</td>
<td valign="top">

Can only represent range:`1677-09-21 00:12:43.145225` to`2262-04-11 23:47:16.854775807`



</td>
<td valign="top">

 



</td>
</tr>
</table>

> ### Note:  
> In the presence of null values, the corresponding value in a DataFrame is of type pd.NA \(not available\). When null values are present, the columns have mixed types and the column dtype is object.



<a name="loio73e8ba1a69cd4eeba722b458a253779d__section_examples"/>

## Basic Examples

Type of incoming data is restricted to Pandas DataFrame.



### Example 1

> ### Sample Code:  
> ```
> 
> def transform(data):
>     return data[['first', 'customer_name', 'office_location']]
> ```

This script creates a projection from an incoming DataFrame. It assumes that there would be at least these three columns in the incoming DataFrame: `first`, `customer_name`, and `office_location`. That is an alternative way to say that the input table has at least these three attributes. The projection script then extracts only these three columns and returns them as a DataFrame.

Input table \(Example DataFrame stored locally in the script as data\):


<table>
<tr>
<th valign="top">

first



</th>
<th valign="top">

last



</th>
<th valign="top">

birthday



</th>
<th valign="top">

customer\_name



</th>
<th valign="top">

office\_location



</th>
</tr>
<tr>
<td valign="top">

John



</td>
<td valign="top">

Doe



</td>
<td valign="top">

2002-04-09 12:33:58



</td>
<td valign="top">

RedBull



</td>
<td valign="top">

Walldorf



</td>
</tr>
<tr>
<td valign="top">

Jane



</td>
<td valign="top">

Doe



</td>
<td valign="top">

2005-03-03 12:33:58



</td>
<td valign="top">

GoPro



</td>
<td valign="top">

São Leopoldo



</td>
</tr>
</table>

Output table \(Example returning DataFrame projection\):


<table>
<tr>
<th valign="top">

first



</th>
<th valign="top">

customer\_name



</th>
<th valign="top">

office\_location



</th>
</tr>
<tr>
<td valign="top">

John



</td>
<td valign="top">

RedBull



</td>
<td valign="top">

Walldorf



</td>
</tr>
<tr>
<td valign="top">

Jane



</td>
<td valign="top">

GoPro



</td>
<td valign="top">

São Leopoldo



</td>
</tr>
</table>

It expects that the output table has only these three attributes, `first`, `customer_name`, and `office_location`. If the output table schema is different in any ways from this, the data flow execution fails.



### Example 2

> ### Sample Code:  
> ```
> 
> def transform(data):
> df = data[['first','last']]
> df[full] =  df['first'] + '.' + df['last']
> return df
> ```

This script extracts the 'first' and 'last' columns of the incoming DataFrame, assuming that they exist in the input table, and stores these two columns as a separate DataFrame in the local variable 'df'. It then computes a third column email from the extracted columns, updates df, and returns it.

Input table \(Example DataFrame stored locally in the script as df\):


<table>
<tr>
<th valign="top">

first



</th>
<th valign="top">

last



</th>
</tr>
<tr>
<td valign="top">

John



</td>
<td valign="top">

Doe



</td>
</tr>
<tr>
<td valign="top">

Jane



</td>
<td valign="top">

Doe



</td>
</tr>
</table>

Output table \(Example returning DataFrame df\):


<table>
<tr>
<th valign="top">

first



</th>
<th valign="top">

last



</th>
<th valign="top">

full



</th>
</tr>
<tr>
<td valign="top">

John



</td>
<td valign="top">

Doe



</td>
<td valign="top">

John.Doe



</td>
</tr>
<tr>
<td valign="top">

Jane



</td>
<td valign="top">

Doe



</td>
<td valign="top">

Jane.Doe



</td>
</tr>
</table>

The data flow would fail if the input table has neither the first nor the last attribute, among others. Similarly, it would also fail if the output table schema does not consist of just these three attributes, `first`, `last`, and `full`.



### Example 3

> ### Sample Code:  
> ```
> 
> def transform(data):
>     timestamps = data['birthday'].apply(lambda x: pd.Timestamp(x))
>     data['birthday'] = timestamps.apply(lambda x: f'{x.month_name()} {x.day}, {x.year}, {x.day_name()}')
>     return data
> ```

This script assumes that there is a `birthday` column among others, with the string values in the incoming DataFrame. It first attempts to convert the string values of this column to pandas **Timestamp** and store as a Series. Finally, it makes a specific string representation of the birth days in the Series, using the methods and attributes from the **Timestamp** class, and updates the same in the original DataFrame, before returning the same.

Input table \(Example of incoming DataFrame as data\):


<table>
<tr>
<th valign="top">

first



</th>
<th valign="top">

last



</th>
<th valign="top">

birthday



</th>
</tr>
<tr>
<td valign="top">

John



</td>
<td valign="top">

Doe



</td>
<td valign="top">

2002-04-09 12:33:58



</td>
</tr>
<tr>
<td valign="top">

Jane



</td>
<td valign="top">

Doe



</td>
<td valign="top">

2005-03-03 12:33:58



</td>
</tr>
</table>

Output table \(Example returning DataFrame as data\):


<table>
<tr>
<th valign="top">

first



</th>
<th valign="top">

last



</th>
<th valign="top">

birthday



</th>
</tr>
<tr>
<td valign="top">

John



</td>
<td valign="top">

Doe



</td>
<td valign="top">

April 9, 2002, Tuesday



</td>
</tr>
<tr>
<td valign="top">

Jane



</td>
<td valign="top">

Doe



</td>
<td valign="top">

March 3, 2005, Thursday



</td>
</tr>
</table>

In this case, it assumes that the input and output tables have the same schema and data types.



<a name="loio73e8ba1a69cd4eeba722b458a253779d__section_decimal_types"/>

## Handling Decimal Types

To work with decimal types in the script operator, the built-in Python `Decimal` class should be used. There is no way or need to import it, as it is available for the user inside the body of the transform function. Few examples of using the `Decimal` type in the script operator are provided below.



### Example 4

> ### Sample Code:  
> ```
> 
> def transform(data):
>   data['start_date_utc_long']=Decimal('123456789012345678901')
>   return data
> ```

This script assumes that the input table has a column name dept\_no and dept\_name and it wants to add decimal type arbitrary column start\_date\_utc\_long to it. The actual data type precision of this column is assumed to be decimal\(21,0\) in the output table definition.

Input table \(Example of incoming DataFrame as data\):


<table>
<tr>
<th valign="top">

dept\_no



</th>
<th valign="top">

dept\_name



</th>
</tr>
<tr>
<td valign="top">

dept\_101



</td>
<td valign="top">

Audit



</td>
</tr>
<tr>
<td valign="top">

dept\_102



</td>
<td valign="top">

Advisory



</td>
</tr>
</table>

Output table \(Example returning DataFrame as data\):


<table>
<tr>
<th valign="top">

dept\_no



</th>
<th valign="top">

dept\_name



</th>
<th valign="top">

start\_date\_utc\_long



</th>
</tr>
<tr>
<td valign="top">

dept\_101



</td>
<td valign="top">

Audit



</td>
<td valign="top">

Decimal\("123456789012345678901"\)



</td>
</tr>
<tr>
<td valign="top">

dept\_102



</td>
<td valign="top">

Advisory



</td>
<td valign="top">

Decimal\("123456789012345678901"\)



</td>
</tr>
</table>

In this case, it assumes that the input and output tables have the same schema and data types.



### Example 5

> ### Sample Code:  
> ```
> 
> def transform(data):
>     data = data[data.salary > Decimal("1299.99")]
>     return data
> ```

This script assumes that the input table has a column name `salary` and this column is of data type `Decimal`. The script applies a filter on the column salary comparing the value of its contents to a python Decimal object and returns the filtered table.

Input table \(Example of incoming DataFrame as data\):


<table>
<tr>
<th valign="top">

first



</th>
<th valign="top">

last



</th>
<th valign="top">

salary



</th>
</tr>
<tr>
<td valign="top">

John



</td>
<td valign="top">

Doe



</td>
<td valign="top">

Decimal\("1099.99"\)



</td>
</tr>
<tr>
<td valign="top">

Jane



</td>
<td valign="top">

Doe



</td>
<td valign="top">

Decimal\("1599.50"\)



</td>
</tr>
</table>

Output table \(Example returning DataFrame as data\):


<table>
<tr>
<th valign="top">

first



</th>
<th valign="top">

last



</th>
<th valign="top">

salary



</th>
</tr>
<tr>
<td valign="top">

Jane



</td>
<td valign="top">

Doe



</td>
<td valign="top">

Decimal\("1599.50"\)



</td>
</tr>
</table>

The example assumes that the input and output tables have the same schema and data types.

