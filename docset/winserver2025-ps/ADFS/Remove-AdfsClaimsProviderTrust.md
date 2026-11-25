---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfsclaimsprovidertrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsClaimsProviderTrust
---

# Remove-AdfsClaimsProviderTrust

## SYNOPSIS
Removes a claims provider trust from the Federation Service.

## SYNTAX

### IdentifierObject
```
Remove-AdfsClaimsProviderTrust -TargetClaimsProviderTrust <ClaimsProviderTrust> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### TokenSigningCertificates
```
Remove-AdfsClaimsProviderTrust -TargetCertificate <X509Certificate2> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Identifier
```
Remove-AdfsClaimsProviderTrust -TargetIdentifier <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierName
```
Remove-AdfsClaimsProviderTrust -TargetName <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsClaimsProviderTrust** cmdlet removes a claims provider trust from the Federation Service.

## EXAMPLES

### Example 1: Remove a claims provider trust
```
PS C:\> Remove-AdfsClaimsProviderTrust -TargetName "Fabrikam claims provider"
```

This command removes the claims provider trust named Fabrikam claims provider.

## PARAMETERS

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

### -TargetCertificate
Specifies the token-signing certificate of the claims provider trust to remove.

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
Specifies a **ClaimsProviderTrust** object.
The cmdlet enables the claims provider trust that you specify.
To obtain a **ClaimsProviderTrust** object, use the **Get-AdfsClaimsProviderTrust** cmdlet.

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
Specifies the identifier of the claims provider trust to remove.

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
Specifies the name of the claims provider trust to remove.

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

### System.Security.Cryptography.X509Certificates.X509Certificate.X509Certificate2

X509Certificate2 objects are received by the *TargetCertificate* parameter.

### Microsoft.IdentityServer.PowerShell.Resources.ClaimsProviderTrust

ClaimsProviderTrust objects are received by the *TargetClaimsProviderTrust* parameter.

### System.String

String objects are received by the *TargetIdentifier* and *TargetName* parameters.

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.ClaimsProviderTrust

Returns the removed ClaimsProviderTrust object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.


## NOTES
* The claims provider collects and authenticates a user's credentials, builds up claims for that user, and packages the claims into security tokens or Information Cards. In other words, a claims provider represents the organization for whose users the claims provider issues security tokens or Information Cards on their behalf. When you configure Active Directory Federation Services (AD FS), the role of the claims provider is to enable its users to access resources that are hosted in a relying party organization by establishing one side of a federation trust relationship. After the trust is established, tokens and Information Cards can be presented to a relying party across the federation trust.

## RELATED LINKS

[Add-AdfsClaimsProviderTrust](./Add-AdfsClaimsProviderTrust.md)

[Disable-AdfsClaimsProviderTrust](./Disable-AdfsClaimsProviderTrust.md)

[Enable-AdfsClaimsProviderTrust](./Enable-AdfsClaimsProviderTrust.md)

[Get-AdfsClaimsProviderTrust](./Get-AdfsClaimsProviderTrust.md)

[Set-AdfsClaimsProviderTrust](./Set-AdfsClaimsProviderTrust.md)

[Update-AdfsClaimsProviderTrust](./Update-AdfsClaimsProviderTrust.md)

