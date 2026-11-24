---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/remove-rdpersonalvirtualdesktoppatchschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-RDPersonalVirtualDesktopPatchSchedule
---

# Remove-RDPersonalVirtualDesktopPatchSchedule

## SYNOPSIS
Removes a patch schedule from a personal virtual desktop.

## SYNTAX

```
Remove-RDPersonalVirtualDesktopPatchSchedule [[-VirtualDesktopName] <String>] [[-ID] <String>]
 [[-ConnectionBroker] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-RDPersonalVirtualDesktopPatchSchedule** cmdlet removes a patch schedule from a personal virtual desktop.

## EXAMPLES

### Example 1: Remove a patch schedule by using an ID
```
PS C:\> Remove-RDPersonalVirtualDesktopPatchSchedule -ID "{58E69A71-AFC9-49A6-81B9-494DA20216AC}"
```

This command removes the path schedule that has the ID "58E69A71-AFC9-49A6-81B9-494DA20216AC" from the local computer.

### Example 2: Remove a patch schedule without a confirmation prompt
```
PS C:\> Remove-RDPersonalVirtualDesktopPatchSchedule -ID "{58E69A71-AFC9-49A6-81B9-494DA20216AC}" -Force
```

This command removes the path schedule that has the ID "58E69A71-AFC9-49A6-81B9-494DA20216AC" from the local computer.
The **Force** parameter specifies that the server removes the patch schedule without prompting you for confirmation.

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

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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

### -ID
Specifies the ID of a patch schedule.
If you do not specify a value, the cmdlet removes all patch schedules.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopName
Specifies the name of a person virtual desktop.
If you do not specify a value, the cmdlet removes patch schedules for all personal virtual desktops.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
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

[Get-RDPersonalVirtualDesktopPatchSchedule](./Get-RDPersonalVirtualDesktopPatchSchedule.md)

[Set-RDPersonalVirtualDesktopPatchSchedule](./Set-RDPersonalVirtualDesktopPatchSchedule.md)

[New-RDPersonalVirtualDesktopPatchSchedule](./New-RDPersonalVirtualDesktopPatchSchedule.md)

