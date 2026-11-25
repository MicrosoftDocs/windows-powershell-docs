---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/disable-adfsrelyingpartytrust?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-AdfsRelyingPartyTrust
---

# Disable-AdfsRelyingPartyTrust

## SYNOPSIS
Disables a relying party trust of the Federation Service.

## SYNTAX

### Identifier
```
Disable-AdfsRelyingPartyTrust -TargetIdentifier <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Disable-AdfsRelyingPartyTrust -TargetRelyingParty <RelyingPartyTrust> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### IdentifierName
```
Disable-AdfsRelyingPartyTrust -TargetName <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-AdfsRelyingPartyTrust** cmdlet disables a relying party trust of the Federation Service.
When disabled, AD FS does not issue tokens when users attempt to access this relying party.

## EXAMPLES

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
Specifies the identifier of the relying party trust to disable.

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
Specifies the name of the relying party trust to disable.

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
Specifies the relying party trust to disable.
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

Returns the disabled RelyingPartyTrust object when the *PassThru* parameter is specified. By default, this cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Add-AdfsRelyingPartyTrust](./Add-AdfsRelyingPartyTrust.md)

[Enable-AdfsRelyingPartyTrust](./Enable-AdfsRelyingPartyTrust.md)

[Get-AdfsRelyingPartyTrust](./Get-AdfsRelyingPartyTrust.md)

[Remove-AdfsRelyingPartyTrust](./Remove-AdfsRelyingPartyTrust.md)

[Set-AdfsRelyingPartyTrust](./Set-AdfsRelyingPartyTrust.md)

