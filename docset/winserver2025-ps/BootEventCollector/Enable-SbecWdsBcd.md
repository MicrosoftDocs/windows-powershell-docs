---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: BootEventCollector-help.xml
Module Name: BootEventCollector
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/booteventcollector/enable-sbecwdsbcd?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-SbecWdsBcd
---

# Enable-SbecWdsBcd

## SYNOPSIS
Enables the BCD settings in the offline boot images imported into the WDS server.

## SYNTAX

### BcdPath
```
Enable-SbecWdsBcd -BcdPath <String[]> -CollectorIp <String> -CollectorPort <UInt32> -Key <String>
 [-BusParameters <String>] [-WdsRoot <String>] [-SkipNotifyWds] [<CommonParameters>]
```

### WdsImage
```
Enable-SbecWdsBcd [-Image <Array>] -CollectorIp <String> -CollectorPort <UInt32> -Key <String>
 [-BusParameters <String>] [-WdsRoot <String>] [-SkipNotifyWds] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SbecWdsBcd** cmdlet enables the Boot Configuration Data (BCD) settings in the offline boot images imported into the WDS server.

After importing a boot image (such as one modified by **Enable-SbecBootImage**) into Windows Deployment Services (WDS), WDS automatically generates the BCD configuration for it.
Then, the boot event support must be enabled in this configuration.
Because this BCD file is specially formatted, you must explicitly enable it.

Because WDS does not support the separate per-client BCD files, sharing of the same BCD files by the clients means that they must use the same secret key for the communication with the Boot Event Collector.
The workaround is to use the common key for the setup, that can be either always be specified in the collector configuration as the second common key for all computers, or can be added to the collector configuration for the computers that are about to be set up, and removed after the setup is complete.

After modifying the BCD files, the WDS service must be notified (or restarted), to let it pick up the modified files.
This cmdlet performs this notification unless instructed otherwise.

## EXAMPLES

### Example 1: Update boot images in WDS
```
PS C:\> Get-WdsBootImage | Enable-SbecWdsBcd -CollectorIp "192.168.1.1" -CollectorPort 50000 -Key "a.b.c.d"
```

This command applies to all the boot images in WDS.

### Example 2: Update a BCD file
```
PS C:\> Enable-SbecWdsBcd -BcdPath "c:\tmp\boot.wim.bcd" -CollectorIp "192.168.1.1" -CollectorPort 50000 -Key "a.b.c.d" -SkipNotifyWds
```

This command updates the settings on a BCD file copied from WDS.

## PARAMETERS

### -BcdPath
Specifies the explicit path of the per-image BCD file(s).

```yaml
Type: String[]
Parameter Sets: BcdPath
Aliases:

Required: True
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
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Image
Specifies the Windows Deployment Services (WDS) Boot Image object(s) obtained from **Get-WdsBootImage**.
You can also specify a manually constructed hash table instead of an object if it contains the Architecture and FileName properties.

```yaml
Type: Array
Parameter Sets: WdsImage
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -SkipNotifyWds
Indicates that this operation does not notify the WDS service about the changed files.

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

### -WdsRoot
Specifies the root of the WDS directory tree.
By default, this value is obtained from the path of the exported SMB share REMINST.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_WdsBootImage
This cmdlet takes as input the Windows Deployment Services (WDS) Boot Image object(s) obtained from **Get-WdsBootImage**.
You can also specify a manually constructed hash table instead of an object if it contains the Architecture and FileName properties.

## OUTPUTS

### None.

## NOTES

## RELATED LINKS

[Enable-SbecBcd](./Enable-SbecBcd.md)

[Enable-SbecBootImage](./Enable-SbecBootImage.md)

[New-SbecUnattendFragment](./New-SbecUnattendFragment.md)

