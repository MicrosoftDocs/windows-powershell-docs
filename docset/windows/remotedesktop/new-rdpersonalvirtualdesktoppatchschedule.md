---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: 
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: New-RDPersonalVirtualDesktopPatchSchedule
ms.reviewer:
ms.assetid: ECE5D121-F6DD-4EB5-B630-61C9A64A08A2
---

# New-RDPersonalVirtualDesktopPatchSchedule

## SYNOPSIS
Creates a patch schedule for a personal virtual desktop.

## SYNTAX

```
New-RDPersonalVirtualDesktopPatchSchedule [-VirtualDesktopName] <String> [[-ID] <String>] [[-Context] <Byte[]>]
 [[-Deadline] <DateTime>] [[-StartTime] <DateTime>] [[-EndTime] <DateTime>] [[-Label] <String>]
 [[-Plugin] <String>] [[-ConnectionBroker] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-RDPersonalVirtualDesktopPatchSchedule** cmdlet creates a patch schedule for a personal virtual desktop.

## EXAMPLES

### Example 1: Create a patch Schedule for a personal virtual desktop
```
PS C:\> New-RDPersonalVirtualDesktopPatchSchedule -VirtualDesktopName "RDS-WKS-A27"
```

This command creates a patch schedule for the personal virtual desktop named RDS-WKS-A27.

### Example 2: Create a new Patch Schedule for a Personal Virtual Desktop
```
PS C:\> New-RDPersonalVirtualDesktopPatchSchedule -VirtualDesktopName "RDS-WKS-A27" -ID "{58E69A71-AFC9-49A6-81B9-494DA20216AC}" -StartTime (Get-Date)
```

This command creates a patch schedule for the personal virtual desktop named RDS-WKS-A27.
The command specifies that the personal virtual desktop use the existing patch schedule that has the ID 58E69A71-AFC9-49A6-81B9-494DA20216AC.
The **StartTime** parameter specifies the current time as the earliest time by which to begin the patch operation.

## PARAMETERS

### -ConnectionBroker
Specifies the Remote Desktop Connection Broker (RD Connection Broker) server for a Remote Desktop deployment.
If you do not specify a value, the cmdlet uses the fully qualified domain name (FQDN) of the local computer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Context
Specifies an array of binary data that the program performing the patch operation uses.
This data is transparent to the user.

```yaml
Type: Byte[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deadline
Specifies a date and time by which the patch operation must be complete.
The server uses this value to prioritize the order in which patches are installed.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndTime
Specifies the latest date and time by which the patch operation must begin.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the ID of a patch schedule.
If you do not specify an ID, the system assigns an ID.

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

### -Label
Specifies a string that describes the purpose of the patch.
Add a user-friendly, descriptive string so that the patch is easy to distinguish from other, potentially similar patches.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Plugin
Specifies name for the program that installs the patches.
For example, Windows Update.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Specifies the earliest date and time by which to begin the patch operation.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDesktopName
Specifies the name of a person virtual desktop.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Object
VirtualDesktopName: Name of virtual desktop
Context: Opaque binary data associated with the patch schedule
Deadline: System uses this to prioritize patches.
The patch with the earliest deadline gets highest priority. 
StartTime : This is the earliest the patch can be started
EndTime : This is the latest the patch can be started
ID : Unique identifier of the patch schedule
Label : A string that describes the purpose of the patch
Plugin : Plugin that created the patch schedule
PatchStatus : 
 -- RDV_TASK_STATUS_UNKNOWN.
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

[Get-RDPersonalVirtualDesktopPatchSchedule](./Get-RDPersonalVirtualDesktopPatchSchedule.md)

[Set-RDPersonalVirtualDesktopPatchSchedule](./Set-RDPersonalVirtualDesktopPatchSchedule.md)

[Remove-RDPersonalVirtualDesktopPatchSchedule](./Remove-RDPersonalVirtualDesktopPatchSchedule.md)

