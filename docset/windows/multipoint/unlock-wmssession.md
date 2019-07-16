---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Unlock-WmsSession
ms.reviewer:
ms.assetid: A8D291D9-4EE4-4EE9-965F-D06D0C02BFAC
---

# Unlock-WmsSession

## SYNOPSIS
Unblocks a user for desktop use.

## SYNTAX

### UnlockById
```
Unlock-WmsSession [-SessionId] <UInt32[]> [-Server <String>] [<CommonParameters>]
```

### UnlockAll
```
Unlock-WmsSession [-All] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Unlock-WmsSession** cmdlet unblocks a user for desktop use.

## EXAMPLES

### Example 1: Unblock a station
```
PS C:\> Unlock-WmsSession -SessionId 3
```

This command unblocks a station.

Note: If a Multipoint Manager session is running, and the state of the sessions was Block All, the Multipoint Manager may block the station again.

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

### -SessionId
Specifies the session ID.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Close-WmsSession](./Close-WmsSession.md)

[Disconnect-WmsSession](./Disconnect-WmsSession.md)

[Get-WmsSession](./Get-WmsSession.md)

[Lock-WmsSession](./Lock-WmsSession.md)

