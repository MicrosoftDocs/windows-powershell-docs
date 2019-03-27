---
external help file: Microsoft.HyperV.PowerShell.dll-Help.xml
Module Name: Hyper-V
online version: 
schema: 2.0.0
title: Set-VMHost
ms.author: kenwith
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 866A8586-BCBE-4C91-B50C-5017C1965942
---

# Set-VMHost

## SYNOPSIS
Configures a Hyper-V host.

## SYNTAX

```
Set-VMHost [[-ComputerName] <String[]>] [-MaximumStorageMigrations <UInt32>]
 [-MaximumVirtualMachineMigrations <UInt32>]
 [-VirtualMachineMigrationAuthenticationType <MigrationAuthenticationType>]
 [-UseAnyNetworkForMigration <Boolean>] [-VirtualMachineMigrationPerformanceOption <VMMigrationPerformance>]
 [-ResourceMeteringSaveInterval <TimeSpan>] [-VirtualHardDiskPath <String>] [-VirtualMachinePath <String>]
 [-MacAddressMaximum <String>] [-MacAddressMinimum <String>] [-FibreChannelWwnn <String>]
 [-FibreChannelWwpnMaximum <String>] [-FibreChannelWwpnMinimum <String>] [-NumaSpanningEnabled <Boolean>]
 [-EnableEnhancedSessionMode <Boolean>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMHost** cmdlet configures a Hyper-V host.

## EXAMPLES

### Example 1
```
PS C:\>Set-VMHost -MaximumVirtualMachineMigrations 10 -MaximumStorageMigrations 10
```

This example configures the local Hyper-V host to allow 10 simultaneous live migrations and storage migrations.

### Example 2
```
PS C:\>Set-VMHost -MacAddressMinimum 00155D020600 -MacAddressMaximum 00155D0206FF
```

This example configures a range of MAC addresses range for the local Hyper-V host.

### Example 3
```
PS C:\>Set-VMHost -UseAnyNetworkForMigration $true
```

This example enables the use of any network for incoming live migrations on the local Hyper-V host.

### Example 4
```
PS C:\>Set-VMHost -VirtualHardDiskPath "C:\Hyper-V\Virtual Hard Disks" -VirtualMachinePath "C:\Hyper-V\Configuration Files"
```

This example specifies new default locations for virtual hard disksand virtual machines on the local Hyper-V host.

### Example 5
```
PS C:\>Set-VMHost -FibreChannelWwnn C003FF0000FFFF00 -FibreChannelWwpnMinimum C003FF661D200000 -FibreChannelWwpnMaximum C003FF661D200000
```

This example configures Fibre Channel host settings on the local Hyper-V host.

### Example 6
```
PS C:\>Set-VMHost -NumaSpanningEnabled $false
```

This example disables NUMA spanning on the local Hyper-V host.

### Example 7
```
PS C:\>Set-VMHost -ResourceMeteringSaveInterval 01:30:00
```

This example configures the local Hyper-V host to save data that tracks resource consumption every hour and a half.

### Example 8
```
PS C:\>Set-VMHost -VirtualMachineMigrationAuthenticationType Kerberos
```

The example configures the local Hyper-V host to use Kerberos to authenticate incoming live migrations.

## PARAMETERS

### -ComputerName
Specifies one or more Hyper-V hosts to be configured.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer - use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: .
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableEnhancedSessionMode
Indicates whether users can use enhanced mode when they connect to virtual machines on this server by using Virtual Machine Connection.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FibreChannelWwnn
Specifies the default  value of the World Wide Node Name  on the Hyper-V host.

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

### -FibreChannelWwpnMaximum
Specifies the maximum value that can be used to generate World Wide Port Names on the Hyper-V host.
Use with FibreChannelWwpnMinimum to establish a range of WWPNs that the specified Hyper-V host can assign to virtual Fibre Channel adapters.

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

### -FibreChannelWwpnMinimum
Specifies the minimum value that can be used to generate the World Wide Port Names on the Hyper-V host.
Use with FibreChannelWwpnMaximum to establish a range of WWPNs that the specified Hyper-V host can assign to virtual Fibre Channel adapters.

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

### -MacAddressMaximum
Specifies the maximum MAC address using a valid hexadecimal value.
Use with MacAddressMinimum to establish a range of MAC addresses that the specified Hyper-V host can assign to virtual machines configured to receive dynamic MAC addresses.

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

### -MacAddressMinimum
Specifies the minimum MAC address using a valid hexadecimal value.
Use with MacAddressMaximum to establish a range of MAC addresses that the specified Hyper-V host can assign to virtual machines configured to receive dynamic MAC addresses.

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

### -MaximumStorageMigrations
Specifies the maximum number of storage migrations that can be performed at the same time on the Hyper-V host.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumVirtualMachineMigrations
Specifies the maximum number of  live migrations that can be performed at the same time on the Hyper-V host.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumaSpanningEnabled
Specifies whether virtual machines on the Hyper-V host can use resources from more than one NUMA node.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Specifies that a **Microsoft.HyperV.PowerShell.Host** is to be passed through to the pipeline representing the Hyper-V host to be configured.

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

### -ResourceMeteringSaveInterval
Specifies how often the Hyper-V host saves the data that tracks resource usage.
The range is a minimum of 1 hour to a maximum of 24 hours.
Time within that range can be specified using a format of hh:mm:ss, where hh indicates hours, mm indicates minutes, and ss indicates seconds.
You also can use a Timespan object to specify the interval.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseAnyNetworkForMigration
Specifies how networks are selected for incoming live migration traffic.
If set to **$TRUE**, any available network on the host can be used for this traffic.
If set to **$FALSE**, incoming live migration traffic is transmitted only on the networks specified in the **MigrationNetworks** property of the host.
The **Get-VMMigrationNetwork** returns the list of networks that can be used for migration traffic.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHardDiskPath
Specifies the default folder to store virtual hard disks on the Hyper-V host.

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

### -VirtualMachineMigrationAuthenticationType
Specifies the type of authentication to be used for live migrations.
Allowed values are **Kerberos** or **CredSSP**.

```yaml
Type: MigrationAuthenticationType
Parameter Sets: (All)
Aliases: 
Accepted values: CredSSP, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachineMigrationPerformanceOption
Specifies the performance option to use for live migration.
The acceptable values for this parameter are:

- Compression.
Compress data to speed up live migration on constrained networks. 
- SMBTransport.
Use server message block (SMB) to get the highest throughput possible.
- None.
Perform standard live migration.

```yaml
Type: VMMigrationPerformance
Parameter Sets: (All)
Aliases: 
Accepted values: TCPIP, Compression, SMB

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachinePath
Specifies the default folder to store virtual machine configuration files on the Hyper-V host.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

###  
None by default; **Microsoft.HyperV.PowerShell.Host** if **-PassThru** is specified.

## NOTES

## RELATED LINKS

