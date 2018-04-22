# BuildingBlocks
In this page, I will explain about BuildingBlocks element in Identity Experience Framework
## ClaimsSchema
In this section, you can define schemas for user objects on Azure AD B2C tenants.
### ClaimType
#### Parameters
- Id
    - DisplayName
    - DataType
    - DefaultPartnerClaimTypes
        - Protocol
            - Name
            - PartnerClaimType
    - UserHelpText
    - UserInputType
    - Restriction
        - Pattern
            - RegularExpression
            - HelpText
#### Values for each parameters
| Parameter | Value | Description |
|:------------|:------------|:------------|
| DataType | string | claim value is string type |
| | stringCollection | claim value is string collection. Currently only for otherMails |
| | boolean | claim value is boolean |


[Note]  
If you want to use extend claim, you have to use *extension_* prefix for Claim Id. e.g. extension_birthDay.

#### Localization


## ClaimsTransformations
In this section, you can define claim trasfomation rules.
### ClaimsTransformation
#### Parameters
- Id
- TransformationMethod
    - InputClaims
        - InputClaim
            - ClaimTypeReferenceId
            - TransformationClaimType
    - OutputClaims
        - OutputClaim
            - ClaimTypeReferenceId
            - TransformationClaimType
            
