---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/set-adfsrelyingpartytrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsRelyingPartyTrust
---

# Set-AdfsRelyingPartyTrust

## SYNOPSIS
Sets the properties of a relying party trust.

## SYNTAX

### Identifier
```
Set-AdfsRelyingPartyTrust [-AllowedAuthenticationClassReferences <String[]>] [-Name <String>]
 [-NotBeforeSkew <Int32>] [-EnableJWT <Boolean>] [-Identifier <String[]>]
 [-EncryptionCertificate <X509Certificate2>] [-EncryptionCertificateRevocationCheck <String>]
 [-EncryptClaims <Boolean>] [-MetadataUrl <Uri>] [-IssuanceAuthorizationRules <String>]
 [-IssuanceAuthorizationRulesFile <String>] [-DelegationAuthorizationRules <String>]
 [-DelegationAuthorizationRulesFile <String>] [-ImpersonationAuthorizationRules <String>]
 [-ImpersonationAuthorizationRulesFile <String>] [-IssuanceTransformRules <String>]
 [-IssuanceTransformRulesFile <String>] [-AdditionalAuthenticationRules <String>]
 [-AdditionalAuthenticationRulesFile <String>] [-AccessControlPolicyName <String>]
 [-AccessControlPolicyParameters <Object>] [-AutoUpdateEnabled <Boolean>] [-WSFedEndpoint <Uri>]
 [-AdditionalWSFedEndpoint <String[]>] [-ClaimsProviderName <String[]>] [-MonitoringEnabled <Boolean>]
 [-Notes <String>] [-ClaimAccepted <ClaimDescription[]>] [-SamlEndpoint <SamlEndpoint[]>]
 [-ProtocolProfile <String>] [-RequestSigningCertificate <X509Certificate2[]>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>] [-SamlResponseSignature <String>]
 [-SignatureAlgorithm <String>] [-SigningCertificateRevocationCheck <String>] [-TokenLifetime <Int32>]
 [-AlwaysRequireAuthentication <Boolean>] [-AllowedClientTypes <AllowedClientTypes>]
 [-IssueOAuthRefreshTokensTo <RefreshTokenIssuanceDeviceTypes>] [-RefreshTokenProtectionEnabled <Boolean>]
 [-RequestMFAFromClaimsProviders <Boolean>] -TargetIdentifier <String> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### IdentifierObject
```
Set-AdfsRelyingPartyTrust [-AllowedAuthenticationClassReferences <String[]>] [-Name <String>]
 [-NotBeforeSkew <Int32>] [-EnableJWT <Boolean>] [-Identifier <String[]>]
 [-EncryptionCertificate <X509Certificate2>] [-EncryptionCertificateRevocationCheck <String>]
 [-EncryptClaims <Boolean>] [-MetadataUrl <Uri>] [-IssuanceAuthorizationRules <String>]
 [-IssuanceAuthorizationRulesFile <String>] [-DelegationAuthorizationRules <String>]
 [-DelegationAuthorizationRulesFile <String>] [-ImpersonationAuthorizationRules <String>]
 [-ImpersonationAuthorizationRulesFile <String>] [-IssuanceTransformRules <String>]
 [-IssuanceTransformRulesFile <String>] [-AdditionalAuthenticationRules <String>]
 [-AdditionalAuthenticationRulesFile <String>] [-AccessControlPolicyName <String>]
 [-AccessControlPolicyParameters <Object>] [-AutoUpdateEnabled <Boolean>] [-WSFedEndpoint <Uri>]
 [-AdditionalWSFedEndpoint <String[]>] [-ClaimsProviderName <String[]>] [-MonitoringEnabled <Boolean>]
 [-Notes <String>] [-ClaimAccepted <ClaimDescription[]>] [-SamlEndpoint <SamlEndpoint[]>]
 [-ProtocolProfile <String>] [-RequestSigningCertificate <X509Certificate2[]>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>] [-SamlResponseSignature <String>]
 [-SignatureAlgorithm <String>] [-SigningCertificateRevocationCheck <String>] [-TokenLifetime <Int32>]
 [-AlwaysRequireAuthentication <Boolean>] [-AllowedClientTypes <AllowedClientTypes>]
 [-IssueOAuthRefreshTokensTo <RefreshTokenIssuanceDeviceTypes>] [-RefreshTokenProtectionEnabled <Boolean>]
 [-RequestMFAFromClaimsProviders <Boolean>] -TargetRelyingParty <RelyingPartyTrust> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### IdentifierName
```
Set-AdfsRelyingPartyTrust [-AllowedAuthenticationClassReferences <String[]>] [-Name <String>]
 [-NotBeforeSkew <Int32>] [-EnableJWT <Boolean>] [-Identifier <String[]>]
 [-EncryptionCertificate <X509Certificate2>] [-EncryptionCertificateRevocationCheck <String>]
 [-EncryptClaims <Boolean>] [-MetadataUrl <Uri>] [-IssuanceAuthorizationRules <String>]
 [-IssuanceAuthorizationRulesFile <String>] [-DelegationAuthorizationRules <String>]
 [-DelegationAuthorizationRulesFile <String>] [-ImpersonationAuthorizationRules <String>]
 [-ImpersonationAuthorizationRulesFile <String>] [-IssuanceTransformRules <String>]
 [-IssuanceTransformRulesFile <String>] [-AdditionalAuthenticationRules <String>]
 [-AdditionalAuthenticationRulesFile <String>] [-AccessControlPolicyName <String>]
 [-AccessControlPolicyParameters <Object>] [-AutoUpdateEnabled <Boolean>] [-WSFedEndpoint <Uri>]
 [-AdditionalWSFedEndpoint <String[]>] [-ClaimsProviderName <String[]>] [-MonitoringEnabled <Boolean>]
 [-Notes <String>] [-ClaimAccepted <ClaimDescription[]>] [-SamlEndpoint <SamlEndpoint[]>]
 [-ProtocolProfile <String>] [-RequestSigningCertificate <X509Certificate2[]>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>] [-SamlResponseSignature <String>]
 [-SignatureAlgorithm <String>] [-SigningCertificateRevocationCheck <String>] [-TokenLifetime <Int32>]
 [-AlwaysRequireAuthentication <Boolean>] [-AllowedClientTypes <AllowedClientTypes>]
 [-IssueOAuthRefreshTokensTo <RefreshTokenIssuanceDeviceTypes>] [-RefreshTokenProtectionEnabled <Boolean>]
 [-RequestMFAFromClaimsProviders <Boolean>] -TargetName <String> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AdfsRelyingPartyTrust** cmdlet configures the trust relationship with a specified relying party object.

## EXAMPLES

### Example 1: Set the name and identifier for a relying party trust
```
PS C:\> Set-AdfsRelyingPartyTrust -TargetName "FabrikamApp" -Identifier "https://FabrikamApp.CentralServerNew.org"
```

This command sets the name and identifier for the specified relying party trust.

### Example 2: Set the target identifier for a relying party trust
```
PS C:\> Set-AdfsRelyingPartyTrust -TargetIdentifier "https://FabrikamApp.CentralServer.org" -Identifier "https://FabrikamApp.CentralServerNew.org"
```

This command sets the target identifier for the specified relying party trust.

### Example 3: Assign a policy that uses parameters
```
PS C:\> Set-AdfsRelyingPartyTrust -TargetName "DemoRP1" -AccessControlPolicyParameters ("Administrators","Users") -AccessControlPolicyName "DemoOne"
```

This command assigns a policy that uses parameters.

For more information about access control policy parameters, see [Active Directory Federation Services](https://technet.microsoft.com/windows-server-docs/identity/active-directory-federation-services) (https://technet.microsoft.com/windows-server-docs/identity/active-directory-federation-services) on TechNet.

### Example 4: Un-assign a policy template
```
PS C:\> Set-AdfsRelyingPartyTrust -TargetName "DemoRP1" -AccessControlPolicyName $null
```

This command un-assigns a policy template.

## PARAMETERS

### -AccessControlPolicyName
Specifies the name of an access control policy.

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

### -AccessControlPolicyParameters
```yaml
Type: Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AdditionalAuthenticationRules
Specifies the additional authorization rules to require additional authentication based on user, device and location attributes after the completion of the first step of authentication.
Note: These rules must only be configured after there is at least one authentication provider enabled for additional authentication.

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

### -AdditionalAuthenticationRulesFile
Specifies a file that contains the additional authentication rules to require additional authentication when a user is attempting to access this relying party.

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

### -AdditionalWSFedEndpoint
Specifies an array of alternate return addresses for the application.
This is typically used when the application wants to indicate to AD FS what the return URL should be on successful token generation.
AD FS requires that all acceptable URLs are entered as trusted information by the administrator.

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

### -AllowedAuthenticationClassReferences
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

### -AllowedClientTypes
Specifies allowed client types.
The acceptable values for this parameter are:

- None
- Public
- Confidential

```yaml
Type: AllowedClientTypes
Parameter Sets: (All)
Aliases:
Accepted values: None, Public, Confidential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AlwaysRequireAuthentication
Indicates to always require authentication.

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

### -ClaimAccepted
Specifies an array of claims that this relying party accepts.

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

### -ClaimsProviderName
Specifies an array of claims provider names.

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

### -DelegationAuthorizationRules
Specifies the delegation authorization rules for issuing claims to this relying party.

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

### -DelegationAuthorizationRulesFile
Specifies a file that contains the delegation authorization rules for issuing claims to this relying party.

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

### -EnableJWT
Indicates whether the JSON Web Token (JWT) format should be used to issue a token on a WS-Federation request.
By default, SAML tokens are issued over WS-Federation.

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

### -EncryptClaims
Indicates whether the claims that are sent to the relying party should be encrypted.

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

### -EncryptedNameIdRequired
Indicates whether the relying party requires that the **NameID** claim be encrypted.

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
Specifies the certificate to be used for encrypting claims that are issued to this relying party.
Encrypting claims is optional.

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
Specifies the type of validation that occurs for the encryption certificate before it is used for encrypting claims to the relying party.
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

### -Identifier
Specifies an array of unique identifiers for this relying party trust.
No other trust can use an identifier from this list.
Uniform Resource Identifiers (URIs) are often used as unique identifiers for a relying party trust, but you can use any string of characters.

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

### -ImpersonationAuthorizationRules
Specifies the impersonation authorization rules for issuing claims to this relying party.

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

### -ImpersonationAuthorizationRulesFile
Specifies a file that contains the impersonation authorization rules for issuing claims to this relying party.

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

### -IssuanceAuthorizationRules
Specifies the issuance authorization rules for issuing claims to this relying party.

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

### -IssuanceAuthorizationRulesFile
Specifies a file that contains the issuance authorization rules for issuing claims to this relying party.

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

### -IssuanceTransformRules
Specifies the issuance transform rules for issuing claims to this relying party.

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

### -IssuanceTransformRulesFile
Specifies a file that contains the issuance transform rules for issuing claims to this relying party.

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

### -IssueOAuthRefreshTokensTo
Specifies the refresh token issuance device types.
The acceptable values for this parameter are:

- NoDevice
- WorkplaceJoinedDevices
- AllDevices

```yaml
Type: RefreshTokenIssuanceDeviceTypes
Parameter Sets: (All)
Aliases:
Accepted values: NoDevice, WorkplaceJoinedDevices, AllDevices

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MetadataUrl
Specifies a URL at which the federation metadata for this relying party trust is available.

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
Indicates whether periodic monitoring of this relying party federation metadata is enabled.
The *MetadataUrl* parameter specifies the URL of the relying party's federation metadata.

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
Specifies the friendly name of this relying party trust.

Note: You can use the *Name* parameter as an identifier for the object.

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

### -NotBeforeSkew
Specifies the skew, as in integer, for the time stamp that marks the beginning of the validity period.
The higher this number is, the further back in time the validity period begins with respect to the time that the claims are issued for the relying party.
By default, this value is 0.
Specify a positive value if validation fails on the relying party because the validity period has not yet begun.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notes
Specifies notes for this relying party trust.

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

### -ProtocolProfile
Specifies which protocol profiles the relying party supports.
The acceptable values for this parameter are: SAML and WsFederation.
By default, this parameter is blank, which indicates that both protocols are supported.

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

### -RefreshTokenProtectionEnabled
Indicates that refresh token protection is enabled.

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

### -RequestMFAFromClaimsProviders
Indicates whether to use the request MFA from claims providers option.

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

### -RequestSigningCertificate
Specifies an array of certificate that is used to verify the signature on a request from the relying party.

```yaml
Type: X509Certificate2[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SamlEndpoint
Specifies an array of Security Assertion Markup Language (SAML) protocol endpoints for this relying party.

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

### -SamlResponseSignature
Specifies the response signatures that the relying party expects.
The acceptable values for this parameter are:

- AssertionOnly
- MessageAndAssertion
- MessageOnly

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: AssertionOnly, MessageAndAssertion, MessageOnly

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignatureAlgorithm
Specifies the signature algorithm that the relying party uses for signing and verification.
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
Specifies the type of certificate validation that should occur when signatures on requests from the relying party are verified.
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

### -TargetIdentifier
Specifies the identifier of the relying party trust that is modified by the cmdlet.

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
Specifies the friendly name of the relying party trust that is modified by the cmdlet.

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

### -TargetRelyingParty
Specifies a **RelyingPartyTrust** object.
The cmdlet modifies the relying party trust that you specify.
To obtain a **RelyingPartyTrust** object, use the **Get-AdfsRelyingPartyTrust** cmdlet.

```yaml
Type: RelyingPartyTrust
Parameter Sets: IdentifierObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TokenLifetime
Specifies the duration, in minutes, for which the claims that are issued to the relying party are valid. The default TokenLifetime is 60 minutes.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WSFedEndpoint
Specifies the WS-Federation Passive URL for this relying party.

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

### System.String

String objects are received by the *AccessControlPolicyName*, *AdditionalAuthenticationRules*, *DelegationAuthorizationRules*, *ImpersonationAuthorizationRules*, *IssuanceAuthorizationRules*, *IssuanceTransformRules*, *TargetIdentifier*, and *TargetName* parameters.

### System.Object

Objects are received by the *AccessControlPolicyParameters* parameter.

### System.Management.Automation.SwitchParameter

SwitchParameter objects are received by the *AlwaysRequireAuthentication* and *RequestMFAFromClaimsProviders* parameters.

### Microsoft.IdentityServer.PowerShell.Resources.ClaimDescription

ClaimDescription Objects are received by the *ClaimAccepted* parameter.

### System.Security.Cryptography.X509Certificates.X509Certificate2

X509Certificate2 objects are received by the *RequestSigningCertificate* parameter.

### Microsoft.IdentityServer.PowerShell.Resources.SamlEndpoint

SamlEndpoint objects are received by the *SamlEndpoint* parameter.

### Microsoft.IdentityServer.PowerShell.Resources.RelyingPartyTrust

RelyingPartyTrust objects are received by the *TargetRelyingParty* parameter.

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.RelyingPartyTrust

Returns the updated RelyingPartyTrust object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES
* A relying party in Active Directory Federation Services (AD FS) is an organization in which Web servers that host one or more Web-based applications reside. Tokens and Information Cards that originate from a claims provider can then be presented and ultimately accessed by the Web-based resources that are located in the relying party organization. When AD FS is configured in the role of the relying party, it acts as a partner that trusts a claims provider to authenticate users. Therefore, the relying party accesses the claims that are packaged in security tokens that come from users in the claims provider. In other words, a relying party is the organization whose Web servers are protected by the resource-side federation server. The federation server in the relying party uses the security tokens that the claims provider produces to issue tokens to the Web servers that are located in the relying party.

## RELATED LINKS

[Add-AdfsRelyingPartyTrust](./Add-AdfsRelyingPartyTrust.md)

[Disable-AdfsRelyingPartyTrust](./Disable-AdfsRelyingPartyTrust.md)

[Enable-AdfsRelyingPartyTrust](./Enable-AdfsRelyingPartyTrust.md)

[Get-AdfsRelyingPartyTrust](./Get-AdfsRelyingPartyTrust.md)

[Remove-AdfsRelyingPartyTrust](./Remove-AdfsRelyingPartyTrust.md)

[Update-AdfsRelyingPartyTrust](./Update-AdfsRelyingPartyTrust.md)

