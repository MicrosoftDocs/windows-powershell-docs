---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/hide-wmsidentifier?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Hide-WmsIdentifier
---

# Hide-WmsIdentifier

## SYNOPSIS
Hides the identification window for a station or session.

## SYNTAX

### HideIdentifyBySessionId
```
Hide-WmsIdentifier [-SessionId <UInt32[]>] [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HideIdentifyByStationId
```
Hide-WmsIdentifier [-StationId <UInt32[]>] [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### HideIdentifyAll
```
Hide-WmsIdentifier [-All] [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Hide-WmsIdentifier** cmdlet hides identification window for the specified station or session.

## EXAMPLES

### Example 1: Hide the identification window for a session
```
PS C:\> Hide-WmsIdentifier -SessionID 2
```

This command hides the identification window for the session with the ID of 2.

## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: HideIdentifyAll
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -SessionId
Specifies an array of session IDs.

```yaml
Type: UInt32[]
Parameter Sets: HideIdentifyBySessionId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StationId
Specifies an array of station IDs.

```yaml
Type: UInt32[]
Parameter Sets: HideIdentifyByStationId
Aliases:

Required: False
Position: Named
Default value: None
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

### System.UInt32[]

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Show-WmsIdentifier](./Show-WmsIdentifier.md)

