<!-- loio1fc32b552d144ee6b504bd290be443c3 -->

# Prepare Input and Lookup Entities

Prepare your input entity, which you want to enrich, and your lookup entity, from which you want to retrieve columns to add to your intelligent lookup.

An intelligent lookup can join any two entities that have some kind of semantic relationship, even if the input entity is not able consistently to identify records in the lookup entity. It can be particularly helpful for harmonizing heterogeneous data \(including data from external sources\) in the following common situations:

-   Combine internal product data with retailer sales transactions
-   Combine OEM warranty claims with supplier data
-   Combine marketing data with official government data
-   Combine internal customer revenue data with externally-available data such stock price, turnover, market capitalization, number of employees

Identify and prepare your input and lookup entities as follows:


<table>
<tr>
<th valign="top">

Your Input Entity

</th>
<th valign="top">

Your Lookup Entity

</th>
</tr>
<tr>
<td valign="top">

-   Is a table or view that you want to enrich by joining it to a lookup entity.
-   Must contain a key column to uniquely identify each record.
-   Passes all of its columns to the output view produced by the intelligent lookup.
-   May contain transactional, master, or general data.
-   Must contain a column that can be used as the pairing column. You should choose:
    -   A column intended to identify individual objects of the type stored in the lookup table. These columns often end in *ID* \(such as a `Product ID`, `Customer ID`, or `Building ID`\) or are some other kind of unique identifier, like `Email Address`.
    -   If such a column does not exist, you may choose to create a calculated column and concatenate values from other columns into it to provide unique identifier values.
    -   If the column does not exist and cannot be easily created, or if the objects in the input and lookup entities are of the same type, select the key column.




</td>
<td valign="top">

-   Is a table or view that you want to join to your input entity, in order to enrich it.
-   Must contain a key column to uniquely identify each record.
-   Passes only columns that you identify as return columns to the output view produced by the intelligent lookup.
-   Will generally contain master data, such as:
    -   Product data
    -   Employee data
    -   Supplier data
    -   Customer data




</td>
</tr>
</table>

> ### Note:  
> Views containing input parameters \(see [Create an Input Parameter in a Graphical View](create-an-input-parameter-in-a-graphical-view-53fa99a.md)\) cannot be used as input or lookup entities in an intelligent lookup.

