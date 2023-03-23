<!-- loio5f0ea0dbf75e4020b6ef2d5e5498037d -->

# Objects in the Business Builder

This is an overview of all the available objects in the Business Builder.



<a name="loio5f0ea0dbf75e4020b6ef2d5e5498037d__section_tzg_35m_pnb"/>

## Business Entities

Business entities can define measures or attributes. Measures are quantifiable values that refer to an aggregable field of the underlying model. An attribute is a descriptive element of a business entity and provides meaningful business insights into measures. The underlying model is a view or a table, which has been created in the Data Builder.

Business entities can be modeled as a dimension or as an analytical dataset. The definition doesn't really differ but rather the intended usage within the consumption model.

**Dimensions** are generally used to contain master data, such as product, customer, or time. The more dimensions you define for your model, the more flexible your analysis will be later on. They must have a key defined.

**Analytical datasets** are generally used to contain transactional data \(facts\) and must have at least one measure defined.

Associations are needed to connect your fact data to your dimensions.



<a name="loio5f0ea0dbf75e4020b6ef2d5e5498037d__section_xjx_25m_pnb"/>

## Fact Models

Fact models let you predefine an array of measures, attributes, and filters that are relevant to a specific business context. Fact models can then be reused in several use cases within that business context.



<a name="loio5f0ea0dbf75e4020b6ef2d5e5498037d__section_pgv_35m_pnb"/>

## Consumption Models

Consumption models are the basis to consume your data. You build your consumption models on top of business entities or on top of fact models, which have some elements of the consumption model already predefined.



<a name="loio5f0ea0dbf75e4020b6ef2d5e5498037d__section_ykk_s5m_pnb"/>

## Perspectives

Perspectives are reusable configurations that contain a subset of a consumption models attributes, measures and parameters. They are used for reporting and are defined within the consumption model editor.

