---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/enable-physicaldiskidentification?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PhysicalDiskIdentification
---

# Enable-PhysicalDiskIdentification

## SYNOPSIS
Enables the identification LED on the specified physical disk.

## SYNTAX

### ByName (Default)
```
Enable-PhysicalDiskIdentification [-FriendlyName] <String> [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByUniqueId
```
Enable-PhysicalDiskIdentification -UniqueId <String> [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByInputObject
```
Enable-PhysicalDiskIdentification -InputObject <CimInstance[]> [-CimSession <CimSession>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-PhysicalDiskIdentification** cmdlet enables the identification LED on the specified physical disk.
The LED is typically used for visual identification of the location of a physical disk in an enclosure for removal and replacement operations.
This cmdlet requires a storage enclosure that supports SCSI Enclosure Services (SES).

## EXAMPLES

### Example 1: Enable the identification LED on all physical disks with certain FriendlyName
```powershell
PS C:\> Enable-PhysicalDiskIdentification -FriendlyName ST2000LM015-2E8174
```

This example enables the identification LED on all physical disks with *FriendlyName* ST2000LM015-2E8174.

### Example 2: Enable the identification LED on physical disk with certain UniqueId
```powershell
sPS C:\> Enable-PhysicalDiskIndication -UniqueId 5000C500B1DA75F6
```

This example enables the identification LED physical disk with *UniqueId* 5000C500B1DA75F6.

### Example 3: Enable the identification LED on all disks that are not healthy
```powershell
PS C:\>Get-PhysicalDisk | Where-Object -FilterScript { $_.HealthStatus -Ne "healthy" } | Enable-PhysicalDiskIndication
```

This example gets all physical disks with a health status that is not Healthy, and pipes the disks to the **Enable-PhysicalDiskIndication** cmdlet, enabling the LEDs on the disks, if supported by the drive enclosure.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FriendlyName
Specifies the friendly name of the disk on which to enable the identification LED.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.
```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UniqueId
Specifies an ID used to uniquely identify a Disk object in the system.
The ID persists through restarts.

```yaml
Type: String
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
You can pipe a **Disk** object to the *InputObject* parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_PhysicalDisk
This cmdlet outputs an object that represents the physical disk for which you enabled the identification LED.

## NOTES
* The **Microsoft.Management.Infrastructure.CimInstance** object is a wrapper class that displays Windows Management Instrumentation (WMI) objects. The path after the pound sign (#) provides the namespace and class name for the underlying WMI object.
* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Disable-PhysicalDiskIdentification](./Disable-PhysicalDiskIdentification.md)
