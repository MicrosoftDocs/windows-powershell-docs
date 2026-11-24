---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/enable-adfsclaimsprovidertrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-AdfsClaimsProviderTrust
---

# Enable-AdfsClaimsProviderTrust

## SYNOPSIS
Enables a claims provider trust in the Federation Service.

## SYNTAX

### IdentifierObject
```
Enable-AdfsClaimsProviderTrust -TargetClaimsProviderTrust <ClaimsProviderTrust> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### TokenSigningCertificates
```
Enable-AdfsClaimsProviderTrust -TargetCertificate <X509Certificate2> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Identifier
```
Enable-AdfsClaimsProviderTrust -TargetIdentifier <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierName
```
Enable-AdfsClaimsProviderTrust -TargetName <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-AdfsClaimsProviderTrust** cmdlet enables a claims provider trust in the Federation Service.

## EXAMPLES

### Example 1: Enable a claims provider trust
```
PS C:\> Enable-AdfsClaimsProviderTrust -TargetName "Fabrikam claims provider"
```

This command enables a claims provider trust with the name Fabrikam claims provider.

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
Specifies the token-signing certificate of the claims provider trust to enable.

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
Specifies the identifier of the claims provider trust to enable.

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
Specifies the name of the claims provider trust to enable.

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

Returns the disabled ClaimsProviderTrust object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES
* A relying party in Active Directory Federation Services (AD FS) is an organization in which web servers that host one or more web-based applications reside. Tokens and Information Cards that originate from a claims provider can then be presented and ultimately accessed by the web-based resources that are located in the relying party organization. When AD FS is configured in the role of the relying party, it acts as a partner that trusts a claims provider to authenticate users. Therefore, the relying party accesses the claims that are packaged in security tokens that come from users in the claims provider. In other words, a relying party is the organization whose web servers are protected by the resource-side federation server. The federation server in the relying party uses the security tokens that the claims provider produces to issue tokens to the web servers that are located in the relying party.

## RELATED LINKS

[Add-AdfsClaimsProviderTrust](./Add-AdfsClaimsProviderTrust.md)

[Disable-AdfsClaimsProviderTrust](./Disable-AdfsClaimsProviderTrust.md)

[Get-AdfsClaimsProviderTrust](./Get-AdfsClaimsProviderTrust.md)

[Remove-AdfsClaimsProviderTrust](./Remove-AdfsClaimsProviderTrust.md)

[Set-AdfsClaimsProviderTrust](./Set-AdfsClaimsProviderTrust.md)

[Update-AdfsClaimsProviderTrust](./Update-AdfsClaimsProviderTrust.md)

