---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: ADFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/adfs/remove-adfsrelyingpartywebtheme?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-AdfsRelyingPartyWebTheme
---

# Remove-AdfsRelyingPartyWebTheme

## SYNOPSIS
Removes a web theme to a relying party.

## SYNTAX

### IdentifierName
```
Remove-AdfsRelyingPartyWebTheme [-TargetRelyingPartyName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### IdentifierObject
```
Remove-AdfsRelyingPartyWebTheme [-TargetRelyingPartyWebTheme] <AdfsRelyingPartyWebTheme> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-AdfsRelyingPartyWebTheme** cmdlet removes a web theme for a relying party.

## EXAMPLES

### Example 1: Remove a web theme
```
PS C:\> Remove-AdfsRelyingPartyWebTheme -TargetRelyingPartyName "urn:app1"
```

This command removes the relying party web theme for the relying party named urn:app1.

## PARAMETERS

### -TargetRelyingPartyName
Specifies the name of the target relying party for which to remove the web theme.

```yaml
Type: String
Parameter Sets: IdentifierName
Aliases: Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TargetRelyingPartyWebTheme
Specifies the target relying party for which to remove the web theme.

```yaml
Type: AdfsRelyingPartyWebTheme
Parameter Sets: IdentifierObject
Aliases: TargetWebTheme

Required: True
Position: 0
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AdfsRelyingPartyWebTheme](./Get-AdfsRelyingPartyWebTheme.md)

[Set-AdfsRelyingPartyWebTheme](./Set-AdfsRelyingPartyWebTheme.md)

