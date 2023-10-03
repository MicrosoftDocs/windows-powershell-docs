---
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/adfs/get-adfsclaimsprovidertrust?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AdfsClaimsProviderTrust
---

# Get-AdfsClaimsProviderTrust

## SYNOPSIS
Gets the claims provider trusts in the Federation Service.

## SYNTAX

### ClaimsProviderName (Default)
```
Get-AdfsClaimsProviderTrust [[-Name] <String[]>] [<CommonParameters>]
```

### TokenSigningCertificates
```
Get-AdfsClaimsProviderTrust [-Certificate] <X509Certificate2[]> [<CommonParameters>]
```

### Identifier
```
Get-AdfsClaimsProviderTrust [-Identifier] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-AdfsClaimsProviderTrust** cmdlet gets the claims provider trusts in the Federation Service.
You can use this cmdlet with no parameters to get all the claims provider trust objects.

## EXAMPLES

### Example 1: Get claims provider trusts
```
PS C:\> Get-AdfsClaimsProviderTrust -Name "Fabrikam claims provider"
```

This command gets the property settings for the claims provider trust named Fabrikam claims provider.

## PARAMETERS

### -Certificate
Specifies an array of token-signing certificates of the claims provider trust to get.

```yaml
Type: X509Certificate2[]
Parameter Sets: TokenSigningCertificates
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Identifier
Specifies an array of unique IDs of the claims provider trust to get.

```yaml
Type: String[]
Parameter Sets: Identifier
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of display names of the claims provider trust to get.

```yaml
Type: String[]
Parameter Sets: ClaimsProviderName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimsProviderTrust
The cmdlet outputs a class structure that represents the claims provider trusts for the Federation Service.

## NOTES
* If you do not specify the **Name** parameter, the cmdlet lists all claims providers. The claims provider collects and authenticates a user's credentials, builds up claims for that user, and packages the claims into security tokens or Information Cards. In other words, a claims provider represents the organization for whose users the claims provider issues security tokens or Information Cards on their behalf. When you configure Active Directory Federation Services (AD FS) 2.0, the role of the claims provider is to enable its users to access resources that are hosted in a relying party organization by establishing one side of the federation trust relationship. After the federation trust is established, tokens and Information Cards can be presented to the relying party across the trust.

## RELATED LINKS

[Disable-AdfsClaimsProviderTrust](./Disable-AdfsClaimsProviderTrust.md)

[Enable-AdfsClaimsProviderTrust](./Enable-AdfsClaimsProviderTrust.md)

[Remove-AdfsClaimsProviderTrust](./Remove-AdfsClaimsProviderTrust.md)

[Set-AdfsClaimsProviderTrust](./Set-AdfsClaimsProviderTrust.md)

[Update-AdfsClaimsProviderTrust](./Update-AdfsClaimsProviderTrust.md)

