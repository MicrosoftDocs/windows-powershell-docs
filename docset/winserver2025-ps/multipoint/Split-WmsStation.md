---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/split-wmsstation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Split-WmsStation
---

# Split-WmsStation

## SYNOPSIS
Splits a station.

## SYNTAX

### SplitById
```
Split-WmsStation [-StationId] <UInt32[]> [-Server <String>] [<CommonParameters>]
```

### SplitAll
```
Split-WmsStation [-All] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Split-WmsStation** cmdlet splits the specified station into two stations.

## EXAMPLES

### Example 1: Split a station
```
PS C:\> Split-WmsStation -StationId 01
```

This command splits the station with the ID 01 into two stations.

## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: SplitAll
Aliases:

Required: True
Position: Named
Default value: None
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

### -StationId
Specifies an array of station IDs.

```yaml
Type: UInt32[]
Parameter Sets: SplitById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Clear-WmsStation](./Clear-WmsStation.md)

[Get-WmsStation](./Get-WmsStation.md)

[Join-WmsStation](./Join-WmsStation.md)

[Set-WmsStation](./Set-WmsStation.md)

[Update-WmsStation](./Update-WmsStation.md)

