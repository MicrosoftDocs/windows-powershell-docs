---
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
online version: 
schema: 2.0.0
title: Add-WsusComputer
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 6CFD1224-CEC5-47D9-93F7-89B236146FF6
ms.author: kenwith
ms.reviewer: brianlic
---

# Add-WsusComputer

## SYNOPSIS
Adds a specified client computer, that is already registered to a WSUS server, to a specified target group.

## SYNTAX

```
Add-WsusComputer -Computer <WsusComputer> -TargetGroupName <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WsusComputer** cmdlet adds the specified computer to the specified target group on the local server or a specified server.
You can invoke this command by Piping in the results of the Get-WsusComputer cmdlet.
Calling the Get-WsusComputer cmdlet and piping the results into this cmdlet enables you to leverage the filtering capabilities of the Get-WsusComputer cmdlet in moving the desired computers to the specified target group.
The server used in the Get-WsusComputer cmdlet will also be used in this cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-WsusServer contoso | Get-WsusComputer -NameIncludes winvm | Add-WsusComputer -TargetGroupName "Windows Virtual Machines"
```

This example adds all computers with winvm in the name to the target group named Windows Virtual Machines on the server named contoso.

## PARAMETERS

### -Computer
Specifies the object that contains the client computer to be added.
This value is obtained by running the Get-WsusComputer cmdlet and piping the resulting WsusComputer object into this cmdlet.

```yaml
Type: WsusComputer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -TargetGroupName
Specifies the name of the computer target group for which to run this cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.UpdateServices.Commands.WsusComputer
WsusComputer

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-WsusComputer](./Get-WsusComputer.md)

[Get-WsusServer](./Get-WsusServer.md)

