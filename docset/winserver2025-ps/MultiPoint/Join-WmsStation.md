---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/join-wmsstation?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Join-WmsStation
---

# Join-WmsStation

## SYNOPSIS
Unsplits a station.

## SYNTAX

### JoinById
```
Join-WmsStation [-StationId] <UInt32[]> [-Server <String>] [<CommonParameters>]
```

### JoinAll
```
Join-WmsStation [-All] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Join-WmsStation** cmdlet causes the specified physical station displays that are currently split into two logical displays to be joined back into a single display.

## EXAMPLES

### Example 1: Join station displays
```
PS C:\> Join-WmsStation -StationId 1,2,5
```

This command causes the specified physical station displays which are currently split into two logical displays to be joined back into a single display.

## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: JoinAll
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
Valid values are 1 - the number of stations.

```yaml
Type: UInt32[]
Parameter Sets: JoinById
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

[Set-WmsStation](./Set-WmsStation.md)

[Split-WmsStation](./Split-WmsStation.md)

[Update-WmsStation](./Update-WmsStation.md)

