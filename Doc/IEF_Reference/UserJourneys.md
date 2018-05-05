# UserJourneys
## UserJourney
### OrchestrationSteps
#### OrchestrationStep
##### Parameters
- Order
- Type
- ContentDefinitionReferenceId : <a href='https://github.com/fujie/aadb2c/blob/master/Doc/IEF_Reference/BuildingBlocks.md#values-for-contentdefinition-id'>ContentDefinition-Id</a>
- CpimIssuerTechnicalProfileReferenceId
- ClaimsProviderSelections
    - ClaimsProviderSelection
        - TargetClaimsExchangeId
- ClaimsExchanges
    - ClaimsExchange
        - Id
        - TechnicalProfileReferenceId
- Preconditions
    - Precondition
        - Type
        - ExecuteActionsIf
            - Value
            - Action
#### ClientDefinition
##### Parameters
- ReferenceId


### Values for OrchestrationStep Type
| Value | Description |
|:--|:--|
| CombinedSignInAndSignUp | SignIn and SignUp |
| ClaimsExchange | Handle claims |
| SendClaims | Issue Token |
| ClaimsProviderSelection | Select Claims Provider |

