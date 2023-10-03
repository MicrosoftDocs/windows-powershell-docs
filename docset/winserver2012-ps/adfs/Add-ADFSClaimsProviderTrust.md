---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfsclaimsprovidertrust?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ADFSClaimsProviderTrust

## SYNOPSIS
Adds a new claims provider trust to the Federation Service.

## SYNTAX

### AllProperties
```
Add-ADFSClaimsProviderTrust -Name <String> -Identifier <String> -TokenSigningCertificate <X509Certificate2[]>
 [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>] [-AcceptanceTransformRules <String>]
 [-AcceptanceTransformRulesFile <String>] [-EncryptionCertificate <X509Certificate2>]
 [-EncryptionCertificateRevocationCheck <String>] [-WSFedEndpoint <Uri>] [-Enabled <Boolean>]
 [-MonitoringEnabled <Boolean>] [-Notes <String>] [-ClaimOffered <ClaimDescription[]>]
 [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>] [-RequiredNameIdFormat <Uri>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlAuthenticationRequestIndex <UInt16>] [-SamlAuthenticationRequestParameters <String>]
 [-SamlAuthenticationRequestProtocolBinding <String>] [-SignatureAlgorithm <String>]
 [-SigningCertificateRevocationCheck <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MetadataFile
```
Add-ADFSClaimsProviderTrust -Name <String> [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>]
 [-AcceptanceTransformRules <String>] [-AcceptanceTransformRulesFile <String>]
 [-EncryptionCertificateRevocationCheck <String>] [-MetadataFile <String>] [-Enabled <Boolean>]
 [-MonitoringEnabled <Boolean>] [-Notes <String>] [-ProtocolProfile <String>] [-RequiredNameIdFormat <Uri>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlAuthenticationRequestIndex <UInt16>] [-SamlAuthenticationRequestParameters <String>]
 [-SamlAuthenticationRequestProtocolBinding <String>] [-SignatureAlgorithm <String>]
 [-SigningCertificateRevocationCheck <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MetadataUrl
```
Add-ADFSClaimsProviderTrust -Name <String> [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>]
 [-AcceptanceTransformRules <String>] [-AcceptanceTransformRulesFile <String>]
 [-EncryptionCertificateRevocationCheck <String>] [-MetadataUrl <Uri>] [-Enabled <Boolean>]
 [-MonitoringEnabled <Boolean>] [-Notes <String>] [-ProtocolProfile <String>] [-RequiredNameIdFormat <Uri>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlAuthenticationRequestIndex <UInt16>] [-SamlAuthenticationRequestParameters <String>]
 [-SamlAuthenticationRequestProtocolBinding <String>] [-SignatureAlgorithm <String>]
 [-SigningCertificateRevocationCheck <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Add-ADFSClaimsProviderTrust cmdlet adds a new claims provider trust to the Federation Service. 
A claims provider trust can be specified manually, or a federation metadata document may be provided to bootstrap initial configuration.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Add-ADFSClaimProviderTrust -Name 'Fabrikam' -MetadataURL 'https://fabrikam.com/federationmetadata/2007-06/federationmetadata.xml'
```

Description

-----------

Adds a claims provider trust named Fabrikam for federation.

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
Specifies a file containing the claim acceptance transform rules for accepting claims from this claims provider.

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
Specifies whether changes to the federation metadata at the MetadataURL that is being monitored are applied automatically to the configuration of the trust relationship.
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
Parameter Sets: AllProperties
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

### -Enabled
Specifies whether the claims provider trust is enabled or disabled.

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
Parameter Sets: AllProperties
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
Parameter Sets: AllProperties
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MetadataFile
Specifies a file path, such as c:\metadata.xml, that contains the federation metadata to be used when this claims provider trust is created.

```yaml
Type: String
Parameter Sets: MetadataFile
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MetadataUrl
Specifies a URL at which the federation metadata for this claims provider trust is available.

```yaml
Type: Uri
Parameter Sets: MetadataUrl
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

Required: True
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
The protocols can be one of the following: {SAML, WsFederation, WsFed-SAML}.
By default, this parameter is WsFed-SAML.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: WSFederation, WsFed-SAML, SAML

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
Specify a value from the set: {None, Index, Url, ProtocolBinding, UrlWithProtocolBinding}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Index, None, ProtocolBinding, Url, UrlWithProtocolBinding

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SamlAuthenticationRequestProtocolBinding
Specifies the value of ProtocolBinding that will be placed in SAML authentication requests to the claims provider.
Use values from the set: {Artifact, Post, Redirect}

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Artifact, POST, Redirect

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
Parameter Sets: AllProperties
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SignatureAlgorithm
Specifies the signature algorithm that the claims provider uses for signing and verification. 
Valid values are:

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

### -TokenSigningCertificate
Specifies the token-signing certificates to be used by the claims provider.

```yaml
Type: X509Certificate2[]
Parameter Sets: AllProperties
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WSFedEndpoint
Specifies the WS-Federation Passive URL for this claims provider.

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

### None

## OUTPUTS

### None
The claims provider is responsible for collecting and authenticating a user's credentials, building up claims for that user, and packaging the claims into security tokens or Information Cards.
In other words, a claims provider represents the organization for whose users the claims provider issues security tokens or Information Cards on their behalf.
When you configure AD FS 2.0 to use federation services, the role of the claims provider is to enable its users to access resources that a relying party organization hosts by establishing one side of a federation trust relationship.
After the trust is established, tokens and Information Cards can be presented to the relying party across the federation trust.

## NOTES
* The claims provider is responsible for collecting and authenticating a user's credentials, building up claims for that user, and packaging the claims into security tokens or Information Cards. In other words, a claims provider represents the organization for whose users the claims provider issues security tokens or Information Cards on their behalf. When you configure AD FS 2.0 to use federation services, the role of the claims provider is to enable its users to access resources that a relying party organization hosts by establishing one side of a federation trust relationship. After the trust is established, tokens and Information Cards can be presented to the relying party across the federation trust.

## RELATED LINKS

[Disable-ADFSClaimsProviderTrust](./Disable-ADFSClaimsProviderTrust.md)

[Enable-ADFSClaimsProviderTrust](./Enable-ADFSClaimsProviderTrust.md)

[Get-ADFSClaimsProviderTrust](./Get-ADFSClaimsProviderTrust.md)

[Remove-ADFSClaimsProviderTrust](./Remove-ADFSClaimsProviderTrust.md)

[Set-ADFSClaimsProviderTrust](./Set-ADFSClaimsProviderTrust.md)

[Update-ADFSClaimsProviderTrust](./Update-ADFSClaimsProviderTrust.md)

