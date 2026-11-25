---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: QosVolume.cdxml-help.xml
Module Name: StorageQoS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storageqos/get-storageqosvolume?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageQosVolume
---

# Get-StorageQosVolume

## SYNOPSIS
Retrieves per-volume performance metrics on a volume that is monitored by Storage QoS.

## SYNTAX

```
Get-StorageQosVolume [-VolumeId <Guid[]>] [-Mountpoint <String[]>] [-Status <Status[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageQosVolume** cmdlet retrieves per-volume storage performance metrics on a volume that services Storage Quality of Service (Storage QoS) flows.
The metrics are throughput and latency averages, aggregated over all flows, and computed over a 5-minute rolling time interval.

Each file handle opened by a server that runs Hyper-V to a VHD or VHDX file is considered a flow.
If a virtual machine has two virtual hard disks attached, it has 1 flow to the file server cluster per file.
If a VHDX is shared with multiple virtual machines, it has 1 flow per virtual machine.

For more information about Storage QoS, see Storage Quality of Servicehttps://technet.microsoft.com/en-us/library/Mt126108 (https://technet.microsoft.com/en-us/library/Mt126108).

## EXAMPLES

### Example 1: Get QoS statistics for volumes at a specified path
```
PS C:\>
Get-StorageQosVolume -Mountpoint "C:\ClusterStorage\*"

Mountpoint                 IOPS Latency Status

----------                 ---- ------- ------

C:\ClusterStorage\Volume01\ 110  18.8469 Ok
```

This command gets QoS statistics for all volumes mounted under C:\ClusterStorage.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mountpoint
Specifies the file system path of a volume.

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

### -Status
Specifies the status of flows on a volume.
- Ok indicates the minimum IOPS are being met.
- InsufficientThroughput indicates IOPS are below minimum.

```yaml
Type: Status[]
Parameter Sets: (All)
Aliases:
Accepted values: Ok, InsufficientThroughput, LostCommunication

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

### -VolumeId
Specifies the ID of a volume that services flows.

```yaml
Type: Guid[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#MSFT_StorageQoSVolume
This cmdlet outputs a Common Information Model (CIM) object of type MSFT_StorageQoSVolumehttps://msdn.microsoft.com/en-us/library/mt164596(v=vs.85).aspx (https://msdn.microsoft.com/en-us/library/mt164596(v=vs.85).aspx).

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-StorageQoSFlow](./Get-StorageQoSFlow.md)

[Get-StorageQosPolicy](./Get-StorageQosPolicy.md)

[New-StorageQosPolicy](./New-StorageQosPolicy.md)

[Remove-StorageQosPolicy](./Remove-StorageQosPolicy.md)

[Set-StorageQosPolicy](./Set-StorageQosPolicy.md)

