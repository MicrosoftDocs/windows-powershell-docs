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
title: Close-WmsSession
ms.reviewer:
ms.assetid: 299D02FC-4C37-44F9-863D-E2880EA533A3
---

# Close-WmsSession

## SYNOPSIS
Logs the user off of the specified session.

## SYNTAX

### CloseById
```
Close-WmsSession [-SessionId] <UInt32[]> [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CloseAll
```
Close-WmsSession [-All] [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Close-WmsSession** cmdlet logs off the user for the specified session.
Only administrators can close administrator sessions.
You cannot close the cmdlet's session.

## EXAMPLES

### Example 1: Close a session
```
PS C:\> Close-WmsSession -SessionId 3
```

This command closes the remote desktop session with ID 3.

## PARAMETERS

### -All
Indicates that this operation applies to all sessions on the target host.

```yaml
Type: SwitchParameter
Parameter Sets: CloseAll
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
Parameter Sets: CloseById
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

### None

## OUTPUTS

### None
This cmdlet returns an **ItemNotFoundException** if the specified session ID is not found.

## NOTES

## RELATED LINKS

[Disconnect-WmsSession](./Disconnect-WmsSession.md)

[Get-WmsSession](./Get-WmsSession.md)

[Lock-WmsSession](./Lock-WmsSession.md)

[Unlock-WmsSession](./Unlock-WmsSession.md)

