---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/show-wmsidentifier?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Show-WmsIdentifier
---

# Show-WmsIdentifier

## SYNOPSIS
Displays the identification screen for a station.

## SYNTAX

### IdentifyBySession
```
Show-WmsIdentifier -SessionId <UInt32[]> [-Server <String>] [<CommonParameters>]
```

### IdentifyByStation
```
Show-WmsIdentifier -StationId <UInt32[]> [-Server <String>] [<CommonParameters>]
```

### IdentifyAll
```
Show-WmsIdentifier [-All] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Show-WmsIdentifier** cmdlet displays the identification screen for the specified station.
The top line shown is the client name.
For a Windows MultiPoint Server station, the station-friendly name is used as the client name.
The bottom name is the system in which this session is hosted.

## EXAMPLES

### Example 1: Display the identification screen
```
PS C:\> Show-WmsIdentifier -SessionId 2
PS C:\> Show-WmsIdentifier -StationId 1
```

This example displays the ID screen for the specified session.
The first command displays the system that runs the remote desktop client.

The second command displays the local server name.

## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: IdentifyAll
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

### -SessionId
Specifies an array of MultiPoint session IDs.

```yaml
Type: UInt32[]
Parameter Sets: IdentifyBySession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StationId
Specifies an array of MultiPoint station IDs.

```yaml
Type: UInt32[]
Parameter Sets: IdentifyByStation
Aliases:

Required: True
Position: Named
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

[Hide-WmsIdentifier](./Hide-WmsIdentifier.md)

