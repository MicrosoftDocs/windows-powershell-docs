---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/publish-wmsdesktop?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-WmsDesktop
---

# Publish-WmsDesktop

## SYNOPSIS
Shares a desktop and optionally allows remote control of the desktop.

## SYNTAX

```
Publish-WmsDesktop [-SessionId] <UInt32> [-RemoteControl] [-MaxViewers <Int32>] [-Server <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Publish-WmsDesktop** cmdlet shares the specified session desktop, which makes it viewable by other sessions.
A published desktop can also optionally be remotely controlled.

## EXAMPLES

### Example 1: Publish a desktop
```
PS C:\> Publish-WmsDesktop -RemoteControl -MaxViewers 10 -SessionId 2 -TeacherName "PattiFuller"





Invitation string
```

This command shares the desktop of session 2 for viewing by up to 10 other sessions, and permits remote control of the desktop.

## PARAMETERS

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

### -MaxViewers
Specifies the maximum number of clients that can view the published desktop.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteControl
Indicates that the published desktop can be remotely controlled.

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
Specifies the session ID of the desktop to publish.

```yaml
Type: UInt32
Parameter Sets: (All)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.UInt32

### System.String

## OUTPUTS

### Microsoft.WindowsServerSolutions.MultipointServer.PowerShell.Commands.Library.WmsDesktop

## NOTES

## RELATED LINKS

[Show-WmsDesktop](./Show-WmsDesktop.md)

[Unpublish-WmsDesktop](./Unpublish-WmsDesktop.md)

