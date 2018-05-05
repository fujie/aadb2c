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
    - InputParameter
        - Id
        - DataType
        - Value
    - InputClaims
        - InputClaim
            - ClaimTypeReferenceId
            - TransformationClaimType
    - OutputClaims
        - OutputClaim
            - ClaimTypeReferenceId
            - TransformationClaimType
            
| TransformationMethod | Description | InputParameter | InputClaims | OutputClaims |
|:------------|:------------|:------------|:------------|:------------|
| AddItemToStringCollection | Add the provided string claim to a that contains collection of strings item (String) collection (StringCollection) | | item to add<br>target collection | result collection |
| AddParameterToStringCollection | Add the provided string parameter to a claim that contains collection of strings collection | | | |
| AssertStringClaimsAreEqual | Compare two claims, and throws an exception if they are not equal according to the specified comparison inputClaim1 (String) stringComparison [ordinal, ordinalIgnoreCase] | | | |
| ChangeCase | Change the case of the provided string claim to the one specified inputClaim1 (String) toCase [lower, upper] outputClaim (String) | | | |
| CompareClaimToValue | Compare claim to the provided parameter, and returns a claim with true indicating that the values match, false otherwise inputClaim1 (String) operator [equal, not equal] outputClaim (Boolean) | | | |
| CompareClaims | Compares two claims and returns a claim with true indicating that the claims match, false otherwise inputClaim1 (String) operator [equal, not equal] outputClaim (Boolean) | | | |
| CreateAlternativeSecurityId | Creates a JSON representation of the user’s alternativeSecurityId property that can be used in calls to Graph API. This string is consumed by the Azure AD claims provider when PartnerClaimType is alternativeSecurityId key (String) alternativeSecurityId | | key: socialIdPUserId<br>identityProvider: IdP name | created string |
| CreateStringClaim | Creates a string claim from the provided parameter in the policy value (String) createdClaim (String) | id: value<br>DataType: string<br>Value: not supported | | created string |
| CreateRandomString | Creates a random string using the random number generator used. If the random number generator is of type “integer”, optionally a seed parameter and a maximum number may be provided. An optional string format parameter allows the output to be formatted using it, and an optional base64 parameter specifies whether the output is base64 encoded randomGeneratorType [guid, integer] outputClaim (String) | Id: randomGeneratorType<br>DataType: string<br>Value: string | | created string |
| FormatStringClaim | Format a given claim according to the provided format string. This transformation uses the C# String.Format method. Please see its documentation for more details inputClaim (String) stringFormat (String) outputClaim (String) | Id: stringFormat<br>DataType: string<br>Value: format | inputClaim | formatted string |
| GetClaimFromJson | Given a JSON string of key value pairs, extract the specified claim inputJson (String) claimToExtract (String) extractedClaim (String) | | | |
| GetSingleItemFromStringCollection | Gets the first item from the provided string collection. This transformation should ideally be renamed to GetFirstItemFromStringCollection collection (StringCollection) - optional extractedItem (String) | | | |
| GetSingleValueFromJsonArray | Gets the first item from the provided JSON string. This transformation should ideally be renamed to GetFirstItemFromJsonArray. inputJsonClaim (String) extractedClaim (String) | | | |
| Hash | Hash the provided plain text using the salt and a secret whose identifier is provided as a parameter plaintext (String) randomizerSecret (String) hash (String) | | | |

## ClientDefinitions
### ClientDefinition
#### Parameters
- Id
    - ClientUIFilterFlags

## ContentDefinitions
### ContentDefinition
#### Parameters
- Id
    - LoadUri
    - RecoveryUri
    - DataUri
    - Metadata
        - Item
            - Key
                - DisplayName
                - language.intro

#### Values for ContentDefinition Id
| Value | Description |
|:--|:--|
| api.signuporsignin | Show SignIn and SignUp page |
| api.idpselections | Show Claims Provider selection page |
| api.idpselections.signup | Show Claims Provider selection page |
| api.error | Show error page |
| api.selfasserted | Show self claim assertion page |
| api.selfasserted.profileupdate | Show profile update page |
