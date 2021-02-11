---
external help file: 
Module Name: RemoteDesktop
online version: 
schema: 2.0.0
title: Remove-RDRemoteApp
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: D11BFD30-01D9-4D2A-B92F-801712DAC13D
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Remove-RDRemoteApp

## SYNOPSIS
Removes a RemoteApp program.

## SYNTAX

```
Remove-RDRemoteApp [-CollectionName] <String> -Alias <String> [-ConnectionBroker <String>] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-RDRemoteApp** cmdlet removes a Windows Server 2012 RemoteApp program from a Remote Desktop deployment.

RemoteApp allows Remote Desktop Services (RDS) to run a program remotely that appears as if it runs locally on a client computer.
A RemoteApp program runs in its own resizable window and has its own entry on the taskbar.

When you remove a RemoteApp program, users can no longer use that program as part of a Remote Desktop deployment.
This cmdlet does not delete the program executable.

## EXAMPLES

### Example 1: Remove a RemoteApp program
```
PS C:\> Remove-RDRemoteApp -CollectionName "Session Collection" -Alias "Notepad"
```

This command removes a RemoteApp program that has the alias Notepad from the collection named Session Collection.

## PARAMETERS

### -Alias
Specifies the alias for a RemoteApp program to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CollectionName
Specifies the name of a virtual desktop collection or session collection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Performs the action without a confirmation message.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Get-RDRemoteApp](./Get-RDRemoteApp.md)

[New-RDRemoteApp](./New-RDRemoteApp.md)

[Set-RDRemoteApp](./Set-RDRemoteApp.md)

