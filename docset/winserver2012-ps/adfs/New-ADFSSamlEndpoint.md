---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://docs.microsoft.com/powershell/module/adfs/new-adfssamlendpoint?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-ADFSSamlEndpoint

## SYNOPSIS
Creates a new SAML protocol endpoint object.

## SYNTAX

```
New-ADFSSamlEndpoint -Binding <String> -Protocol <String> -Uri <Uri> [-IsDefault <Boolean>] [-Index <Int32>]
 [-ResponseUri <Uri>] [<CommonParameters>]
```

## DESCRIPTION
The New-ADFSSamlEndpoint cmdlet creates a new SAML protocol endpoint object.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>$ep = New-ADFSSamlEndpoint -Binding "POST" -Protocol "SAMLAssertionConsumer" -Uri "https://fabrikam.com/saml/ac"
Set-ADFSRelyingPartyTrust -Name "My application" -SamlEndpoint $ep
```

Description

-----------

Creates a new SAML endpoint and assigns it to a relying party trust named "My application".

## PARAMETERS

### -Binding
Specifies the binding type of the endpoint.
The possible binding types are POST, SOAP, Artifact, and Redirect.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Artifact, POST, Redirect, SOAP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Index
Specifies the index that is defined for this endpoint.

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

### -IsDefault
Specifies that this is a default endpoint for the particular protocol type.

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

### -Protocol
Specifies the type of service at the endpoint.
The possible values are SAMLSingleSignOn, SAMLArtifactResolution, SAMLLogout, and SAMLAssertionConsumer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: SAMLArtifactResolution, SAMLAssertionConsumer, SAMLLogout, SAMLSingleSignOn

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResponseUri
Specifies the response URI for the endpoint.

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

### -Uri
Specifies the URI of this endpoint.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.SamlEndpoint
A class structure that represents a SAML endpoint resource object.

## NOTES
* You can associate this object with a relying party trust or claims provider trust by using the corresponding cmdlets.

## RELATED LINKS

[Get-ADFSClaimsProviderTrust](./Get-ADFSClaimsProviderTrust.md)

[Get-ADFSRelyingPartyTrust](./Get-ADFSRelyingPartyTrust.md)

[Set-ADFSClaimsProviderTrust](./Set-ADFSClaimsProviderTrust.md)

[Set-ADFSRelyingPartyTrust](./Set-ADFSRelyingPartyTrust.md)

[Update-ADFSClaimsProviderTrust](./Update-ADFSClaimsProviderTrust.md)

[Update-ADFSRelyingPartyTrust](./Update-ADFSRelyingPartyTrust.md)

