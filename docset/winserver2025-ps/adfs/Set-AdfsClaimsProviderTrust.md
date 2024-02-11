---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsclaimsprovidertrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsClaimsProviderTrust
---

# Set-AdfsClaimsProviderTrust

## SYNOPSIS
Sets the properties of a claims provider trust.

## SYNTAX

### IdentifierObject
```
Set-AdfsClaimsProviderTrust [-Name <String>] [-Identifier <String>] [-SignatureAlgorithm <String>]
 [-TokenSigningCertificate <X509Certificate2[]>] [-MetadataUrl <Uri>] [-AcceptanceTransformRules <String>]
 [-AcceptanceTransformRulesFile <String>] [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>]
 [-CustomMFAUri <Uri>] [-SupportsMFA <Boolean>] [-WSFedEndpoint <Uri>]
 [-EncryptionCertificate <X509Certificate2>] [-EncryptionCertificateRevocationCheck <String>]
 [-MonitoringEnabled <Boolean>] [-Notes <String>] [-OrganizationalAccountSuffix <String[]>]
 [-LookupForests <String[]>] [-AlternateLoginID <String>] [-Force] [-ClaimOffered <ClaimDescription[]>]
 [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>] [-RequiredNameIdFormat <Uri>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlAuthenticationRequestIndex <UInt16>] [-SamlAuthenticationRequestParameters <String>]
 [-SamlAuthenticationRequestProtocolBinding <String>] [-SigningCertificateRevocationCheck <String>]
 [-PromptLoginFederation <PromptLoginFederation>] [-PromptLoginFallbackAuthenticationType <String>]
 [-AnchorClaimType <String>] -TargetClaimsProviderTrust <ClaimsProviderTrust> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### TokenSigningCertificates
```
Set-AdfsClaimsProviderTrust [-Name <String>] [-Identifier <String>] [-SignatureAlgorithm <String>]
 [-TokenSigningCertificate <X509Certificate2[]>] [-MetadataUrl <Uri>] [-AcceptanceTransformRules <String>]
 [-AcceptanceTransformRulesFile <String>] [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>]
 [-CustomMFAUri <Uri>] [-SupportsMFA <Boolean>] [-WSFedEndpoint <Uri>]
 [-EncryptionCertificate <X509Certificate2>] [-EncryptionCertificateRevocationCheck <String>]
 [-MonitoringEnabled <Boolean>] [-Notes <String>] [-OrganizationalAccountSuffix <String[]>]
 [-LookupForests <String[]>] [-AlternateLoginID <String>] [-Force] [-ClaimOffered <ClaimDescription[]>]
 [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>] [-RequiredNameIdFormat <Uri>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlAuthenticationRequestIndex <UInt16>] [-SamlAuthenticationRequestParameters <String>]
 [-SamlAuthenticationRequestProtocolBinding <String>] [-SigningCertificateRevocationCheck <String>]
 [-PromptLoginFederation <PromptLoginFederation>] [-PromptLoginFallbackAuthenticationType <String>]
 [-AnchorClaimType <String>] -TargetCertificate <X509Certificate2> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Identifier
```
Set-AdfsClaimsProviderTrust [-Name <String>] [-Identifier <String>] [-SignatureAlgorithm <String>]
 [-TokenSigningCertificate <X509Certificate2[]>] [-MetadataUrl <Uri>] [-AcceptanceTransformRules <String>]
 [-AcceptanceTransformRulesFile <String>] [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>]
 [-CustomMFAUri <Uri>] [-SupportsMFA <Boolean>] [-WSFedEndpoint <Uri>]
 [-EncryptionCertificate <X509Certificate2>] [-EncryptionCertificateRevocationCheck <String>]
 [-MonitoringEnabled <Boolean>] [-Notes <String>] [-OrganizationalAccountSuffix <String[]>]
 [-LookupForests <String[]>] [-AlternateLoginID <String>] [-Force] [-ClaimOffered <ClaimDescription[]>]
 [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>] [-RequiredNameIdFormat <Uri>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlAuthenticationRequestIndex <UInt16>] [-SamlAuthenticationRequestParameters <String>]
 [-SamlAuthenticationRequestProtocolBinding <String>] [-SigningCertificateRevocationCheck <String>]
 [-PromptLoginFederation <PromptLoginFederation>] [-PromptLoginFallbackAuthenticationType <String>]
 [-AnchorClaimType <String>] -TargetIdentifier <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierName
```
Set-AdfsClaimsProviderTrust [-Name <String>] [-Identifier <String>] [-SignatureAlgorithm <String>]
 [-TokenSigningCertificate <X509Certificate2[]>] [-MetadataUrl <Uri>] [-AcceptanceTransformRules <String>]
 [-AcceptanceTransformRulesFile <String>] [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>]
 [-CustomMFAUri <Uri>] [-SupportsMFA <Boolean>] [-WSFedEndpoint <Uri>]
 [-EncryptionCertificate <X509Certificate2>] [-EncryptionCertificateRevocationCheck <String>]
 [-MonitoringEnabled <Boolean>] [-Notes <String>] [-OrganizationalAccountSuffix <String[]>]
 [-LookupForests <String[]>] [-AlternateLoginID <String>] [-Force] [-ClaimOffered <ClaimDescription[]>]
 [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>] [-RequiredNameIdFormat <Uri>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlAuthenticationRequestIndex <UInt16>] [-SamlAuthenticationRequestParameters <String>]
 [-SamlAuthenticationRequestProtocolBinding <String>] [-SigningCertificateRevocationCheck <String>]
 [-PromptLoginFederation <PromptLoginFederation>] [-PromptLoginFallbackAuthenticationType <String>]
 [-AnchorClaimType <String>] -TargetName <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsClaimsProviderTrust** cmdlet configures the trust relationship with a claims provider.

## EXAMPLES

### Example 1: Enable auto-update for a claims provider trust
```
PS C:\> Set-ADFSClaimsProviderTrust -TargetName "Fabrikam claims provider" -AutoUpdateEnabled $False
```

This command enables auto-update for the claims provider trust named Fabrikam claims provider.

## PARAMETERS

### -AcceptanceTransformRules
Specifies the claim acceptance transform rules for accepting claims from this claims provider.
These rules determine the information that is accepted from the partner represented by the claims provider trust.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AcceptanceTransformRulesFile
Specifies a file that contains the claim acceptance transform rules for accepting claims from this claims provider.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowCreate
Indicates whether the Security Assertion Markup Language (SAML) parameter *AllowCreate* is sent in SAML requests to the claims provider.
The default value is True.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AlternateLoginID
Specifies the LDAP name of the attribute that you want to use for login.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AnchorClaimType
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoUpdateEnabled
Indicates whether changes to the federation metadata by the *MetadataURL* parameter apply automatically to the configuration of the trust relationship.
If this parameter has a value of $True, partner claims, certificates, and endpoints are updated automatically.

Note: When auto-update is enabled, fields that can be overwritten by metadata become read only.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClaimOffered
Specifies an array of claims that are offered by this claims provider.

```yaml
Type: ClaimDescription[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CustomMFAUri
```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptedNameIdRequired
Indicates whether the relying party requires that the **NameID** claim be encrypted.
This setting applies to SAML logout requests.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionCertificate
Specifies the certificate to be used for encrypting a **NameID** to this claims provider in SAML logout requests.
Encrypting the **NameID** is optional.

```yaml
Type: X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionCertificateRevocationCheck
Specifies the type of validation that occurs for the encryption certificate before it is used for encrypting claims.
The acceptable values for this parameter are:

- None
- CheckEndCert
- CheckEndCertCacheOnly
- CheckChain
- CheckChainCacheOnly
- CheckChainExcludeRoot
- CheckChainExcludeRootCacheOnly

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: CheckChain, CheckChainCacheOnly, CheckChainExcludeRoot, CheckChainExcludeRootCacheOnly, CheckEndCert, CheckEndCertCacheOnly, None

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identifier
Specifies the unique identifier for this claims provider trust.
No other trust can use an identifier from this list.
Uniform Resource Identifiers (URIs) are often used as unique identifiers for a claims provider trust, but you can use any string of characters.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LookupForests
Specifies the forest DNS names that can be used to look up the **AlternateLoginID**.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MetadataUrl
Specifies the URL at which the federation metadata for this claims provider trust is available.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitoringEnabled
Indicates whether periodic monitoring of this claims provider's federation metadata is enabled.
The URL of the claims provider's federation metadata is specified by the *MetadataUrl* parameter.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the friendly name of this claims provider trust.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notes
Specifies notes for this claims provider trust.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrganizationalAccountSuffix
Specifies a list of organizational account suffixes that an administrator can configure for the claims provider trust for Home Realm Discovery (HRD) scenarios.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PromptLoginFallbackAuthenticationType
```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PromptLoginFederation
The acceptable values for this parameter are:

- None.
Do not federate prompt=login request and error instead.
- FallbackToProtocolSpecificParameters.
Translate prompt=login to wfresh=0 and Wauth=forms during federation.
If wauth is present in the original request, it will be preserved.
- ForwardPromptAndHintsOverWsFederation.
Forward prompt, login_hint, and domain_hint parameters during federation.

```yaml
Type: PromptLoginFederation
Parameter Sets: (All)
Aliases:
Accepted values: None, FallbackToProtocolSpecificParameters, ForwardPromptAndHintsOverWsFederation, Disabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtocolProfile
Specifies which protocol profiles the claims provider supports.
The acceptable values for this parameter are:

- SAML
- WsFederation
- WsFed-SAML

By default, both SAML and WS-Federation protocols are supported.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: WsFed-SAML, WSFederation, SAML

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredNameIdFormat
Specifies the format that is required for **NameID** claims to be included in SAML requests to the claims provider.
By default, no format is required.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SamlAuthenticationRequestIndex
Specifies the value of **AssertionConsumerServiceIndex** that is placed in SAML authentication requests that are sent to the claims provider.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SamlAuthenticationRequestParameters
Specifies which of the following parameters to use in SAML authentication requests to the claims provider: **AssertionConsumerServiceIndex**, **AssertionConsumerServiceUrl**, and **ProtocolBinding**.
The acceptable values for this parameter are:

- None
- Index
- Url
- ProtocolBinding
- UrlWithProtocolBinding

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Index, None, , ProtocolBinding, Url, UrlWithProtocolBinding

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SamlAuthenticationRequestProtocolBinding
Specifies the value of **ProtocolBinding** to place in SAML authentication requests to the claims provider.
The acceptable values for this parameter are:

- Artifact
- POST
- Redirect

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Artifact, , POST, Redirect

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SamlEndpoint
Specifies an array of SAML protocol endpoints for this claims provider.

```yaml
Type: SamlEndpoint[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SignatureAlgorithm
Specifies the signature algorithm that the claims provider uses for signing and verification.
The acceptable values for this parameter are:

- https://www.w3.org/2000/09/xmldsig#rsa-sha1
- https://www.w3.org/2001/04/xmldsig-more#rsa-sha256

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: https://www.w3.org/2000/09/xmldsig#rsa-sha1, https://www.w3.org/2001/04/xmldsig-more#rsa-sha256

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignedSamlRequestsRequired
Indicates whether the Federation Service requires signed SAML protocol requests from the relying party.
If you specify a value of $True, the Federation Service rejects unsigned SAML protocol requests.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SigningCertificateRevocationCheck
Specifies the type of certificate validation that occurs when signatures are verified on responses or assertions from the claims provider.
The acceptable values for this parameter are:

- None
- CheckEndCert
- CheckEndCertCacheOnly
- CheckChain
- CheckChainCacheOnly
- CheckChainExcludeRoot
- CheckChainExcludeRootCacheOnly

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: CheckChain, CheckChainCacheOnly, CheckChainExcludeRoot, CheckChainExcludeRootCacheOnly, CheckEndCert, CheckEndCertCacheOnly, None

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SupportsMFA
```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetCertificate
Specifies the certificate of the claims provider trust that is modified by the cmdlet.

```yaml
Type: X509Certificate2
Parameter Sets: TokenSigningCertificates
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetClaimsProviderTrust
Specifies a **ClaimsProviderTrust** object.
The cmdlet modifies the claims provider trust that you specify.
To obtain a **ClaimsProviderTrust** object, use the **Get-AdfsClaimsProviderTrust** cmdlet.

```yaml
Type: ClaimsProviderTrust
Parameter Sets: IdentifierObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetIdentifier
Specifies the identifier of the claims provider trust that is modified by the cmdlet.

```yaml
Type: String
Parameter Sets: Identifier
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetName
Specifies the friendly name of the claims provider trust that is modified by the cmdlet.

```yaml
Type: String
Parameter Sets: IdentifierName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TokenSigningCertificate
Specifies an array of token-signing certificates that the claims provider use.

```yaml
Type: X509Certificate2[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WSFedEndpoint
Specifies the WS-Federation Passive URL for this claims provider.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimDescription

ClaimDescription objects are received by the *ClaimOffered* parameter.

### System.Security.Cryptography.X509Certificates.X509Certificate.X509Certificate2

X509Certificate2 objects are received by the *TargetCertificate* parameter.

### Microsoft.IdentityServer.PowerShell.Resources.ClaimsProviderTrust

ClaimsProviderTrust objects are received by the *TargetClaimsProviderTrust* parameter.

### System.String

String objects are received by the *AcceptanceTransformRules*, *SamlEndpoint*, *TargetIdentifier*, and *TargetName* parameters.

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimsProviderTrust

Returns the changed ClaimsProviderTrust object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES
* The claims provider collects and authenticates a user's credentials, builds up claims for that user, and packages the claims into security tokens or Information Cards. In other words, a claims provider represents the organization for whose users the claims provider issues security tokens or Information Cards on their behalf. When you configure Active Directory Federation Services (AD FS), the role of the claims provider is to enable its users to access resources that are hosted in a relying party organization by establishing one side of a federation trust relationship. After the trust is established, tokens and Information Cards can be presented to a relying party across the federation trust.

## RELATED LINKS

[Add-AdfsClaimsProviderTrust](./Add-AdfsClaimsProviderTrust.md)

[Disable-AdfsClaimsProviderTrust](./Disable-AdfsClaimsProviderTrust.md)

[Enable-AdfsClaimsProviderTrust](./Enable-AdfsClaimsProviderTrust.md)

[Get-AdfsClaimsProviderTrust](./Get-AdfsClaimsProviderTrust.md)

[Remove-AdfsClaimsProviderTrust](./Remove-AdfsClaimsProviderTrust.md)

[Update-AdfsClaimsProviderTrust](./Update-AdfsClaimsProviderTrust.md)

