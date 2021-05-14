---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://docs.microsoft.com/powershell/module/adfs/set-adfsclaimsprovidertrust?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADFSClaimsProviderTrust

## SYNOPSIS
Sets the properties of a claims provider trust.

## SYNTAX

### IdentifierObject
```
Set-ADFSClaimsProviderTrust [-Name <String>] [-Identifier <String>] [-SignatureAlgorithm <String>]
 [-TokenSigningCertificate <X509Certificate2[]>] [-MetadataUrl <Uri>] [-AcceptanceTransformRules <String>]
 [-AcceptanceTransformRulesFile <String>] [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>]
 [-WSFedEndpoint <Uri>] [-EncryptionCertificate <X509Certificate2>]
 [-EncryptionCertificateRevocationCheck <String>] [-MonitoringEnabled <Boolean>] [-Notes <String>]
 [-ClaimOffered <ClaimDescription[]>] [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>]
 [-RequiredNameIdFormat <Uri>] [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlAuthenticationRequestIndex <UInt16>] [-SamlAuthenticationRequestParameters <String>]
 [-SamlAuthenticationRequestProtocolBinding <String>] [-SigningCertificateRevocationCheck <String>]
 -TargetClaimsProviderTrust <ClaimsProviderTrust> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TokenSigningCertificates
```
Set-ADFSClaimsProviderTrust [-Name <String>] [-Identifier <String>] [-SignatureAlgorithm <String>]
 [-TokenSigningCertificate <X509Certificate2[]>] [-MetadataUrl <Uri>] [-AcceptanceTransformRules <String>]
 [-AcceptanceTransformRulesFile <String>] [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>]
 [-WSFedEndpoint <Uri>] [-EncryptionCertificate <X509Certificate2>]
 [-EncryptionCertificateRevocationCheck <String>] [-MonitoringEnabled <Boolean>] [-Notes <String>]
 [-ClaimOffered <ClaimDescription[]>] [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>]
 [-RequiredNameIdFormat <Uri>] [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlAuthenticationRequestIndex <UInt16>] [-SamlAuthenticationRequestParameters <String>]
 [-SamlAuthenticationRequestProtocolBinding <String>] [-SigningCertificateRevocationCheck <String>]
 -TargetCertificate <X509Certificate2> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Identifier
```
Set-ADFSClaimsProviderTrust [-Name <String>] [-Identifier <String>] [-SignatureAlgorithm <String>]
 [-TokenSigningCertificate <X509Certificate2[]>] [-MetadataUrl <Uri>] [-AcceptanceTransformRules <String>]
 [-AcceptanceTransformRulesFile <String>] [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>]
 [-WSFedEndpoint <Uri>] [-EncryptionCertificate <X509Certificate2>]
 [-EncryptionCertificateRevocationCheck <String>] [-MonitoringEnabled <Boolean>] [-Notes <String>]
 [-ClaimOffered <ClaimDescription[]>] [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>]
 [-RequiredNameIdFormat <Uri>] [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlAuthenticationRequestIndex <UInt16>] [-SamlAuthenticationRequestParameters <String>]
 [-SamlAuthenticationRequestProtocolBinding <String>] [-SigningCertificateRevocationCheck <String>]
 -TargetIdentifier <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierName
```
Set-ADFSClaimsProviderTrust [-Name <String>] [-Identifier <String>] [-SignatureAlgorithm <String>]
 [-TokenSigningCertificate <X509Certificate2[]>] [-MetadataUrl <Uri>] [-AcceptanceTransformRules <String>]
 [-AcceptanceTransformRulesFile <String>] [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>]
 [-WSFedEndpoint <Uri>] [-EncryptionCertificate <X509Certificate2>]
 [-EncryptionCertificateRevocationCheck <String>] [-MonitoringEnabled <Boolean>] [-Notes <String>]
 [-ClaimOffered <ClaimDescription[]>] [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>]
 [-RequiredNameIdFormat <Uri>] [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlAuthenticationRequestIndex <UInt16>] [-SamlAuthenticationRequestParameters <String>]
 [-SamlAuthenticationRequestProtocolBinding <String>] [-SigningCertificateRevocationCheck <String>]
 -TargetName <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADFSClaimsProviderTrust cmdlet configures the trust relationship with a claims provider.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADFSClaimsProviderTrust -TargetName "My claims provider" -AutoUpdateEnabled $false
```

Description

-----------

Enables auto-update for the claims provider trust.

## PARAMETERS

### -AcceptanceTransformRules
Specifies the claim acceptance transform rules for accepting claims from this claims provider.

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
Specifies whether the SAML parameter AllowCreate should be sent in SAML requests to the claims provider.
By default, this parameter is true.

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
Specifies whether changes to the federation metadata at the MetadataURL that is being monitored are automatically applied to the configuration of the trust relationship.
Partner claims, certificates, and endpoints are updated automatically if this parameter is enabled (true).

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
Specifies the claims that are offered by this claims provider.

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

### -EncryptedNameIdRequired
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
Specifies the certificate to be used for encrypting a NameID to this claims provider in SAML logout requests.
Encrypting the NameID is optional.

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
Specifies the unique identifier for this claims provider trust.
No other trust may use an identifier from this list.
Uniform Resource Identifiers (URIs) are often used as unique identifiers for a claims provider trust, but any string of characters may be used.

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
Specifies whether periodic monitoring of this claims provider's federation metadata is enabled.
The URL of the claims provider's federation metadata is specified by the MetadataUrl parameter.

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
Specifies any notes for this claims provider trust.

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
Passes an object to the pipeline.
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
This parameter controls which protocol profiles the claims provider supports.
It must be set to one of the following recognized strings: {SAML, WsFederation, WsFed-SAML}.
By default, both SAML and WS-Federation protocols are supported (WsFed-SAML).

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
Specifies the format that is required for NameID claims to be included in SAML requests to the claims provider.
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
Specifies the value of AssertionConsumerServiceIndex that will be placed in SAML authentication requests that are sent to the claims provider.

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
Specifies which of the parameters (AssertionConsumerServiceIndex, AssertionConsumerServiceUrl, ProtocolBinding) will be used in SAML authentication requests to the claims provider.
Specify a value from the following set: {None, Index, Url, ProtocolBinding, UrlWithProtocolBinding}.

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
Specifies the value of ProtocolBinding that will be placed in SAML authentication requests to the claims provider.
Use values from the following set: {Artifact, Post, Redirect}.

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
Specifies the SAML protocol endpoints for this claims provider.

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
Valid values are as follows:

http://www.w3.org/2000/09/xmldsig#rsa-sha1

http://www.w3.org/2001/04/xmldsig-more#rsa-sha256

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: http://www.w3.org/2000/09/xmldsig#rsa-sha1, http://www.w3.org/2001/04/xmldsig-more#rsa-sha256

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SignedSamlRequestsRequired
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
Specifies the type of certificate validation that should occur when signatures are verified on responses or assertions from the claims provider.
Valid values are None, CheckEndCert, CheckEndCertCacheOnly, CheckChain, CheckChainCacheOnly, CheckChainExcludingRoot, and CheckChainExcludingRootCacheOnly.

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

### -TargetCertificate
Specifies the certificate of the claims provider trust that will be modified by the cmdlet.

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
Specifies the identifier of the claims provider trust that will be modified by the cmdlet.

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
Specifies the friendly name of the claims provider trust that will be modified by the cmdlet.

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
Specifies the token-signing certificates that the claims provider uses.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimsProviderTrust
A class structure that represents a claims provider trust.

## OUTPUTS

### None

## NOTES
* The claims provider collects and authenticates a user's credentials, builds up claims for that user, and packages the claims into security tokens or Information Cards. In other words, a claims provider represents the organization for whose users the claims provider issues security tokens or Information Cards on their behalf. When you configure Active Directory Federation Services (AD FS) 2.0, the role of the claims provider is to enable its users to access resources that are hosted in a relying party organization by establishing one side of a federation trust relationship. After the trust is established, tokens and Information Cards can be presented to a relying party across the federation trust.

## RELATED LINKS

[Disable-ADFSClaimsProviderTrust](./Disable-ADFSClaimsProviderTrust.md)

[Enable-ADFSClaimsProviderTrust](./Enable-ADFSClaimsProviderTrust.md)

[Get-ADFSClaimsProviderTrust](./Get-ADFSClaimsProviderTrust.md)

[Remove-ADFSClaimsProviderTrust](./Remove-ADFSClaimsProviderTrust.md)

[Update-ADFSClaimsProviderTrust](./Update-ADFSClaimsProviderTrust.md)

