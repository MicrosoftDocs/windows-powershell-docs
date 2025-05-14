---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: RemoteDesktop.psm1-help.xml
Module Name: RemoteDesktop
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/RemoteDesktop/get-rdpersonalvirtualdesktoppatchschedule?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RDPersonalVirtualDesktopPatchSchedule
---

# Get-RDPersonalVirtualDesktopPatchSchedule

## SYNOPSIS
Gets a patch schedule for a virtual desktop.

## SYNTAX

```
Get-RDPersonalVirtualDesktopPatchSchedule [[-VirtualDesktopName] <String>] [[-ID] <String>]
 [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RDPersonalVirtualDesktopPatchSchedule** cmdlet gets patch schedule details for a personal virtual desktop.

## EXAMPLES

### Example1: Get the patch schedule for all virtual desktops
```
PS C:\> Get-RDPersonalVirtualDesktopPatchSchedule
```

This command gets the patch schedule for all virtual desktops on the local computer.

### Example 2: Get a patch schedule by using an ID
```
PS C:\> Get-RDPersonalVirtualDesktopPatchSchedule -ID "{58E69A71-AFC9-49A6-81B9-494DA20216AC}"
```

This command gets the patch schedule that has the ID 58E69A71-AFC9-49A6-81B9-494DA20216AC.

### Example 3: Get a patch schedule by using a virtual desktop name
```
PS C:\> Get-RDPersonalVirtualDesktopPatchSchedule -VirtualDesktopName "RDS-WKS-A27"
```

This command gets the patch schedule for the virtual desktop named RDS-WKS-A27.

## PARAMETERS

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

### -ID
Specifies the ID of a patch schedule.
The ID of a patch schedule is a system-assigned GUID.

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
If you do not specify a value for this parameter, the cmdlet returns patch schedules for all personal virtual desktops.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object
VirtualDesktopName: Name of virtual desktop
Context: Opaque binary data associated with the patch schedule
Deadline: System uses this to prioritize patches.
The patch with the earliest deadline has the highest priority.
StartTime : This is the earliest the patch can be started
EndTime : This is the latest the patch can be started
ID : Unique identifier of the patch schedule
Label : A string that describes the purpose of the patch
Plugin : Plugin that created the patch schedule
PatchStatus  :
- RDV_TASK_STATUS_UNKNOWN.
(Not used by task agent.)
- RDV_TASK_STATUS_SEARCHING.
Searching for applicable tasks.
- RDV_TASK_STATUS_DOWNLOADING.
Downloading tasks.
- RDV_TASK_STATUS_APPLYING.
Executing tasks.
- RDV_TASK_STATUS_REBOOTING.
Rebooting after performing tasks.
Rebooting after performing tasks.
- RDV_TASK_STATUS_REBOOTED.
Rebooted complete after performing tasks.
- RDV_TASK_STATUS_SUCCESS.
Task completed successfully.
- RDV_TASK_STATUS_FAILED.
Task failed.
- RDV_TASK_STATUS_TIMEOUT.
Task did not end in time (not used by task agent).

## NOTES

## RELATED LINKS

[Set-RDPersonalVirtualDesktopPatchSchedule](./Set-RDPersonalVirtualDesktopPatchSchedule.md)

[New-RDPersonalVirtualDesktopPatchSchedule](./New-RDPersonalVirtualDesktopPatchSchedule.md)

[Remove-RDPersonalVirtualDesktopPatchSchedule](./Remove-RDPersonalVirtualDesktopPatchSchedule.md)

