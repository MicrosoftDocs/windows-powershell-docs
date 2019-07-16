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
title: Enable-WmsScheduledUpdate
ms.reviewer:
ms.assetid: 7CB2803E-8BA5-4142-A04B-90EF6021BC95
---

# Enable-WmsScheduledUpdate

## SYNOPSIS
Enables scheduled updates while disk protection is enabled and in discard mode.

## SYNTAX

```
Enable-WmsScheduledUpdate [-AutomaticUpdateMode <EAutomaticUpdateMode>] [-HourToScheduleUpdates <UInt32>]
 [-CustomScript <String>] [-MaxTimeAllowedForCustomScript <UInt32>] [-ReturnState <EScheduleUpdateReturnState>]
 [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WmsScheduledUpdate** cmdlet enables the specified computer to periodically disable the disk protection feature so that scheduled updates can be applied.
After updates are applied, the disk protection feature is automatically re-enabled.

## EXAMPLES

### Example 1: Enable scheduled updates
```
PS C:\> Enable-WmsScheduledUpdate -Server "Sample.microsoft.com" -AutomaticUpdateMode WindowsOnly -HourToScheduleUpdates 3 -CustomScript "C:\MyApps\SampleApp.exe" -MaxTimeAllowedForCustomScript 30 -ReturnState PreviousState
IsScheduleUpdateEnabled       : True
AutomaticUpdateMode           : WindowsOnly
HourToScheduleUpdates         : 3
CustomScript                  : c:\myapps\sampleapp.exe
MaxTimeAllowedForCustomScript : 30
ReturnState                   : PreviousState
```

This command enables the computer Sample.microsoft.com to switch disk protection to passive mode (reboot) at 3 AM to apply any pending Windows updates and run the application SampleApp.exe.
The system then returns to the power/running state it was in before 3 AM.

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

## OUTPUTS

### scheduledUpdate
This cmdlet returns a structure containing the current configuration.

## NOTES

## RELATED LINKS

[Disable-WmsScheduledUpdate](./Disable-WmsScheduledUpdate.md)

[Get-WmsScheduledUpdate](./Get-WmsScheduledUpdate.md)

[Set-WmsScheduledUpdate](./Set-WmsScheduledUpdate.md)

