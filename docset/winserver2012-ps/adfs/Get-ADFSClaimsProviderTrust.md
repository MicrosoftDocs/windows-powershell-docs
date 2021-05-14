---
external help file: Microsoft.IdentityServer.PowerShell.dll-Help.xml
Module Name: ADFS
online version: https://docs.microsoft.com/powershell/module/adfs/get-adfsclaimsprovidertrust?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADFSClaimsProviderTrust

## SYNOPSIS
Gets the claims provider trusts in the Federation Service.

## SYNTAX

### ClaimsProviderName (Default)
```
Get-ADFSClaimsProviderTrust [[-Name] <String[]>] [<CommonParameters>]
```

### TokenSigningCertificates
```
Get-ADFSClaimsProviderTrust [-Certificate] <X509Certificate2[]> [<CommonParameters>]
```

### Identifier
```
Get-ADFSClaimsProviderTrust [-Identifier] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The Get-ADFSClaimsProviderTrust cmdlet retrieves the claims provider trusts in the Federation Service.
You can use this cmdlet with no parameters to get all the claims provider trust objects.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADFSClaimsProviderTrust -name "My claims provider"
```

Description

-----------

Gets the current property settings for a specified claims provider trust named "My claims provider".

## PARAMETERS

### -Certificate
Specifies the token-signing certificate of the claims provider trust to retrieve.

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
Specifies the unique identifier of the claims provider trust to retrieve.

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
Specifies the display name of the claims provider trust to retrieve.

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
A class structure that represents the claims provider trusts for the Federation Service.

## NOTES
* If no target parameter is provided, all claims providers are listed. The claims provider collects and authenticates a user's credentials, builds up claims for that user, and packages the claims into security tokens or Information Cards. In other words, a claims provider represents the organization for whose users the claims provider issues security tokens or Information Cards on their behalf. When you configure Active Directory Federation Services (AD FS) 2.0, the role of the claims provider is to enable its users to access resources that are hosted in a relying party organization by establishing one side of the federation trust relationship. After the federation trust is established, tokens and Information Cards can be presented to the relying party across the trust.

## RELATED LINKS

[Disable-ADFSClaimsProviderTrust](./Disable-ADFSClaimsProviderTrust.md)

[Enable-ADFSClaimsProviderTrust](./Enable-ADFSClaimsProviderTrust.md)

[Remove-ADFSClaimsProviderTrust](./Remove-ADFSClaimsProviderTrust.md)

[Set-ADFSClaimsProviderTrust](./Set-ADFSClaimsProviderTrust.md)

[Update-ADFSClaimsProviderTrust](./Update-ADFSClaimsProviderTrust.md)

