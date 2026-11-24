---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Policy.psm1-help.xml
Module Name: StorageQoS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storageqos/get-storageqosflow?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageQoSFlow
---

# Get-StorageQoSFlow

## SYNOPSIS
Retrieves performance metrics on an I/O flow that is monitored by Storage QoS.

## SYNTAX

### Arguments
```
Get-StorageQoSFlow [[-FlowId] <Guid>] [[-InitiatorId] <String>] [[-FilePath] <String>] [[-VolumeId] <String>]
 [[-InitiatorName] <String>] [[-InitiatorNodeName] <String>] [[-StorageNodeName] <String>] [[-Status] <Status>]
 [-IncludeHidden] [-AsJob] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [<CommonParameters>]
```

### Object
```
Get-StorageQoSFlow [-Policy] <CimInstance> [-AsJob] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageQoSFlow** cmdlet retrieves performance metrics on an I/O flow that is monitored by Storage Quality of Service (Storage QoS).
The metrics are throughput and latency averages, computed over a 5-minute rolling time interval.

Each file handle opened by a server that runs Hyper-V to a VHD or VHDX file is considered a flow.
If a virtual machine has two virtual hard disks attached, it will have 1 flow to the file server cluster per file.
If a VHDX is shared with multiple virtual machines, it will have 1 flow per virtual machine.

For more information about Storage QoS, see Storage Quality of Service in Windows Server Technical Previewhttps://technet.microsoft.com/en-us/library/Mt126108 (https://technet.microsoft.com/en-us/library/Mt126108).

## EXAMPLES

### Example 1: Get information on an I/O flow
```
PS C:\>
Get-StorageQoSFlow -FilePath "C:\ClusterStorage\Volume01\TEST"

InitiatorName FilePath                       InitiatorIOPS InitiatorLatency InitiatorBandwidth PSComputerName

------------- --------                       ------------- ---------------- ------------------ --------------

storqosclient C:\ClusterStorage\Volume01\TEST 104           8.0921 ms        0.2 MB/s

storqosclient C:\ClusterStorage\Volume01\TEST 31            8.9741 ms        0.5 MB/s
```

This command gets information about all flow initiators accessing C:\ClusterStorage\Volume01\TEST.

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
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
Specifies the path of the file that a flow accesses.

```yaml
Type: String
Parameter Sets: Arguments
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FlowId
Specifies the GUID that identifies the flow.
This identifier is not unique across flow objects, because the same logical flow may be split across several volumes or storage nodes.

```yaml
Type: Guid
Parameter Sets: Arguments
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeHidden
Indicates that this cmdlet includes the default flow, which groups together all flows not governed by a policy.

```yaml
Type: SwitchParameter
Parameter Sets: Arguments
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiatorId
Identifies the virtual machine that is the initiator of the flow.

```yaml
Type: String
Parameter Sets: Arguments
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiatorName
Specifies the friendly name of the initiator.

```yaml
Type: String
Parameter Sets: Arguments
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiatorNodeName
Specifies the hostname of the node initiating the flow.

```yaml
Type: String
Parameter Sets: Arguments
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy
Specifies a policy for which to get associated flows.

```yaml
Type: CimInstance
Parameter Sets: Object
Aliases:

Required: True
Position: 9
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Status
Specifies the status of the flow.

- Ok indicates that the flow meets the minimum Input/Output Operations Per Second (IOPS).
- InsufficientThroughput indicates that the IOPS are below the minimum.

```yaml
Type: Status
Parameter Sets: Arguments
Aliases:
Accepted values: Ok, InsufficientThroughput, UnknownPolicyId, LostCommunication

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageNodeName
Specifies the hostname of the storage node servicing the flow.

```yaml
Type: String
Parameter Sets: Arguments
Aliases:

Required: False
Position: 6
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
Specifies the ID of a volume that the flow accesses.

```yaml
Type: String
Parameter Sets: Arguments
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-StorageQosPolicy](./Get-StorageQosPolicy.md)

[Get-StorageQosVolume](./Get-StorageQosVolume.md)

[New-StorageQosPolicy](./New-StorageQosPolicy.md)

[Remove-StorageQosPolicy](./Remove-StorageQosPolicy.md)

[Set-StorageQosPolicy](./Set-StorageQosPolicy.md)

