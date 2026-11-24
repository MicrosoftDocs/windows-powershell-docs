---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/remove-wmssystem?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WmsSystem
---

# Remove-WmsSystem

## SYNOPSIS
Removes a computer from the list of managed systems.

## SYNTAX

```
Remove-WmsSystem [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WmsSystem** cmdlet removes the specified computer from the list of managed systems so that it is no longer remotely managed.

## EXAMPLES

### Example 1: Remove a MultiPoint system
```
PS C:\> Remove-WmsSystem -ComputerName "sample.microsoft.com"
```

This command removes the computer named sample.microsoft.com from the collection of computers that can be managed.

## PARAMETERS

### -ComputerName
Specifies an array of computer host names from the MultiPoint system to remove.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String[]

## OUTPUTS

### Microsoft.WindowsServerSolutions.MultipointServer.PowerShell.Commands.Library.WmsSystem

## NOTES

## RELATED LINKS

[Add-WmsSystem](./Add-WmsSystem.md)

[Get-WmsSystem](./Get-WmsSystem.md)

[Restart-WmsSystem](./Restart-WmsSystem.md)

[Search-WmsSystem](./Search-WmsSystem.md)

[Set-WmsSystem](./Set-WmsSystem.md)

[Stop-WmsSystem](./Stop-WmsSystem.md)

