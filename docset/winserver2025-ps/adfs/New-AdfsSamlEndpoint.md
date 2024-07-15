---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/new-adfssamlendpoint?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-AdfsSamlEndpoint
---

# New-AdfsSamlEndpoint

## SYNOPSIS
Creates a SAML protocol endpoint object.

## SYNTAX

```
New-AdfsSamlEndpoint -Binding <String> -Protocol <String> -Uri <Uri> [-IsDefault <Boolean>] [-Index <Int32>]
 [-ResponseUri <Uri>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AdfsSamlEndpoint** cmdlet creates a Security Assertion Markup Language (SAML) protocol endpoint object.

## EXAMPLES

### Example 1: Create a SAML endpoint and assign it to a relying party
```
PS C:\> $EP = New-AdfsSamlEndpoint -Binding "POST" -Protocol "SAMLAssertionConsumer" -Uri "https://fabrikam.com/saml/ac"
PS C:\> Set-AdfsRelyingPartyTrust -TargetName "My application" -SamlEndpoint $EP
```

The first command creates a SAML endpoint, and then stores it in the $EP variable.

The second command uses the **Set-AdfsRelyingPartyTrust** cmdlet to assign the endpoint stored in $EP to a relying party trust named My application.

## PARAMETERS

### -Binding
Specifies the binding type of the endpoint.
The acceptable values for this parameter are: POST, SOAP, Artifact, and Redirect.

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
Indicates whether this is a default endpoint for the particular protocol type.

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
The acceptable values for this parameter are: SAMLSingleSignOn, SAMLArtifactResolution, SAMLLogout, and SAMLAssertionConsumer.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.SamlEndpoint
This cmdlet generates a class structure that represents a SAML endpoint resource object.

## NOTES
* You can associate this object with a relying party trust or claims provider trust by using the corresponding cmdlets.

## RELATED LINKS

[Get-AdfsClaimsProviderTrust](./Get-AdfsClaimsProviderTrust.md)

[Get-AdfsRelyingPartyTrust](./Get-AdfsRelyingPartyTrust.md)

[Set-AdfsClaimsProviderTrust](./Set-AdfsClaimsProviderTrust.md)

[Set-AdfsRelyingPartyTrust](./Set-AdfsRelyingPartyTrust.md)

[Update-AdfsClaimsProviderTrust](./Update-AdfsClaimsProviderTrust.md)

[Update-AdfsRelyingPartyTrust](./Update-AdfsRelyingPartyTrust.md)

