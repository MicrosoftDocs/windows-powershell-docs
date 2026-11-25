---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/clear-wmsstation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-WmsStation
---

# Clear-WmsStation

## SYNOPSIS
Clears station mapping information for all stations.

## SYNTAX

```
Clear-WmsStation [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-WmsStation** cmdlet clears station mapping information for all stations.

## EXAMPLES

### Example 1: Clear station mapping
```
PS C:\> Clear-WmsStation
```

This command puts all MultiPoint Server stations into an unmapped state.
All station mapping information is lost, along with any station friendly names and station autologon information.

If you subsequently run **Get-WmsStation** it returns no station information.


## PARAMETERS

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

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-WmsStation](./Get-WmsStation.md)

[Join-WmsStation](./Join-WmsStation.md)

[Set-WmsStation](./Set-WmsStation.md)

[Split-WmsStation](./Split-WmsStation.md)

[Update-WmsStation](./Update-WmsStation.md)

