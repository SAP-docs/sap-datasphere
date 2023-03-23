<!-- loio54839e83afb54d40a083d03c292ea6e8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Using an Authorization Scenario in a Consumption Model

Choose from your business entities which authorization scenarios to use in a consumption model.



## Context

Consumption models are use-case specific. You can take advantage of the authorization scenarios that you've previously created and assigned to business entities to refine the ways in which users can or cannot access data.



## Procedure

1.  Select a consumption model.

2.  Go to the *General* tab. Under *Authorization Scenario*, next to *Supported Authorization Scenarios*, click <span class="FPA-icons"></span>.

3.  The *Authorization Scenarios* dialog opens. The listed authorizations scenarios come from the business entities used as Fact Source in the consumption model. Select the ones you want to use in your consumption model. Click *Select*.

    You can only select the authorization scenarios that are shared between all Fact Source. If a Fact Source allows Public Data Access, it doesn't need to share an authorization scenario:

    -   Allow Public Data Access: switch it on if this business entity and its data should be accessible for everyone.
    -   Authorization Scenario: if your business entity shouldn't be public, an authorization scenario must be selected to allow consumption.

4.  Click *Save*.




## Results

The authorization scenario is visible in the consumption model's data preview. You can chose to use authorization scenarios or not depending on the use-case you dedicate your consumption model to.

> ### Note:  
> -   If Pulic Data Access is turned on on a consumption model, you are able to to select “without authorization scenario public access” in the Data Preview.
> -   You can define perspectives in a consumption model. To learn more, see [Define Perspectives](define-perspectives-ce26fd3.md).

**Related Information**  


[Creating a Business Entity](creating-a-business-entity-c912cdc.md "You use business entities to build your consumption model for analysis and reporting.")

[Creating an Authorization Scenario](creating-an-authorization-scenario-167c05c.md "Authorization scenarios help you control data access for business entities leveraging data access controls.")

[Assigning an Authorization Scenario](assigning-an-authorization-scenario-2e62354.md "Once you've created an authorization scenario, you can assign it to a business entity to tailor data access to different business contexts.")

