---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/disable-sbecautologger?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-SbecAutologger
---

# Disable-SbecAutologger

## SYNOPSIS
Disables the forwarding of events to the Setup and Boot Event Collector in the AutoLogger settings.

## SYNTAX

### Offline
```
Disable-SbecAutologger -Path <String[]> [-Logger <String[]>] [-NoDefaultLoggers] [-DismLogPath <String>]
 [<CommonParameters>]
```

### Online
```
Disable-SbecAutologger -ComputerName <String[]> [-Credential <PSCredential>] [-Logger <String[]>]
 [-NoDefaultLoggers] [<CommonParameters>]
```

### OnlineSession
```
Disable-SbecAutologger -Session <PSSession[]> [-Logger <String[]>] [-NoDefaultLoggers] [<CommonParameters>]
```

### Local
```
Disable-SbecAutologger [-Local] [-SystemHive <String>] [-ControlSet <String>] [-Logger <String[]>]
 [-NoDefaultLoggers] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SbecAutologger** cmdlet disables the forwarding of events to the Setup and Boot Event Collector in the AutoLogger settings in the registry.
This has no immediate effect on the currently running log sessions, but takes effect after the operating system reboots and the AutoLogger service restarts the log sessions.

The changes can be applied to the local computer, to a remote computer, or to an offline disk image.

To operate on a local computer, specify the *Local* parameter.
Enabling forwarding on the computer that runs the Collector service makes sense only if it sends the data to a Collector on a different computer.
Otherwise, the in-kernel module is not able to connect to the Collector.
However, you can copy the PowerShell BootEventCollector module to the other computers, where you can use it for local configuration.

To operate on a remote computer, specify either the *ComputerName* or *Session* parameter.
Windows PowerShell remoting is used to perform the remote operations.

To operate on an offline (WIM or VHD) image, use the *Path* parameter.

If you used the **Enable-SbecAutologger** cmdlet to convert some log sessions from file-based to real-time mode, this command undoes that conversion.

If **Enable-SbecAutologger** created the NT Kernel Logger session, that session is **not** deleted by **Disable-SbecAutologger**.
Only the forwarding of events from it to the Collector is disabled.

If the Debug Print filter was modified by **Enable-SbecAutologger**, the change is **not** undone by **Disable-SbecAutologger**.

## EXAMPLES

### Example 1: Disable the AutoLogger
```
PS C:\> Disable-SbecAutologger -ComputerName Server01
```

This command disables the AutoLogger settings on the computer named Server01.

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
This parameter is valid only when used with the *Local* parameter.

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
Specifies an array of AutoLogger sessions to disable.
Specify an asterisk (*) to disable the EVENTNET forwarding in all of the sessions defined in the registry.

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
Indicates this operation does not automatically add the default set of logger sessions (EventLog-System, NT Kernel Logger, and SetupPlatform) to those specified by the *Logger* parameter.

If the value of Logger is *, this parameter has no effect.

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
Specifies the list of full paths to the offline Windows image files (WIM or VHD) to which to apply the settings.
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

### -Session
Specifies the **PSSession** objects connected to the remote target computers.
Enter a session object, such as the output of the **Get-PSSession** or **New-PSSession** cmdlet, or an array of these objects.

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
Specifies the full path to the system hive for the registry path.

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

### None.

## OUTPUTS

### None.

## NOTES

## RELATED LINKS

[Disable-SbecBcd](./Disable-SbecBcd.md)

[Enable-SbecAutologger](./Enable-SbecAutologger.md)

[Enable-SbecBcd](./Enable-SbecBcd.md)

[Enable-SbecBootImage](./Enable-SbecBootImage.md)

