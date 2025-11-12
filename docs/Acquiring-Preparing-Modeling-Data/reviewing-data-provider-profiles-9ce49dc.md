<!-- loio9ce49dcb70df4065880342beec03e25e -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Reviewing Data Provider Profiles

Use the catalog *Data Providers* collection to search for data providers. You can see their profile details and find out which data products they offer.



From the catalog search page, you can select the *Data Providers* collection and then select one or more filters to narrow the search results. This collection is only available in the SAP Datasphere catalog.

The search results provides high-level information about a data provider, including their name and a short description. If you want to know more about a data provider, select their name to view their profile page that provides all legally required and additional information, such as company and contact information and general information about the data products offered, including the industry your data products belong to and the SAP applications that are related to your data products.

Data provider profiles are managed by the data provider themselves or by a content aggregator.

-   A data provider is a person or company that offers one or multiple data products.
-   A content aggregator is a company managing one or multiple data provider profiles and their available data products.

To learn more, see [Data Provider Vs Content Aggregator](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/ba1b703d905547b392c09b35c1028de1.html "Data Marketplace content can either be created by a data provider or a content aggregator.") :arrow_upper_right:.

For example, if you’re a content aggregator, you might want to review the data provider profile of a company you manage to ensure that their information is correct and their data offerings are current. If any changes are needed, go to the Data Sharing Cockpit to make them. For more information, see [Maintaining your Data Provider Profile](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/4d298f8654fe4a6c9b6a4399a9e14c77.html "Provide information as you would like to present it to consumers of Data Marketplace. Provide company and business contact information as well as general information about the data you offer.") :arrow_upper_right:.



The data provider details header provides high-level information about the data provider and organizes the information as shown in the following table.


<table>
<tr>
<th valign="top">

Section

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Displays the name of the data provider.

</td>
</tr>
<tr>
<td valign="top">

Active Data Products and Product Views

</td>
<td valign="top">

Displays the number of published data products and the total number of views for all data products.

</td>
</tr>
</table>

In the header, you'll also be able to see a toolbar with actions available for all catalog users.

-   *Contact*: Opens an email message that you can edit and send to the data provider.
-   <span class="FPA-icons-V3"></span> \(Add to Favorites\): Adds frequently viewed data providers to your favorites.



<a name="loio9ce49dcb70df4065880342beec03e25e__section_cwg_yzm_bdc"/>

## Data Provider's Description and Properties

In the *Overview* tab, you'll find a description of the data provider and their other properties organized into the following groups: data provider details and contact details. To view the properties, select *Overview* \> *Properties*.

Review the following descriptions for the content you'll see. If a property is not described here, please see the documentation for the data provider.

> ### Tip:  
> If the property is related to a search filter, each value appears as a link that you can select. The link opens the catalog search page with the filter value applied.

**Data Provider Properties**

Displays properties for the data provider, such as the following:

Displays the contact details for the data provider and content aggregator, which can include the email address, address, and phone number. A content aggregator is a company that manages one or multiple data provider profiles and that creates the data product content on behalf of one or multiple data providers. For more information, see [Data Provider Vs Content Aggregator](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/ba1b703d905547b392c09b35c1028de1.html "Data Marketplace content can either be created by a data provider or a content aggregator.") :arrow_upper_right:.

**Data Provider Properties**


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Business Name

</td>
<td valign="top">

Displays the data provider's business name.

</td>
</tr>
<tr>
<td valign="top">

URL

</td>
<td valign="top">

Displays a link to the data provider's website.

</td>
</tr>
<tr>
<td valign="top">

Marketplace Visibility

</td>
<td valign="top">

Displays the marketplace visibility of the data provider profile. The visibility affects which contexts have visible access to the data products. Data products can have the following visibilities:

-   *Public Data Provider*: Data products are visible for everyone in the context owned by SAP and are available in the *Data Products \(Marketplace\)* collection.

-   *Private Data Provider*: Data products are visible to users that are members of contexts created by the data provider and are available in the *Data Products \(Marketplace\)* collection. These type of contexts include Private Data Products, Private Data Exchange, or Data Shop.

-   *Internal Data Provider*: Data products are visible to only members who belong to systems that have been specified in your contexts and are available in the *Data Products \(Marketplace\)* collection. Data providers can also restrict the visibility to individual users.

-   *Formations*: Data products are available to all users in the *Data Products* collection.


A data provider can have both public and private visibility options. The internal and formation options cannot be used with the other options. For more information, see [Using Contexts to Realize Public, Private, and Internal Data Marketplaces](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/c936499e7ef045b09139723fd0ac9e09.html "Use contexts to realize private or internal data marketplaces by restricting the visibility of your data provider profile and your data products to selected users only.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

Data Category

</td>
<td valign="top">

Displays one or more categories that the data provider has data products for.

</td>
</tr>
<tr>
<td valign="top">

Provider Data Products

</td>
<td valign="top">

Displays the total number of data products that the data provider has in the catalog.

</td>
</tr>
<tr>
<td valign="top">

Regional Coverage

</td>
<td valign="top">

Displays the countries and regions that the data provider has data products for.

</td>
</tr>
<tr>
<td valign="top">

Data Shipment

</td>
<td valign="top">

Displays the data shipment types the data provider supports.

-   *Integrated Delivery*: The data is copied directly into the selected space. After the data product is activated, it is visible in the *Repository Explorer*, where it can be selected for use in an SAP Datasphere project. For example, the data product can be used as a source in the *Data Builder*. This type of data shipment is managed by Data Marketplace.
-   *External Delivery*: The data is delivered by sharing files outside SAP Datasphere. This type of data shipment is managed by the data provider.
-   *Open SQL*: The data is delivered by using an Open SQL Schema. Consumers create an OpenSQL Schema in the space and provide the information to the data provider using the Data Inbox. Once the data product is activated, consumers can access the data through the *Data Builder* and the provided schema appears as a source. This type of data shipment is managed by the data provider.



</td>
</tr>
<tr>
<td valign="top">

SAP Store ID

</td>
<td valign="top">

Displays the data provider's SAP store customer number.

</td>
</tr>
<tr>
<td valign="top">

Industry

</td>
<td valign="top">

Displays one or more industries that the data provider has data products for.

</td>
</tr>
<tr>
<td valign="top">

SAP Application

</td>
<td valign="top">

Displays one or more SAP applications that the data provider has data products for.

</td>
</tr>
</table>

**Contact Details**

Displays the contact details for the data provider and content aggregator, which can include the email address, address, and phone number. A content aggregator is a company that manages one or multiple data provider profiles and that creates the data product content on behalf of one or multiple data providers. For more information, see [Data Provider Vs Content Aggregator](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/ba1b703d905547b392c09b35c1028de1.html "Data Marketplace content can either be created by a data provider or a content aggregator.") :arrow_upper_right:.



<a name="loio9ce49dcb70df4065880342beec03e25e__section_y52_qcn_bdc"/>

## Data Provider's Data Products

To see what types of data products the data provider offers, select the *Data Products* tab. This tab provides a list of all active and inactive data products from the data provider. If the data provider has a lot of data products, select the *Show All* link to see a filtered view of the catalog search results for that data provider.

**Data Provider's Data Products**


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Displays the data product name. Select the link to open the data product details page.

> ### Tip:  
> To get a better understanding of a data product, you can view the impact and lineage analysis diagram from the data product details page. See the section **Impact and Lineage Analysis Diagram for a Marketplace Data Product** in [Marketplace Data Product Details](marketplace-data-product-details-f59e912.md).



</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Displays a description of the data product.

</td>
</tr>
<tr>
<td valign="top">

Contexts

</td>
<td valign="top">

Displays the contexts that the data provider has data products for.

</td>
</tr>
<tr>
<td valign="top">

Access

</td>
<td valign="top">

Displays the license access type for the data product.

</td>
</tr>
</table>



<a name="loio9ce49dcb70df4065880342beec03e25e__section_gnd_zcn_bdc"/>

## Next Steps

Now that you've reviewed the data provider's profile and have seen their data products, what's next?


<table>
<tr>
<th valign="top">

If you are a ...

</th>
<th valign="top">

You can ...

</th>
<th valign="top">

Find out more

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

Data Provider

</td>
<td valign="top">

Update your data provider profile.

</td>
<td valign="top">

[Maintaining your Data Provider Profile](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/4d298f8654fe4a6c9b6a4399a9e14c77.html "Provide information as you would like to present it to consumers of Data Marketplace. Provide company and business contact information as well as general information about the data you offer.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage the lifecycle of your data products.

</td>
<td valign="top">

[Preparing your Data Products for Listing](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/e5cdfc3cf098402ca5d77b6be262761b.html "Prepare the data products you want to offer to your consumers.") :arrow_upper_right:

[Creating Custom Delta Share Data Products](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/b07e95d07a1e4569b87d9bb57b732bcf.html "Create a custom data product on a Delta Share runtime. This custom data product can then be shared with any system in the formation that supports it, such as SAP Databricks.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Content Aggregator

</td>
<td valign="top">

Update a profile for a data provider that you manage.

</td>
<td valign="top">

[Maintaining your Data Provider Profile](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/4d298f8654fe4a6c9b6a4399a9e14c77.html "Provide information as you would like to present it to consumers of Data Marketplace. Provide company and business contact information as well as general information about the data you offer.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Manage the lifecycle for a data product from one of the data providers you manage.

</td>
<td valign="top">

[Preparing your Data Products for Listing](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/e5cdfc3cf098402ca5d77b6be262761b.html "Prepare the data products you want to offer to your consumers.") :arrow_upper_right:

[Creating Custom Delta Share Data Products](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/b07e95d07a1e4569b87d9bb57b732bcf.html "Create a custom data product on a Delta Share runtime. This custom data product can then be shared with any system in the formation that supports it, such as SAP Databricks.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Data Consumer

</td>
<td valign="top">

Select a data product and evaluate it to see if you can use it or share it.

</td>
<td valign="top">

[Installing Marketplace Data Products](installing-marketplace-data-products-92c35ef.md)

[Sharing Data Products to Target Systems](https://help.sap.com/docs/business-data-cloud/governing-and-publishing-data-in-catalog/sharing-data-products-to-sap-databricks) \(SAP Business Data Cloud help documentation\)

</td>
</tr>
</table>

