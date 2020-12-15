---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
ms.assetid: 79C5CC0C-311C-450E-AFF5-666E85FCE249
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-ADFSRelyingPartyTrust

## SYNOPSIS
Sets the properties of a relying party trust.

## SYNTAX

### Identifier
```
Set-ADFSRelyingPartyTrust [-Name <String>] [-NotBeforeSkew <Int32>] [-Identifier <String[]>]
 [-EncryptionCertificate <X509Certificate2>] [-EncryptionCertificateRevocationCheck <String>]
 [-EncryptClaims <Boolean>] [-MetadataUrl <Uri>] [-IssuanceAuthorizationRules <String>]
 [-IssuanceAuthorizationRulesFile <String>] [-DelegationAuthorizationRules <String>]
 [-DelegationAuthorizationRulesFile <String>] [-ImpersonationAuthorizationRules <String>]
 [-ImpersonationAuthorizationRulesFile <String>] [-IssuanceTransformRules <String>]
 [-IssuanceTransformRulesFile <String>] [-AutoUpdateEnabled <Boolean>] [-WSFedEndpoint <Uri>]
 [-MonitoringEnabled <Boolean>] [-Notes <String>] [-ClaimAccepted <ClaimDescription[]>]
 [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>] [-RequestSigningCertificate <X509Certificate2[]>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>] [-SamlResponseSignature <String>]
 [-SignatureAlgorithm <String>] [-SigningCertificateRevocationCheck <String>] [-TokenLifetime <Int32>]
 -TargetIdentifier <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Set-ADFSRelyingPartyTrust [-Name <String>] [-NotBeforeSkew <Int32>] [-Identifier <String[]>]
 [-EncryptionCertificate <X509Certificate2>] [-EncryptionCertificateRevocationCheck <String>]
 [-EncryptClaims <Boolean>] [-MetadataUrl <Uri>] [-IssuanceAuthorizationRules <String>]
 [-IssuanceAuthorizationRulesFile <String>] [-DelegationAuthorizationRules <String>]
 [-DelegationAuthorizationRulesFile <String>] [-ImpersonationAuthorizationRules <String>]
 [-ImpersonationAuthorizationRulesFile <String>] [-IssuanceTransformRules <String>]
 [-IssuanceTransformRulesFile <String>] [-AutoUpdateEnabled <Boolean>] [-WSFedEndpoint <Uri>]
 [-MonitoringEnabled <Boolean>] [-Notes <String>] [-ClaimAccepted <ClaimDescription[]>]
 [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>] [-RequestSigningCertificate <X509Certificate2[]>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>] [-SamlResponseSignature <String>]
 [-SignatureAlgorithm <String>] [-SigningCertificateRevocationCheck <String>] [-TokenLifetime <Int32>]
 -TargetRelyingParty <RelyingPartyTrust> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierName
```
Set-ADFSRelyingPartyTrust [-Name <String>] [-NotBeforeSkew <Int32>] [-Identifier <String[]>]
 [-EncryptionCertificate <X509Certificate2>] [-EncryptionCertificateRevocationCheck <String>]
 [-EncryptClaims <Boolean>] [-MetadataUrl <Uri>] [-IssuanceAuthorizationRules <String>]
 [-IssuanceAuthorizationRulesFile <String>] [-DelegationAuthorizationRules <String>]
 [-DelegationAuthorizationRulesFile <String>] [-ImpersonationAuthorizationRules <String>]
 [-ImpersonationAuthorizationRulesFile <String>] [-IssuanceTransformRules <String>]
 [-IssuanceTransformRulesFile <String>] [-AutoUpdateEnabled <Boolean>] [-WSFedEndpoint <Uri>]
 [-MonitoringEnabled <Boolean>] [-Notes <String>] [-ClaimAccepted <ClaimDescription[]>]
 [-SamlEndpoint <SamlEndpoint[]>] [-ProtocolProfile <String>] [-RequestSigningCertificate <X509Certificate2[]>]
 [-EncryptedNameIdRequired <Boolean>] [-SignedSamlRequestsRequired <Boolean>] [-SamlResponseSignature <String>]
 [-SignatureAlgorithm <String>] [-SigningCertificateRevocationCheck <String>] [-TokenLifetime <Int32>]
 -TargetName <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADFSRelyingParty cmdlet configures the trust relationship with a specified relying party object.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADFSRelyingPartyTrust -TargetName SampleApp -Identifier  http://SampleApp.SampleServerNew.org
```

Description

-----------

Sets the name and identifier for the specified relying party trust.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Set-ADFSRelyingPartyTrust -TargetIdentifier http://SampleApp.SampleServer.org -Identifier http://SampleApp.SampleServerNew.org
```

Description

-----------

Sets the target identifier for the specified relying party trust.

## PARAMETERS

### -AutoUpdateEnabled
Specifies whether changes to the federation metadata at the MetadataURL that is being monitored are automatically applied to the configuration of the trust relationship.
Partner claims, certificates, and endpoints are automatically updated if this parameter is enabled (true).

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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionCertificateRevocationCheck
Specifies the type of validation that should occur for the encryption certificate before it is used for encrypting claims to the relying party.
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
Specifies a file that containis the impersonation authorization rules for issuing claims to this relying party.

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

Note: You can use the Name parameter as an identifier for the object.

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
The protocol can be one of the following: {SAML, WsFederation}. 
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

### -RequestSigningCertificate
Specifies the certificate that is used to verify the signature on a request from the relying party.

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
Specifies the SAML protocol endpoints for this relying party.

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

### -TargetIdentifier
Specifies the identifier of the relying party trust that will be modified by the cmdlet.

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
Specifies the friendly name of the relying party trust that will be modified by the cmdlet.

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
Specifies the relying party trust that will be modified by the cmdlet.
This value is typically taken from the pipeline.

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
Specifies the duration (in minutes) for which the claims that are issued to the relying party are valid.

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

### Microsoft.IdentityServer.PowerShell.Resources.RelyingPartyTrust
A class structure that represents a relying party trust.

## OUTPUTS

### None

## NOTES
* A relying party in Active Directory Federation Services (AD FS) 2.0 is an organization in which Web servers that host one or more Web-based applications reside. Tokens and Information Cards that originate from a claims provider can be presented and ultimately consumed by the Web-based resources that are located in the relying party organization. When AD FS 2.0 is configured in the role of the relying party, it acts as a partner that trusts a claims provider to authenticate users. Therefore, the relying party consumes the claims that are packaged in security tokens that come from users in the claims provider. In other words, a relying party is the organization whose Web servers are protected by the resource-side federation server. The federation server at the relying party uses the security tokens that the claims provider produces to issue tokens to the Web servers that are located in the relying party.

## RELATED LINKS

[Add-ADFSRelyingPartyTrust](./Add-ADFSRelyingPartyTrust.md)

[Disable-ADFSRelyingPartyTrust](./Disable-ADFSRelyingPartyTrust.md)

[Enable-ADFSRelyingPartyTrust](./Enable-ADFSRelyingPartyTrust.md)

[Get-ADFSRelyingPartyTrust](./Get-ADFSRelyingPartyTrust.md)

[Remove-ADFSRelyingPartyTrust](./Remove-ADFSRelyingPartyTrust.md)

[Update-ADFSRelyingPartyTrust](./Update-ADFSRelyingPartyTrust.md)

