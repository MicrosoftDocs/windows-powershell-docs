---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://learn.microsoft.com/powershell/module/adfs/add-adfsrelyingpartytrust?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ADFSRelyingPartyTrust

## SYNOPSIS
Adds a new relying party trust to the Federation Service.

## SYNTAX

### AllProperties
```
Add-ADFSRelyingPartyTrust -Name <String> -Identifier <String[]> [-EncryptionCertificate <X509Certificate2>]
 [-EncryptClaims <Boolean>] [-IssuanceAuthorizationRules <String>] [-IssuanceAuthorizationRulesFile <String>]
 [-DelegationAuthorizationRules <String>] [-DelegationAuthorizationRulesFile <String>]
 [-EncryptionCertificateRevocationCheck <String>] [-ImpersonationAuthorizationRules <String>]
 [-ImpersonationAuthorizationRulesFile <String>] [-IssuanceTransformRules <String>]
 [-IssuanceTransformRulesFile <String>] [-AutoUpdateEnabled <Boolean>] [-WSFedEndpoint <Uri>]
 [-Enabled <Boolean>] [-MonitoringEnabled <Boolean>] [-NotBeforeSkew <Int32>] [-Notes <String>]
 [-ClaimAccepted <ClaimDescription[]>] [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>]
 [-RequestSigningCertificate <X509Certificate2[]>] [-EncryptedNameIdRequired <Boolean>]
 [-SignedSamlRequestsRequired <Boolean>] [-SamlResponseSignature <String>] [-SignatureAlgorithm <String>]
 [-SigningCertificateRevocationCheck <String>] [-TokenLifetime <Int32>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### MetadataFile
```
Add-ADFSRelyingPartyTrust -Name <String> [-EncryptClaims <Boolean>] [-IssuanceAuthorizationRules <String>]
 [-IssuanceAuthorizationRulesFile <String>] [-DelegationAuthorizationRules <String>]
 [-DelegationAuthorizationRulesFile <String>] [-EncryptionCertificateRevocationCheck <String>]
 [-ImpersonationAuthorizationRules <String>] [-ImpersonationAuthorizationRulesFile <String>]
 [-IssuanceTransformRules <String>] [-IssuanceTransformRulesFile <String>] [-MetadataFile <String>]
 [-AutoUpdateEnabled <Boolean>] [-Enabled <Boolean>] [-MonitoringEnabled <Boolean>] [-NotBeforeSkew <Int32>]
 [-Notes <String>] [-ProtocolProfile <String>] [-EncryptedNameIdRequired <Boolean>]
 [-SignedSamlRequestsRequired <Boolean>] [-SamlResponseSignature <String>] [-SignatureAlgorithm <String>]
 [-SigningCertificateRevocationCheck <String>] [-TokenLifetime <Int32>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### MetadataUrl
```
Add-ADFSRelyingPartyTrust -Name <String> [-EncryptClaims <Boolean>] [-IssuanceAuthorizationRules <String>]
 [-IssuanceAuthorizationRulesFile <String>] [-DelegationAuthorizationRules <String>]
 [-DelegationAuthorizationRulesFile <String>] [-EncryptionCertificateRevocationCheck <String>]
 [-ImpersonationAuthorizationRules <String>] [-ImpersonationAuthorizationRulesFile <String>]
 [-IssuanceTransformRules <String>] [-IssuanceTransformRulesFile <String>] [-MetadataUrl <Uri>]
 [-AutoUpdateEnabled <Boolean>] [-Enabled <Boolean>] [-MonitoringEnabled <Boolean>] [-NotBeforeSkew <Int32>]
 [-Notes <String>] [-ProtocolProfile <String>] [-EncryptedNameIdRequired <Boolean>]
 [-SignedSamlRequestsRequired <Boolean>] [-SamlResponseSignature <String>] [-SignatureAlgorithm <String>]
 [-SigningCertificateRevocationCheck <String>] [-TokenLifetime <Int32>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Add-ADFSRelyingPartyTrust cmdlet adds a new relying party trust to the Federation Service.
A relying party trust can be specified manually, or a federation metadata document may be provided to bootstrap initial configuration.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Add-ADFSRelyingPartyTrust -Name 'Fabrikam' -MetadataURL 'https://fabrikam.com/federationmetadata/2007-06/federationmetadata.xml'
```

Description

-----------

Adds a relying party trust named Fabrikam for federation.

## PARAMETERS

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

### -ClaimAccepted
Specifies the claims that this relying party accepts.

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
Specifies whether the relying party trust is enabled.

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
Specifies whether the claims that are sent to the relying party should be encrypted.

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

### -Identifier
Specifies the unique identifiers for this relying party trust.
No other trust may use an identifier from this list.
Uniform Resource Identifiers (URIs) are often used as unique identifiers for a relying party trust, but any string of characters may be used.

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
Specifies the file containing the issuance authorization rules for issuing claims to this relying party.

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

### -MetadataFile
Specifies a file path, such as c:\metadata.xml, that contains the federation metadata for this relying party trust.

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
Specifies a URL at which the federation metadata for this relying party trust is available.

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
Specifies whether periodic monitoring of this relying party's federation metadata is enabled.
The URL of the relying party's federation metadata is specified by the MetadataUrl parameter.

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
Specifies any notes for this relying party trust.

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
This parameter controls which protocol profiles the relying party supports.
The protocols can be one of the following: {SAML, WsFederation, WsFed-SAML}.
By default, this parameter is WsFed-SAML.

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

### -RequestSigningCertificate
Specifies the certificate to be used to verify the signature on a request from the relying party.

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
Specifies the SAML protocol endpoints for this relying party.

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
Valid values are AssertionOnly, MessageAndAssertion, and MessageOnly.

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
Specifies the type of certificate validation that should occur when signatures on requests from the relying party are verified.
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

### -TokenLifetime
Specifies the duration in minutes for which the claims that are issued to the relying party are valid.

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

## NOTES
* A relying party in Active Directory Federation Services (AD FS) 2.0 is an organization in which Web servers that host one or more Web-based applications reside. Tokens and Information Cards that originate from a claims provider can then be presented and ultimately consumed by the Web-based resources that are located in the relying party organization. When AD FS 2.0 is configured in the role of the relying party, it acts as a partner that trusts a claims provider to authenticate users. Therefore, the relying party consumes the claims that are packaged in security tokens that come from users in the claims provider. In other words, a relying party is the organization whose Web servers are protected by the resource-side federation server. The federation server in the relying party uses the security tokens that the claims provider produces to issue tokens to the Web servers that are located in the relying party.

  

## RELATED LINKS

[Disable-ADFSRelyingPartyTrust](./Disable-ADFSRelyingPartyTrust.md)

[Enable-ADFSRelyingPartyTrust](./Enable-ADFSRelyingPartyTrust.md)

[Get-ADFSRelyingPartyTrust](./Get-ADFSRelyingPartyTrust.md)

[Remove-ADFSRelyingPartyTrust](./Remove-ADFSRelyingPartyTrust.md)

[Set-ADFSRelyingPartyTrust](./Set-ADFSRelyingPartyTrust.md)

[Update-ADFSRelyingPartyTrust](./Update-ADFSRelyingPartyTrust.md)

