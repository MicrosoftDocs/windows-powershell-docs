---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/enable-sbecbootimage?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-SbecBootImage
---

# Enable-SbecBootImage

## SYNOPSIS
Enables AutoLogger settings in offline WinPE Setup images.

## SYNTAX

```
Enable-SbecBootImage [-Path] <String[]> [[-Logger] <String[]>] [[-PermLogger] <String[]>] [-NoDefaultLoggers]
 [[-DismLogPath] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SbecBootImage** cmdlet enables the AutoLogger settings and creates the Winpeshl.ini files in offline WinPE Setup images to forward events to the Setup and Boot Event Collector.

The default event log sessions that are configured for sending events to the Boot Event Collector are NT Kernel Logger, EventLog-System, and SetupPlatform.
You can configure other loggers with the parameters *Logger* and *PermLogger*.
Loggers are always switched to real-time mode, regardless of whether they previously wrote to a file.

The AutoLogger settings enable event forwarding during the first stage of Setup when it boots from the WinPE image.
The Winpeshl.ini files facilitate the configuration of events on the HDD image through Unattend.xml.

## EXAMPLES

### Example 1: Enable Boot Event Collector in a WIM image
```
PS C:\> Enable-SbecBootImage -Path "C:\Images\Boot.wim"
```

This command enables the Boot Event Collector for the Boot.wim image.

## PARAMETERS

### -DismLogPath
Specifies the path of the Deployment Image Servicing and Management (DISM) log file to use when mounting images.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Logger
Specifies the AutoLogger sessions for which to enable forwarding.
The forwarding on these sessions auto-disables after the operating system starts.
Specifying a session explicitly in *Logger* or *PermLogger* overrides the defaults for it.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoDefaultLoggers
Indicates that this operation does not automatically add the default set of logger sessions.

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

### -Path
Specifies an array of full paths to the offline Windows image (WIM or VHD) files to which to apply the settings.
If a WIM file contains multiple images, all of them are modified.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PermLogger
Specifies the AutoLogger sessions for which to enable forwarding.
The forwarding on these sessions remains enabled after the operating system starts.
Specifying a session explicitly in *Logger* or *PermLogger* overrides the defaults for it.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.

## OUTPUTS

### None.

## NOTES

## RELATED LINKS

[Disable-SbecAutologger](./Disable-SbecAutologger.md)

[Enable-SbecAutologger](./Enable-SbecAutologger.md)

[Enable-SbecWdsBcd](./Enable-SbecWdsBcd.md)

[New-SbecUnattendFragment](./New-SbecUnattendFragment.md)

