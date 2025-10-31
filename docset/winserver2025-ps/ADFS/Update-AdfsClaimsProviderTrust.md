---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/update-adfsclaimsprovidertrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-AdfsClaimsProviderTrust
---

# Update-AdfsClaimsProviderTrust

## SYNOPSIS
Updates the claims provider trust from federation metadata.

## SYNTAX

### IdentifierObject
```
Update-AdfsClaimsProviderTrust [-MetadataFile <String>] -TargetClaimsProviderTrust <ClaimsProviderTrust>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### TokenSigningCertificates
```
Update-AdfsClaimsProviderTrust [-MetadataFile <String>] -TargetCertificate <X509Certificate2> [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Identifier
```
Update-AdfsClaimsProviderTrust [-MetadataFile <String>] -TargetIdentifier <String> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### IdentifierName
```
Update-AdfsClaimsProviderTrust [-MetadataFile <String>] -TargetName <String> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-AdfsClaimsProviderTrust** cmdlet updates the claims provider trust from federation metadata.

## EXAMPLES

## PARAMETERS

### -MetadataFile
Specifies a UNC file path to a file that contains the federation metadata information for the claims provider.

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
Specifies the token-signing certificate of the claims provider trust to update.

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
Specifies the claims provider trust to update.
This value is typically taken from the pipeline.

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
Specifies the identifier of the claims provider trust to update.

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
Specifies the name of the claims provider trust to update.

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

Returns the updated ClaimsProviderTrust object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Add-AdfsClaimsProviderTrust](./Add-AdfsClaimsProviderTrust.md)

[Disable-AdfsClaimsProviderTrust](./Disable-AdfsClaimsProviderTrust.md)

[Enable-AdfsClaimsProviderTrust](./Enable-AdfsClaimsProviderTrust.md)

[Get-AdfsClaimsProviderTrust](./Get-AdfsClaimsProviderTrust.md)

[Remove-AdfsClaimsProviderTrust](./Remove-AdfsClaimsProviderTrust.md)

[Set-AdfsClaimsProviderTrust](./Set-AdfsClaimsProviderTrust.md)

