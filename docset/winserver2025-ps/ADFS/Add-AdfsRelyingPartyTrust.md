---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfsrelyingpartytrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsRelyingPartyTrust
---

# Add-AdfsRelyingPartyTrust

## SYNOPSIS
Adds a new relying party trust to the Federation Service.

## SYNTAX

### AllProperties
```
Add-AdfsRelyingPartyTrust -Name <String> -Identifier <String[]> [-EncryptClaims <Boolean>] [-Enabled <Boolean>]
 [-EncryptionCertificate <X509Certificate2>] [-AutoUpdateEnabled <Boolean>] [-WSFedEndpoint <Uri>]
 [-AdditionalWSFedEndpoint <String[]>] [-ClaimAccepted <ClaimDescription[]>] [-SamlEndpoint <SamlEndpoint[]>]
 [-RequestSigningCertificate <X509Certificate2[]>] [-EncryptedNameIdRequired <Boolean>]
 [-SignedSamlRequestsRequired <Boolean>] [-Notes <String>] [-SignatureAlgorithm <String>]
 [-SigningCertificateRevocationCheck <String>] [-TokenLifetime <Int32>] [-AlwaysRequireAuthentication]
 [-RequestMFAFromClaimsProviders] [-AllowedAuthenticationClassReferences <String[]>]
 [-EncryptionCertificateRevocationCheck <String>] [-NotBeforeSkew <Int32>] [-ProtocolProfile <String>]
 [-ClaimsProviderName <String[]>] [-EnableJWT <Boolean>] [-SamlResponseSignature <String>]
 [-AllowedClientTypes <AllowedClientTypes>] [-IssueOAuthRefreshTokensTo <RefreshTokenIssuanceDeviceTypes>]
 [-RefreshTokenProtectionEnabled <Boolean>] [-PassThru] [-MonitoringEnabled <Boolean>]
 [-ImpersonationAuthorizationRules <String>] [-ImpersonationAuthorizationRulesFile <String>]
 [-IssuanceTransformRules <String>] [-IssuanceTransformRulesFile <String>]
 [-IssuanceAuthorizationRules <String>] [-IssuanceAuthorizationRulesFile <String>]
 [-DelegationAuthorizationRules <String>] [-DelegationAuthorizationRulesFile <String>]
 [-AdditionalAuthenticationRules <String>] [-AdditionalAuthenticationRulesFile <String>]
 [-AccessControlPolicyName <String>] [-AccessControlPolicyParameters <Object>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### MetadataFile
```
Add-AdfsRelyingPartyTrust -Name <String> -MetadataFile <String> [-EncryptClaims <Boolean>]
 [-Enabled <Boolean>] [-AutoUpdateEnabled <Boolean>] [-EncryptedNameIdRequired <Boolean>]
 [-SignedSamlRequestsRequired <Boolean>] [-Notes <String>] [-SignatureAlgorithm <String>]
 [-SigningCertificateRevocationCheck <String>] [-TokenLifetime <Int32>] [-AlwaysRequireAuthentication]
 [-RequestMFAFromClaimsProviders] [-AllowedAuthenticationClassReferences <String[]>]
 [-EncryptionCertificateRevocationCheck <String>] [-NotBeforeSkew <Int32>] [-ProtocolProfile <String>]
 [-ClaimsProviderName <String[]>] [-EnableJWT <Boolean>] [-SamlResponseSignature <String>]
 [-AllowedClientTypes <AllowedClientTypes>] [-IssueOAuthRefreshTokensTo <RefreshTokenIssuanceDeviceTypes>]
 [-RefreshTokenProtectionEnabled <Boolean>] [-PassThru] [-MonitoringEnabled <Boolean>]
 [-ImpersonationAuthorizationRules <String>] [-ImpersonationAuthorizationRulesFile <String>]
 [-IssuanceTransformRules <String>] [-IssuanceTransformRulesFile <String>]
 [-IssuanceAuthorizationRules <String>] [-IssuanceAuthorizationRulesFile <String>]
 [-DelegationAuthorizationRules <String>] [-DelegationAuthorizationRulesFile <String>]
 [-AdditionalAuthenticationRules <String>] [-AdditionalAuthenticationRulesFile <String>]
 [-AccessControlPolicyName <String>] [-AccessControlPolicyParameters <Object>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### MetadataUrl
```
Add-AdfsRelyingPartyTrust -Name <String> -MetadataUrl <Uri> [-EncryptClaims <Boolean>] [-Enabled <Boolean>]
 [-AutoUpdateEnabled <Boolean>] [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-Notes <String>] [-SignatureAlgorithm <String>] [-SigningCertificateRevocationCheck <String>]
 [-TokenLifetime <Int32>] [-AlwaysRequireAuthentication] [-RequestMFAFromClaimsProviders]
 [-AllowedAuthenticationClassReferences <String[]>] [-EncryptionCertificateRevocationCheck <String>]
 [-NotBeforeSkew <Int32>] [-ProtocolProfile <String>] [-ClaimsProviderName <String[]>] [-EnableJWT <Boolean>]
 [-SamlResponseSignature <String>] [-AllowedClientTypes <AllowedClientTypes>]
 [-IssueOAuthRefreshTokensTo <RefreshTokenIssuanceDeviceTypes>] [-RefreshTokenProtectionEnabled <Boolean>]
 [-PassThru] [-MonitoringEnabled <Boolean>] [-ImpersonationAuthorizationRules <String>]
 [-ImpersonationAuthorizationRulesFile <String>] [-IssuanceTransformRules <String>]
 [-IssuanceTransformRulesFile <String>] [-IssuanceAuthorizationRules <String>]
 [-IssuanceAuthorizationRulesFile <String>] [-DelegationAuthorizationRules <String>]
 [-DelegationAuthorizationRulesFile <String>] [-AdditionalAuthenticationRules <String>]
 [-AdditionalAuthenticationRulesFile <String>] [-AccessControlPolicyName <String>]
 [-AccessControlPolicyParameters <Object>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsRelyingPartyTrust** cmdlet adds a new relying party trust to the Federation Service.
You can specify a relying party trust manually, or you can provide a federation metadata document to bootstrap initial configuration.

## EXAMPLES

### Example 1: Add a relying party trust
```
PS C:\> Add-ADFSRelyingPartyTrust -Name "Fabrikam" -MetadataURL "https://fabrikam.com/federationmetadata/2007-06/federationmetadata.xml"
```

This command adds a relying party trust named Fabrikam for federation.

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
Parameter Sets: AllProperties
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: AllProperties
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

### -Enabled
Indicates whether the relying party trust is enabled.

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
Indicates whether the claims that are sent to the relying party are encrypted.

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
Parameter Sets: AllProperties
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionCertificateRevocationCheck
Specifies the type of validation that should occur for the encryption certificate it is used for encrypting claims to the relying party.
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
Specifies the unique identifiers for this relying party trust.
No other trust can use an identifier from this list.
Uniform Resource Identifiers (URIs) are often used as unique identifiers for a relying party trust, but you can use any string of characters.

```yaml
Type: String[]
Parameter Sets: AllProperties
Aliases:

Required: True
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
Specifies the file that contains the impersonation authorization rules for issuing claims to this relying party.

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
Specifies the file that contains the issuance authorization rules for issuing claims to this relying party.

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
Specifies the file that contains the issuance transform rules for issuing claims to this relying party.

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

### -MetadataFile
Specifies a file path, such as c:\metadata.xml, that contains the federation metadata for this relying party trust.

```yaml
Type: String
Parameter Sets: MetadataFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MetadataUrl
Specifies a URL at which the federation metadata for this relying party trust is available.

```yaml
Type: Uri
Parameter Sets: MetadataUrl
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonitoringEnabled
Indicates whether periodic monitoring of this relying party federation metadata is enabled.
The *MetadataUrl* parameter specifies the URL of the relying party federation metadata.

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

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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
The acceptable values for this parameter are:

- SAML
- WsFederation
- WsFed-SAML

The default value is WsFed-SAML.

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
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RequestSigningCertificate
Specifies an array of certificates to be used to verify the signature on a request from the relying party.

```yaml
Type: X509Certificate2[]
Parameter Sets: AllProperties
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
Parameter Sets: AllProperties
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SamlResponseSignature
Specifies the response signature or signatures that the relying party expects.
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
Specifies the type of certificate validation that occur when signatures on requests from the relying party are verified.
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

### -TokenLifetime
Specifies the duration, in minutes, for which the claims that are issued to the relying party are valid.

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
Parameter Sets: AllProperties
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

String objects are received by the *AccessControlPolicyName*, *AdditionalAuthenticationRules*, *DelegationAuthorizationRules*, *ImpersonationAuthorizationRules*, *IssuanceAuthorizationRules*, and *IssuanceTransformRules* parameters.

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

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.RelyingPartyTrust

Returns the new RelyingPartyTrust object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES
* A relying party in Active Directory Federation Services (AD FS) is an organization in which Web servers that host one or more Web-based applications reside. Tokens and Information Cards that originate from a claims provider can then be presented and ultimately accessed by the Web-based resources that are located in the relying party organization. When AD FS is configured in the role of the relying party, it acts as a partner that trusts a claims provider to authenticate users. Therefore, the relying party accesses the claims that are packaged in security tokens that come from users in the claims provider. In other words, a relying party is the organization whose Web servers are protected by the resource-side federation server. The federation server in the relying party uses the security tokens that the claims provider produces to issue tokens to the Web servers that are located in the relying party.

## RELATED LINKS

[Disable-AdfsRelyingPartyTrust](./Disable-AdfsRelyingPartyTrust.md)

[Enable-AdfsRelyingPartyTrust](./Enable-AdfsRelyingPartyTrust.md)

[Get-AdfsRelyingPartyTrust](./Get-AdfsRelyingPartyTrust.md)

[Remove-AdfsRelyingPartyTrust](./Remove-AdfsRelyingPartyTrust.md)

[Set-AdfsRelyingPartyTrust](./Set-AdfsRelyingPartyTrust.md)

[Update-AdfsRelyingPartyTrust](./Update-AdfsRelyingPartyTrust.md)

