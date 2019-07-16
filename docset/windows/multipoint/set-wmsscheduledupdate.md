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
title: Set-WmsScheduledUpdate
ms.reviewer:
ms.assetid: C867D455-D830-4C1C-A0C8-40A9C2912674
---

# Set-WmsScheduledUpdate

## SYNOPSIS
Sets the schedule for Windows updates and custom maintenance scripts.

## SYNTAX

```
Set-WmsScheduledUpdate [-AutomaticUpdateMode <EAutomaticUpdateMode>] [-HourToScheduleUpdates <UInt32>]
 [-CustomScript <String>] [-MaxTimeAllowedForCustomScript <UInt32>] [-ReturnState <EScheduleUpdateReturnState>]
 [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WmsScheduledUpdate** cmdlet sets the schedule for Windows updates and custom maintenance scripts for a computer running MultiPoint Server with disk protection enabled and configured for discard mode.

## EXAMPLES

### Example 1: Enable Windows updates on MultiPoint Server
```
PS C:\> Set-WmsScheduledUpdate -AutomaticUpdateMode WindowsOnly -HourToScheduleUpdates 2 -ReturnState PreviousState
```

This command configures the local MultiPoint Server to check for available Windows updates at 2:00 AM, apply the updates, and return the computer to the power state it was in before updates were applied.
To update the MultiPoint Server, the command performs these operations: 

- Restart the computer to disable disk protection.
- Apply pending Windows updates.
- Restart the computer to enable disk protection and to return it to the previous power state.

## PARAMETERS

### -AutomaticUpdateMode
Specifies the type of automatic updates to process.
The acceptable values for this parameter are:

- None
- WindowsOnly
- WindowsAndOtherPrograms

```yaml
Type: EAutomaticUpdateMode
Parameter Sets: (All)
Aliases: 
Accepted values: None, WindowsOnly, WindowsAndOtherPrograms

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomScript
Specifies the full path of a user-supplied command to run at update time.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HourToScheduleUpdates
Specifies the hour at which to run automatic updates.
The acceptable values for this parameter are: 0-23.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxTimeAllowedForCustomScript
Specifies the maximum amount of time that the custom script is allowed to run.
After this amount of time expires, the process is stopped and the system is restarted to re-enable disk protection.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReturnState
Specifies the state in which to place the computer after updates are complete.
The acceptable values for this parameter are: Shutdown and PreviousState.

```yaml
Type: EScheduleUpdateReturnState
Parameter Sets: (All)
Aliases: 
Accepted values: Shutdown, PreviousState

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Disable-WmsScheduledUpdate](./Disable-WmsScheduledUpdate.md)

[Enable-WmsScheduledUpdate](./Enable-WmsScheduledUpdate.md)

[Get-WmsScheduledUpdate](./Get-WmsScheduledUpdate.md)

