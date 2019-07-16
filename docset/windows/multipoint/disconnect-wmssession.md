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
title: Disconnect-WmsSession
ms.reviewer:
ms.assetid: FCB27786-1D95-4C7D-8D7E-C7C4A8D600FD
---

# Disconnect-WmsSession

## SYNOPSIS
Disconnects a session.

## SYNTAX

### DisconnectById
```
Disconnect-WmsSession [-SessionId] <UInt32[]> [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisconnectAll
```
Disconnect-WmsSession [-All] [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disconnect-WmsSession** cmdlet disconnects the specified session.
You cannot disconnect the cmdlet's process.

## EXAMPLES

### Example 1: Disconnect a session
```
PS C:\> Disconnect-WmsSession -SessionId 3
```

This command disconnects the session with the ID 3.


## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: DisconnectAll
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
Parameter Sets: DisconnectById
Aliases: 

Required: True
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### WmsSession

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Close-WmsSession](./Close-WmsSession.md)

[Get-WmsSession](./Get-WmsSession.md)

[Lock-WmsSession](./Lock-WmsSession.md)

[Unlock-WmsSession](./Unlock-WmsSession.md)

