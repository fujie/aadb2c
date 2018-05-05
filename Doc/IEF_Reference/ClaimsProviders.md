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
        - Handler
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
    - ValidationTechnicalProfiles
        - ValidationTechnicalProfile
            - ReferenceId
    - IncludeInSso
    - UseTechnicalProfileForSessionManagement
        - ReferenceId
        
#### Values for Protocol/Metadata
| Name | Description | Metadata key | Metadata value |
|:--|:--|:--|:--|
| OAuth2 | OAuth2.0 | ProviderName | Identity Provider Name |
| | | authorization_endpoint | Authorization Endpoint |
| | | AccessTokenEndpoint | Token Endpoint|
| | | ClaimsEndpoint | Profile Endpoint |
| | | client_id | client id |
| | | HttpBinding | Binding method for xxx endpoint |
| | | UsePolicyInRedirectUri | |
| OpenIdConnect | OpenID Connect | METADATA | discovery(well-known) endpoint uri |
| | | ProviderName | Identity Provider Name |
| | | authorization_endpoint | Authorization Endpoint |
| | | client_id | client id |
| | | IdTokenAudience | aud |
| | | response_types | response type |
| | | scope | scope |
| | | UsePolicyInRedirectUri | |
| Proprietary | REST API(for AAD/Self Asserted/Session Management) | ApplicationObjectId | Application Object Id |
| | | ClientId | client id |
| | | ContentDefinitionReferenceId | |
| | | AlwaysFetchClaimsFromProvider | |
| None | None(for Trustframework Policy Engine/Token Issuer) | url | |
| | | issuer_refresh_token_user_identity_claim_type | |
| | | SendTokenResponseBodyWithJsonNumbers | |
| | | IssuerUri | SAML Token Issuer Uri |
| | | TokenLifeTimeInSeconds | SAML Token lifetime |

#### Technical profile values for Azure AD REST API
| Id | Description | Operation | InputClaimsTransformations | InputClaims | PersistedClaims | OutputClaims | Inherited |
|:--|:--|:--|:--|:--|:--|:--|:--|
| AAD-UserWriteUsingAlternativeSecurityId | Write user by Alternative Security Id | Write | CreateOtherMailsFromEmail | [Required]<br>AlternativeSecurityId | alternativeSecurityId<br>userPrincipalName<br>mailNickName<br>displayName | objectId<br>newUser | AAD-Common |
| AAD-UserReadUsingAlternativeSecurityId | Read user from Azure AD with Alternative Security Id | Read | | [Required]<br>AlternativeSecurityId | | objectId | AAD-Common |
| AAD-UserReadUsingAlternativeSecurityId-NoError | Read user from Azure AD with Alternative Security Id | | | | | | AAD-UserReadUsingAlternativeSecurityId |
| AAD-UserWriteProfileUsingObjectId | Update user profile with object Id | Write | | [Required]<br>objectId | objectId | | AAD-Common |
| AAD-UserReadUsingObjectId| Read user from Azure AD with object Id | Read | | [Required]<br>objectId | | | AAD-Common |
