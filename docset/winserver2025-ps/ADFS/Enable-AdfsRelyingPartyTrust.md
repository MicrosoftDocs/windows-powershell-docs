---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/enable-adfsrelyingpartytrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-AdfsRelyingPartyTrust
---

# Enable-AdfsRelyingPartyTrust

## SYNOPSIS
Enables a relying party trust of the Federation Service.

## SYNTAX

### Identifier
```
Enable-AdfsRelyingPartyTrust -TargetIdentifier <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Enable-AdfsRelyingPartyTrust -TargetRelyingParty <RelyingPartyTrust> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### IdentifierName
```
Enable-AdfsRelyingPartyTrust -TargetName <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-AdfsRelyingPartyTrust** cmdlet enables a relying party trust of the Federation Service.

## EXAMPLES

### Example 1: Enable a relying party trust
```
PS C:\> Enable-ADFSRelyingPartyTrust -TargetName "Fabrikam01"
```

This command enables the relying party trust named Fabrikam01.

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

### -TargetIdentifier
Specifies the identifier of the relying party trust to enable.

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
Specifies the name of the relying party trust to enable.

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
Specifies a **RelyingPartyTrust** object.
The cmdlet disables the relying party trust that you specify.
To obtain a **RelyingPartyTrust** object, use the **Get-AdfsRelyingPartyTrust** cmdlet.

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

### System.String

String objects are received by the *TargetIdentifier* and *TargetName* parameters.

### Microsoft.IdentityServer.PowerShell.Resources.RelyingPartyTrust

RelyingPartytrust objects are received by the *TargetRelyingParty* parameter.

## OUTPUTS

### Microsoft.IdentityServer.PowerShell.Resources.RelyingPartyTrust

Returns the enabled RelyingPartyTrust object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES
* A relying party in Active Directory Federation Services (AD FS) is an organization in which Web servers that host one or more Web-based applications reside. Tokens and Information Cards that originate from a claims provider can then be presented and ultimately accessed by the Web-based resources that are located in the relying party organization. When AD FS is configured in the role of the relying party, it acts as a partner that trusts a claims provider to authenticate users. Therefore, the relying party accesses the claims that are packaged in security tokens that come from users in the claims provider. In other words, a relying party is the organization whose Web servers are protected by the resource-side federation server. The federation server in the relying party uses the security tokens that the claims provider produces to issue tokens to the Web servers that are located in the relying party.

## RELATED LINKS

[Add-AdfsRelyingPartyTrust](./Add-AdfsRelyingPartyTrust.md)

[Disable-AdfsRelyingPartyTrust](./Disable-AdfsRelyingPartyTrust.md)

[Get-AdfsRelyingPartyTrust](./Get-AdfsRelyingPartyTrust.md)

[Remove-AdfsRelyingPartyTrust](./Remove-AdfsRelyingPartyTrust.md)

[Set-AdfsRelyingPartyTrust](./Set-AdfsRelyingPartyTrust.md)

[Update-AdfsRelyingPartyTrust](./Update-AdfsRelyingPartyTrust.md)

