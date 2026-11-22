---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/unlock-wmsusbstorage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Unlock-WmsUsbStorage
---

# Unlock-WmsUsbStorage

## SYNOPSIS
Unlocks USB storage.

## SYNTAX

### UnlockById
```
Unlock-WmsUsbStorage [-StationId] <UInt32[]> [-Server <String>] [<CommonParameters>]
```

### UnlockAll
```
Unlock-WmsUsbStorage [-All] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Unlock-WmsUsbStorage** cmdlet enables USB storage on the specified station or stations.
If a USB storage device is hidden, this cmdlet makes it available.

## EXAMPLES

### Example 1: Unblock USB storage devices
```
PS C:\> Unlock-WmsUsbStorage -StationId 2
```

This command unblocks USB storage devices on the specified station.

## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: UnlockAll
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
Parameter Sets: UnlockById
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

[Lock-WmsUsbStorage](./Lock-WmsUsbStorage.md)

