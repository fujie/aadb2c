# ClaimsProviders
## ClaimsProvider
### Parameters
- Domain
- DisplayName
- TechnicalProfiles
    - Id
    - DisplayName
    - Protocol
        - Name
    - OutputTokenFormat
    - Metadata
        - Item
            - Key
    - CryptographicKeys
        - Key
            - Id
            - StorageReferenceId
    - InputClaims
        - InputClaim
            - ClaimTypeReferenceId
            - PartnerClaimType
            - Required
    - PersistedClaims
        - PersistedClaim
            - ClaimTypeReferenceId
            - OverwriteIfExists
            - DefaultValue
    - OutputClaims
        - OutputClaim
            - ClaimTypeReferenceId
            - PartnerClaimType
            - DefaultValue
    - OutputClaimsTransformations
        - OutputClaimsTransformation
            - ReferenceId
    - UseTechnicalProfileForSessionManagement
        - ReferenceId
        
#### Value table for Protocol
| Name | Description | Metadata key | Metadata value |
|:--|:--|:--|:--|
| OAuth2 | OAuth2.0 | ProviderName | Identity Provider Name |
| | | authorization_endpoint | Authorization Endpoint |

