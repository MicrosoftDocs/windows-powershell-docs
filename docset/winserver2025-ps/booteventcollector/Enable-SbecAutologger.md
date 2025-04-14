---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/enable-sbecautologger?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-SbecAutologger
---

# Enable-SbecAutologger

## SYNOPSIS
Enables the forwarding of the events to the Setup and Boot Event Collector in the AutoLogger settings.

## SYNTAX

### Offline
```
Enable-SbecAutologger -Path <String[]> [-Logger <String[]>] [-PermLogger <String[]>] [-NoDefaultLoggers]
 [-ForceLogger] [-DismLogPath <String>] [<CommonParameters>]
```

### Online
```
Enable-SbecAutologger -ComputerName <String[]> [-Credential <PSCredential>] [-Logger <String[]>]
 [-PermLogger <String[]>] [-NoDefaultLoggers] [-ForceLogger] [<CommonParameters>]
```

### OnlineSession
```
Enable-SbecAutologger -Session <PSSession[]> [-Logger <String[]>] [-PermLogger <String[]>] [-NoDefaultLoggers]
 [-ForceLogger] [<CommonParameters>]
```

### Local
```
Enable-SbecAutologger [-Local] [-SystemHive <String>] [-ControlSet <String>] [-Logger <String[]>]
 [-PermLogger <String[]>] [-NoDefaultLoggers] [-ForceLogger] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SbecAutologger** cmdlet enables the forwarding of the events to the Setup and Boot Event Collector in the AutoLogger settings in the registry.
This operation has no immediate effect on the currently running log sessions; it takes effect after the operating system reboots and the AutoLogger service restarts the log sessions.

The changes can be applied to the local computer, to a remote computer, or to an offline disk image.

To operate on a local computer, specify the *Local* parameter.
Enabling forwarding on the computer that runs the Collector service makes sense only if it sends the data to a Collector on a different computer.
Otherwise, the in-kernel module is not able to connect to the Collector.
However, you can copy the PowerShell BootEventCollector module to the other computers, where you can use it for local configuration.

To operate on a remote computer, specify either the *ComputerName* or *Session* parameter.
Windows PowerShell remoting is used to perform the remote operations.

To operate on an offline (WIM or VHD) image, use the *Path* parameter.

This operation configures the event log session NT Kernel Logger (creating it if it does not exist) and, if present, EventLog-System and SetupPlatform to send events to the Boot Event Collector.
You can configure other log sessions by specifying the *Logger* or *PermLogger* parameter.

By default for the sessions NT Kernel Logger and EventLog-System, or when using the *Logger* parameter, the event log sessions are configured in such a manner that the event forwarding from them to the Collector becomes automatically disabled once the computer completes the boot sequence and the logging subsystem on it becomes fully functional.
To let a session forward the events all the time, as is done by default for the session SetupPlatform, use the *PermLogger* parameter.

You can enable forwarding only for the sessions in the real-time mode (as opposed to writing to a file), so by default the file-based sessions are left unchanged.
You can use the *ForceLogger* parameter to change such sessions to the real-time mode and enable forwarding.

This command also configures the Debug Print filter registry settings to pass, at minimum, Bugcheck messages for a system crash.

You must enable **both** AutoLogger and BCD settings to forward events to the Boot Event Collector.

## EXAMPLES

### Example 1: Enable AutoLogger on a computer
```
PS C:\> Enable-SbecAutologger -ComputerName "Server01"
```

This command enables AutoLogger settings on the computer named Server01.

### Example 2: Enable AutoLogger for network setup images
```
PS C:\> Enable-SbecAutologger -Path "boot.wim","install.wim" -ForceLogger
```

This command configures the AutoLogger settings in the two images used for network-based setup, and forces the switch of the SetupPlatform session from the file destination to the event collector destination.

### Example 3: Enable AutoLogger in a VHD image
```
PS C:\> Enable-SbecAutologger -Path "NanoServer.vhd" -Logger "Microsoft-Windows-Setup" -ForceLogger
```

This command configures the AutoLogger in a VHD image, and switches the log session of the post-install setup (as used in Windows Nano Server) to the Boot Event Collector destination.

## PARAMETERS

### -ComputerName
Specifies the names of the computers on which you want to perform the operation.
You can specify a fully qualified domain name (FQDN), a NetBIOS name, or an IP address for each computer.
For more information, see [Invoke-CimMethod](https://go.microsoft.com/fwlink/?LinkId=808801) on TechNet.

```yaml
Type: String[]
Parameter Sets: Online
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ControlSet
Specifies the control set key for the registry path.

```yaml
Type: String
Parameter Sets: Local
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user account that has permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential
Parameter Sets: Online
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DismLogPath
Specifies the path of the file for the Deployment Image Servicing and Management (DISM) log when mounting images.

```yaml
Type: String
Parameter Sets: Offline
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForceLogger
Forces the file-based AutoLogger sessions to real-time mode before enabling event forwading for them.
Without this switch, they remain unchanged.

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

### -Local
Indicates to perform this operation on the local computer.
This mode enables control over the registry path of where settings are applied.

```yaml
Type: SwitchParameter
Parameter Sets: Local
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Logger
Specifies the AutoLogger sessions for which to enable forwarding.
The forwarding for these sessions is automatically disabled after the operating system starts.
Specifying a session explicitly in *Logger* or *PermLogger* overrides its defaults.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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
Parameter Sets: Offline
Aliases:

Required: True
Position: Named
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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session
Specifies the **PSSession** objects connected to the remote target computers.
Enter a session object, such as the output of **Get-PSSession** or **New-PSSession**, or an array of these objects.

```yaml
Type: PSSession[]
Parameter Sets: OnlineSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SystemHive
Specifies the full path to the system hive for the registry.

```yaml
Type: String
Parameter Sets: Local
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Disable-SbecAutologger](./Disable-SbecAutologger.md)

[Disable-SbecBcd](./Disable-SbecBcd.md)

[Enable-SbecBcd](./Enable-SbecBcd.md)

[Enable-SbecBootImage](./Enable-SbecBootImage.md)

