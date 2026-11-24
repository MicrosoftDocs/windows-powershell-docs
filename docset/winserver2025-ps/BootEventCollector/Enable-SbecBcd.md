---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/enable-sbecbcd?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-SbecBcd
---

# Enable-SbecBcd

## SYNOPSIS
Enables and configures the event forwarding mode in the BCD settings.

## SYNTAX

### Offline
```
Enable-SbecBcd -Path <String[]> -CollectorIp <String> -CollectorPort <String> -Key <String> [-Id <String>]
 [-BusParameters <String>] [-DismLogPath <String>] [<CommonParameters>]
```

### Online
```
Enable-SbecBcd -ComputerName <String[]> [-Credential <PSCredential>] -CollectorIp <String>
 -CollectorPort <String> -Key <String> [-Id <String>] [-BusParameters <String>] [<CommonParameters>]
```

### OnlineSession
```
Enable-SbecBcd -Session <PSSession[]> -CollectorIp <String> -CollectorPort <String> -Key <String>
 [-Id <String>] [-BusParameters <String>] [<CommonParameters>]
```

### Local
```
Enable-SbecBcd [-Local] [-BcdStore <String>] [-CreateEventSettings] -CollectorIp <String>
 -CollectorPort <String> -Key <String> [-Id <String>] [-BusParameters <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SbecBcd** cmdlet configures the Setup and Boot Event Collector settings in the BCD.
This enables the */event* flag, and sets the collector host IP address, port, and the encryption key in */eventsettings* in Boot Configuration Data (BCD).

This operation has no immediate effect on the current connections; it takes effect after the operating system reboots.

The changes can be applied to the local computer, to a remote computer, or to an offline disk image.

To operate on a local computer, specify the *Local* parameter.
Enabling forwarding on the computer that runs the Collector service makes sense only if it sends the data to a Collector on a different computer.
Otherwise, the in-kernel module is not able to connect to the Collector.
However, you can copy the PowerShell BootEventCollector module to the other computers, where you can use it for local configuration.

To operate on a remote computer, specify either the *ComputerName* or *Session* parameter.
Windows PowerShell remoting is used to perform the remote operations.

To operate on an offline (WIM or VHD) image, use the *Path* parameter.
WIM images do not normally contain the BCD files, there is rarely a requirement to place them there.
Instead, Windows Setup creates the BCD settings when it extracts the image from WIM onto the hard drive.

You must enable **both** AutoLogger and BCD settings to forward events to the Boot Event Collector.

## EXAMPLES

### Example 1: Configure the BCD settings for a remote session
```
PS C:\> Enable-SbecBcd -Session $MyPSSession -CollectorIp 192.168.1.1 -CollectorPort "50000" -Key "a.b.c.d"
```

This command configures the BCD settings for a remote session.

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

### -BusParameters
Specifies the bus parameters to use to select the NIC of the target computer for communication.
This value overrides the default choice of the first supported adapter.

This value applies to all the computers that use this image; it can be used only if the hardware of these computers is sufficiently homogeneous.

To find the value of bus parameters for a specific NIC on a machine, open Device Manager, and in Network Adapters select the desired device.
Right-click the device, select Properties, select the Details tab, and then select Location information.
It will display a string of the form PCI bus X, device Y, function Z.
The bus parameter to specify in this example is "X,Y,Z".

```yaml
Type: String
Parameter Sets: (All)
Aliases: BusParams

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectorIp
Specifies the IPv4 address of the host on which the Boot Event Collector is located.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectorPort
Specifies the port number (common for the target and collector).

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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

### -CreateEventSettings
Indicates that this operation explicitly creates the {eventsettings} key, which is required for the BCD files generated by WDS.

```yaml
Type: SwitchParameter
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

### -Id
Specifies the ID of the entry to modify, without the curly braces.
The BCD settings may contain entries for multiple boot images (when a computer has multiple operating system versions installed).
When the settings for another operating system than the currently booted one (or the default one in an offline image) must be modified, you can use this parameter to select the entry.

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

### -Key
Specifies the encryption key for the communication.
This value must match the key specified in the collector configuration for this target.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
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

### Name

## OUTPUTS

### Name

## NOTES

## RELATED LINKS

[Disable-SbecAutologger](./Disable-SbecAutologger.md)

[Disable-SbecBcd](./Disable-SbecBcd.md)

[Enable-SbecAutologger](./Enable-SbecAutologger.md)

[Enable-SbecBootImage](./Enable-SbecBootImage.md)

[Enable-SbecWdsBcd](./Enable-SbecWdsBcd.md)

