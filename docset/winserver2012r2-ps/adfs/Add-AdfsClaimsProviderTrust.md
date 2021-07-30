---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/adfs/add-adfsclaimsprovidertrust?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-AdfsClaimsProviderTrust
---

# Add-AdfsClaimsProviderTrust

## SYNOPSIS
Adds a new claims provider trust to the Federation Service.

## SYNTAX

### AllProperties
```
Add-AdfsClaimsProviderTrust -Name <String> -Identifier <String> -TokenSigningCertificate <X509Certificate2[]>
 [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>] [-AcceptanceTransformRules <String>]
 [-AcceptanceTransformRulesFile <String>] [-EncryptionCertificate <X509Certificate2>]
 [-EncryptionCertificateRevocationCheck <String>] [-OrganizationalAccountSuffix <String[]>]
 [-WSFedEndpoint <Uri>] [-Enabled <Boolean>] [-MonitoringEnabled <Boolean>] [-Notes <String>]
 [-ClaimOffered <ClaimDescription[]>] [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>]
 [-RequiredNameIdFormat <Uri>] [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>]
 [-SamlAuthenticationRequestIndex <UInt16>] [-SamlAuthenticationRequestParameters <String>]
 [-SamlAuthenticationRequestProtocolBinding <String>] [-SignatureAlgorithm <String>]
 [-SigningCertificateRevocationCheck <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MetadataFile
```
Add-AdfsClaimsProviderTrust -Name <String> [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>]
 [-AcceptanceTransformRules <String>] [-AcceptanceTransformRulesFile <String>]
 [-EncryptionCertificateRevocationCheck <String>] [-OrganizationalAccountSuffix <String[]>]
 [-MetadataFile <String>] [-Enabled <Boolean>] [-MonitoringEnabled <Boolean>] [-Notes <String>]
 [-ProtocolProfile <String>] [-RequiredNameIdFormat <Uri>] [-EncryptedNameIdRequired <Boolean>]
 [-SignedSamlRequestsRequired <Boolean>] [-SamlAuthenticationRequestIndex <UInt16>]
 [-SamlAuthenticationRequestParameters <String>] [-SamlAuthenticationRequestProtocolBinding <String>]
 [-SignatureAlgorithm <String>] [-SigningCertificateRevocationCheck <String>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### MetadataUrl
```
Add-AdfsClaimsProviderTrust -Name <String> [-AllowCreate <Boolean>] [-AutoUpdateEnabled <Boolean>]
 [-AcceptanceTransformRules <String>] [-AcceptanceTransformRulesFile <String>]
 [-EncryptionCertificateRevocationCheck <String>] [-OrganizationalAccountSuffix <String[]>]
 [-MetadataUrl <Uri>] [-Enabled <Boolean>] [-MonitoringEnabled <Boolean>] [-Notes <String>]
 [-ProtocolProfile <String>] [-RequiredNameIdFormat <Uri>] [-EncryptedNameIdRequired <Boolean>]
 [-SignedSamlRequestsRequired <Boolean>] [-SamlAuthenticationRequestIndex <UInt16>]
 [-SamlAuthenticationRequestParameters <String>] [-SamlAuthenticationRequestProtocolBinding <String>]
 [-SignatureAlgorithm <String>] [-SigningCertificateRevocationCheck <String>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-AdfsClaimsProviderTrust** cmdlet adds a new claims provider trust to the Federation Service.
Use this cmdlet when users from a partner organization need to access resources (relying parties) protected by the Active Directory Federation Services (AD FS) service.
You can specify a claims provider trust manually, or you can provide a federation metadata document to bootstrap initial configuration.

## EXAMPLES

### Example 1: Add a claims provder trust
```
PS C:\>Add-AdfsClaimsProviderTrust -Name 'Fabrikam' -MetadataURL 'https://fabrikam.com/federationmetadata/2007-06/federationmetadata.xml'
```

This command adds a claims provider trust named Fabrikam that has the specified metadata URL to the Federation Service.

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
Specifies a file that contains the claim acceptance transform rules for accepting claims from the claims provider.

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
Indicates whether the Security Assertion Markup Language (SAML) parameter **AllowCreate** is sent in SAML requests to the claims provider.
The default values $True.

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
Indicates whether changes to the federation metadata by the **MetadataURL** parameter apply automatically to the configuration of the trust relationship.
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
Indicates whether the claims provider trust is enabled or disabled.

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
Parameter Sets: AllProperties
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
- CheckChainExcludingRoot
- CheckChainExcludingRootCacheOnly

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
No other trust can use an identifier from this list.
Uniform Resource Identifiers (URIs) are often used as unique identifiers for a claims provider trust, but you can use any string of characters.

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
Indicates whether periodic monitoring of this claims provider's federation metadata is enabled.
The URL of the claims provider's federation metadata is specified by the **MetadataUrl** parameter.

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
{{Fill OrganizationalAccountSuffix Description}}

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

### -ProtocolProfile
Specifies which protocol profiles the claims provider supports.
The acceptable values for this parameter are: SAML, WsFederation, and WsFed-SAML.
The default value is WsFed-SAML.

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
Specifies the value of **AssertionConsumerServiceIndex** that will be placed in SAML authentication requests that are sent to the claims provider.

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
Specifies which of the following parameters to use in SAML authentication requests to the claims provider: **AssertionConsumerServiceIndex**, **AssertionConsumerServiceUrl**, and **ProtocolBinding**.The acceptable values for this parameter are: None, Index, Url, ProtocolBinding, and UrlWithProtocolBinding.

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
Specifies the value of **ProtocolBinding** to place in SAML authentication requests to the claims provider.
The acceptable values for this parameter are: Artifact, Post, and Redirect.

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
Specifies an array of SAML protocol endpoints for this claims provider.

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
The acceptable values for this parameter are:

https://www.w3.org/2000/09/xmldsig#rsa-sha1
https://www.w3.org/2001/04/xmldsig-more#rsa-sha256

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
The acceptable values for this parameter are: None, CheckEndCert, CheckEndCertCacheOnly, CheckChain, CheckChainCacheOnly, CheckChainExcludingRoot, and CheckChainExcludingRootCacheOnly.

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
Specifies an array of token-signing certificates that the claims provider uses.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES
* The claims provider is responsible for collecting and authenticating a user's credentials, building up claims for that user, and packaging the claims into security tokens or Information Cards. In other words, a claims provider represents the organization for whose users the claims provider issues security tokens or Information Cards on their behalf. When you configure Active Directory Federation Services (AD FS) 2.0 to use federation services, the role of the claims provider is to enable its users to access resources that a relying party organization hosts by establishing one side of a federation trust relationship. After the trust is established, tokens and Information Cards can be presented to the relying party across the federation trust.

## RELATED LINKS

[Disable-AdfsClaimsProviderTrust](./Disable-AdfsClaimsProviderTrust.md)

[Enable-AdfsClaimsProviderTrust](./Enable-AdfsClaimsProviderTrust.md)

[Get-AdfsClaimsProviderTrust](./Get-AdfsClaimsProviderTrust.md)

[Remove-AdfsClaimsProviderTrust](./Remove-AdfsClaimsProviderTrust.md)

[Set-AdfsClaimsProviderTrust](./Set-AdfsClaimsProviderTrust.md)

[Update-AdfsClaimsProviderTrust](./Update-AdfsClaimsProviderTrust.md)

