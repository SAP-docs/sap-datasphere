<!-- loio950d55834dee450c9f71786d8b14a634 -->

# Python Operator Reference

Learn about the Python support offered by the Python operator in a transformation flow in a file space.

This topic contains the following sections:

-   [Support for Python Standard Libraries](python-operator-reference-950d558.md#loio950d55834dee450c9f71786d8b14a634__section_standardlibraries)
-   [Basic Examples for Standard Libraries](python-operator-reference-950d558.md#loio950d55834dee450c9f71786d8b14a634__section_exampleslibraries)
-   [Support for builtins, Numpy, and Pandas Modules](python-operator-reference-950d558.md#loio950d55834dee450c9f71786d8b14a634__section_modules)
-   [Support for builtins Exception Types](python-operator-reference-950d558.md#loio950d55834dee450c9f71786d8b14a634__section_exception_types)
-   [Basic Examples for Exception Types](python-operator-reference-950d558.md#loio950d55834dee450c9f71786d8b14a634__section_examplesexceptiontypes)
-   [Handling Decimal Types](python-operator-reference-950d558.md#loio950d55834dee450c9f71786d8b14a634__section_decimal_types)
-   [Basic Examples for Decimal Types](python-operator-reference-950d558.md#loio950d55834dee450c9f71786d8b14a634__section_examplesdecimaltypes)



<a name="loio950d55834dee450c9f71786d8b14a634__section_standardlibraries"/>

## Support for Python Standard Libraries

The following standard python libraries are supported:

-   time
-   dateutil.parser
-   datetime
-   calendar
-   random
-   math
-   re

These libraries don’t have any alias and can be used directly.



<a name="loio950d55834dee450c9f71786d8b14a634__section_exampleslibraries"/>

## Basic Examples for Standard Libraries



### Example 1

> ### Sample Code:  
> ```
> 
> def transform(data): data['street_number'] =
> 	data['address'].apply(lambda x: (re.findall(r'\d+', x))[0]).astype(int)
> 	current_date = datetime.date.today()
> 	data['service_years']=data['date_of_joining'].apply(lambda x: current_date.year - x.year) 
> 	data["bonus_rounded"]=data["bonus"].apply(math.ceil) 
> 	return data
> ```

This code snippet creates three new columns:

-   `street_number [Integer]`: extracts the digits from the address column \(string type\) in the source table.
-   `bonus_rounded [Integer]`: rounds off the column bonus \(float type\) to nearest integer.
-   `service_years [Integer]`: calculates the difference between the current year and `date_of_joining` \(date type\).

**Source Table** 


<table>
<tr>
<th valign="top">

first

</th>
<th valign="top">

last

</th>
<th valign="top">

address

</th>
<th valign="top">

date\_of\_joining

</th>
<th valign="top">

bonus

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

123 St, Rock Valley

</td>
<td valign="top">

Feb 26, 2022

</td>
<td valign="top">

67.5

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

456 St, It Valley

</td>
<td valign="top">

Dec 9, 2005

</td>
<td valign="top">

90.75

</td>
</tr>
</table>

**Taget Table** 


<table>
<tr>
<th valign="top">

first

</th>
<th valign="top">

last

</th>
<th valign="top">

address

</th>
<th valign="top">

date\_of\_joining

</th>
<th valign="top">

bonus

</th>
<th valign="top">

service\_year

</th>
<th valign="top">

bonus\_rounded

</th>
<th valign="top">

street\_number

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

123 St, Rock Valley

</td>
<td valign="top">

Feb 26, 2022

</td>
<td valign="top">

6700

</td>
<td valign="top">

3

</td>
<td valign="top">

68

</td>
<td valign="top">

123

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

456 St, It Valley

</td>
<td valign="top">

Dec 9, 2005

</td>
<td valign="top">

9000

</td>
<td valign="top">

20

</td>
<td valign="top">

91

</td>
<td valign="top">

456

</td>
</tr>
</table>



### Example 2

> ### Sample Code:  
> ```
> 
> def transform(data):
> 	data['current_timestamp']=time.strftime('%Y-%m-%d %H:%M:%S')
> 	data[‘employee_rating’]= [random.randint(1,5) for _ in range(len(data))]
> 	data[‘day_of_the_week’]=data['date_of_joining’].apply(lambda x:calendar.day_name[dateutil.parser.parse(x).weekday()]) 
> 	return data
> ```

This code snippet expects a column `date_of_joining` of type `string` which has a date in `string` format. It uses the calendar library and fetches the `day_name` of the week by parsing it using the `dateutil.parser` library, and stores in the new column `day_of_the_week`.

The current timestamp is fetched with the help of the `timestamp` column and stored in `string` format using the `time` library and stored in the new column as `current_timestamp`.

The employee rating is assigned randomly in the range of 1 to 5 using the `random` library and stored in the new column `employee_rating`.

**Source Table** 


<table>
<tr>
<th valign="top">

first

</th>
<th valign="top">

last

</th>
<th valign="top">

address

</th>
<th valign="top">

date\_of\_joining

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

123 St, Rock Valley

</td>
<td valign="top">

24-09-1999

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

456 St, It Valley

</td>
<td valign="top">

23-10-2005

</td>
</tr>
</table>

**Target Table** 


<table>
<tr>
<th valign="top">

first

</th>
<th valign="top">

last

</th>
<th valign="top">

address

</th>
<th valign="top">

date\_of\_joining

</th>
<th valign="top">

current\_timestamp

</th>
<th valign="top">

day\_of\_the\_week

</th>
<th valign="top">

employee\_rating

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

123 St, Rock Valley

</td>
<td valign="top">

24-09-1999

</td>
<td valign="top">

2025-03-11 07:58:19

</td>
<td valign="top">

Friday

</td>
<td valign="top">

4

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

456 St, It Valley

</td>
<td valign="top">

23-10-2005

</td>
<td valign="top">

2025-03-11 07:58:19

</td>
<td valign="top">

Sunday

</td>
<td valign="top">

2

</td>
</tr>
</table>



<a name="loio950d55834dee450c9f71786d8b14a634__section_modules"/>

## Support for builtins, Numpy, and Pandas Modules

The Python operator offers support for data manipulation and vector operations via support for the `builtins` \(version 3.11\), `NumPy` \(version 1.26.4\), and `Pandas` \(version 2.2.2\) modules. In order to achieve a safe execution environment, some restrictions are applied.

> ### Note:  
> Use of the unsupported functions or objects listed here triggers an internal exception, resulting in a runtime transformation flow execution failure.


<table>
<tr>
<th valign="top">

Builtin Module \(version 3.11\)

</th>
<th valign="top">

NumPy Module \(version 1.26.4\)

</th>
<th valign="top">

Pandas Module \(version 2.2.2\)

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



<a name="loio950d55834dee450c9f71786d8b14a634__section_exception_types"/>

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



<a name="loio950d55834dee450c9f71786d8b14a634__section_examplesexceptiontypes"/>

## Basic Examples for Exception Types

Type of incoming data is restricted to Pandas DataFrame.



### Example 1

> ### Sample Code:  
> ```
> 
> def transform(data):
>     return data[['first', 'customer_name', 'office_location']]
> ```

This script creates a projection from an incoming DataFrame. It assumes that there would be at least these three columns in the incoming DataFrame: `first`, `customer_name`, and `office_location`. That is an alternative way to say that the source table has at least these three attributes. The projection script then extracts only these three columns and returns them as a DataFrame.

Source table \(Example DataFrame stored locally in the script as data\):


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

Target table \(Example returning DataFrame projection\):


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

It expects that the target table has only these three attributes, `first`, `customer_name`, and `office_location`. If the target table schema is different in any ways from this, the transformation flow execution fails.



### Example 2

> ### Sample Code:  
> ```
> 
> def transform(data):
> 	df = data[['first','last']]
> 	df[full] =  df['first'] + '.' + df['last']
> 	return df
> ```

This script extracts the 'first' and 'last' columns of the incoming DataFrame, assuming that they exist in the source table, and stores these two columns as a separate DataFrame in the local variable 'df'. It then computes a third column email from the extracted columns, updates the df, and returns it.

Source table \(Example DataFrame stored locally in the script as df\):


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

The transformation flow would fail if the source table has neither the first nor the last attribute, among others. Similarly, it would also fail if the target table schema does not consist of just these three attributes, `first`, `last`, and `full`.



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

Source table \(Example of incoming DataFrame as data\):


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

Target table \(Example returning DataFrame as data\):


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

In this case, it assumes that the source and target tables have the same schema and data types.



<a name="loio950d55834dee450c9f71786d8b14a634__section_decimal_types"/>

## Handling Decimal Types

To work with decimal types in the script operator, the built-in Python `Decimal` class should be used. There is no way or need to import it, as it is available for the user inside the body of the transform function. Few examples of using the `Decimal` type in the script operator are provided below.



<a name="loio950d55834dee450c9f71786d8b14a634__section_examplesdecimaltypes"/>

## Basic Examples for Decimal Types



### Example 1

> ### Sample Code:  
> ```
> 
> def transform(data):
>   data['start_date_utc_long']=Decimal('123456789012345678901')
>   return data
> ```

This script assumes that the source table has a column name dept\_no and dept\_name and it wants to add decimal type arbitrary column start\_date\_utc\_long to it. The actual data type precision of this column is assumed to be decimal\(21,0\) in the target table definition.

Source table \(Example of incoming DataFrame as data\):


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

Target table \(Example returning DataFrame as data\):


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

In this case, it assumes that the source and target tables have the same schema and data types.



### Example 2

> ### Sample Code:  
> ```
> 
> def transform(data):
>     data = data[data.salary > Decimal("1299.99")]
>     return data
> ```

This script assumes that the source table has a column name `salary` and this column is of data type `Decimal`. The script applies a filter on the column salary comparing the value of its contents to a python Decimal object and returns the filtered table.

Source table \(Example of incoming DataFrame as data\):


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

Target table \(Example returning DataFrame as data\):


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

The example assumes that the source and target tables have the same schema and data types.

