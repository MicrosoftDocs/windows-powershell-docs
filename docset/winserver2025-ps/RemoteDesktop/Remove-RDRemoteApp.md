---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/remove-rdremoteapp?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-RDRemoteApp
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
Forces the command to run without asking for user confirmation.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Null

## NOTES

## RELATED LINKS

[Get-RDRemoteApp](./Get-RDRemoteApp.md)

[New-RDRemoteApp](./New-RDRemoteApp.md)

[Set-RDRemoteApp](./Set-RDRemoteApp.md)

