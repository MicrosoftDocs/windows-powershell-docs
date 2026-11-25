---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/disable-sbecbcd?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-SbecBcd
---

# Disable-SbecBcd

## SYNOPSIS
Disables the event forwarding mode in BCD settings.

## SYNTAX

### Offline
```
Disable-SbecBcd -Path <String[]> [-Id <String>] [-DismLogPath <String>] [<CommonParameters>]
```

### Online
```
Disable-SbecBcd -ComputerName <String[]> [-Credential <PSCredential>] [-Id <String>] [<CommonParameters>]
```

### OnlineSession
```
Disable-SbecBcd -Session <PSSession[]> [-Id <String>] [<CommonParameters>]
```

### Local
```
Disable-SbecBcd [-Local] [-BcdStore <String>] [-Id <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SbecBcd** cmdlet disables the Boot Configuration Data (BCD) */event* flag.
This operation has no effect on the current connections; you must reboot the computer for the settings to take effect.

You can apply these changes to the local computer, to a remote computer, or to an offline disk image.

To operate on a local computer, specify the *Local* parameter.
Enabling forwarding on the computer that runs the Collector service makes sense only if it sends the data to a Collector on a different computer.
Otherwise, the in-kernel module is not able to connect to the Collector.
However, you can copy the PowerShell BootEventCollector module to the other computers, where you can use it for local configuration.

To operate on a remote computer, specify either the *ComputerName* or *Session* parameter.
Windows PowerShell remoting is used to perform the remote operations.

To operate on an offline (WIM or VHD) image, use the *Path* parameter.
WIM images do not normally contain the BCD files, and there is rarely a need to replace them there.
Instead, Windows Setup creates the BCD settings when it extracts the image from WIM to the hard drive.

## EXAMPLES

### Example 1: Disable BCD
```
PS C:\> Disable-SbecBcd -Session $MyPSSession
```

This command disables the BCD settings on a remote session.

## PARAMETERS

### -BcdStore
Specifies the full path of the BCD store.

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

### -Id
Specifies the ID of the entry to disable, without the curly braces.

The BCD settings may contain entries for multiple boot images (when a computer has multiple operating system versions installed).
When the settings for an operating system other than the currently running one (or the default operating system in an offline image) must be modified, you can use this parameter to select the entry.

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

### -Local
Indicates that this operation occurs on the local computer.
This mode also allows the extra control over the BCD store of where the settings are applied.

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

[Enable-SbecBcd](./Enable-SbecBcd.md)

[Enable-SbecBootImage](./Enable-SbecBootImage.md)

[Enable-SbecWdsBcd](./Enable-SbecWdsBcd.md)

