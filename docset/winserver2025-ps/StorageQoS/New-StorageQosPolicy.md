---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Policy.psm1-help.xml
Module Name: StorageQoS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storageqos/new-storageqospolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-StorageQosPolicy
---

# New-StorageQosPolicy

## SYNOPSIS
Creates a Storage QoS policy.

## SYNTAX

### Arguments (Default)
```
New-StorageQosPolicy [[-PolicyId] <Guid>] [[-Name] <String>] [[-MaximumIops] <UInt64>]
 [[-MinimumIops] <UInt64>] [[-MaximumIOBandwidth] <UInt64>] [[-ParentPolicy] <CimInstance>]
 [[-PolicyType] <PolicyType>] [-AsJob] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Object
```
New-StorageQosPolicy [-Policy] <CimInstance> [-AsJob] [-CimSession <CimSession>] [-ThrottleLimit <Int32>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-StorageQoSPolicy** cmdlet creates a Storage Quality of Service (Storage QoS) policy that specifies the maximum and minimum throughput.

This cmdlet generates the ID of the policy that it creates, if the **PolicyId** parameter is not specified.

For more information about Storage QoS, see Storage Quality of Servicehttps://technet.microsoft.com/en-us/library/Mt126108 (https://technet.microsoft.com/en-us/library/Mt126108).

## EXAMPLES

### Example 1: Create a policy
```
PS C:\>New-StorageQosPolicy -Name "Policy01" -MaximumIops 100 -MinimumIops 10

Name    MinimumIops MaximumIops Status

----    ----------- ----------- ------

Policy01 10          100         Ok
```

This command creates a policy with a maximum of 100 8KB-normalized IOPS and a minimum of 10.

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

### -MaximumIOBandwidth
Specifies the bandwidth limit for the policy, in bytes per seconds.

```yaml
Type: UInt64
Parameter Sets: Arguments
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumIops
Specifies the throughput limit for the policy, in units of 8KB-normalized Input/Output Operations Per Second (IOPS).

Storage usage is measured in normalized IOPS.
This is a count of the storage input/output operations per second.
Any IO that is 8KB or smaller is considered as one normalized IOPS.
Any IO that is larger than 8KB is treated as multiple normalized IOPS.
For example, a 256KB request is treated as 32 normalized IOPS.

```yaml
Type: UInt64
Parameter Sets: Arguments
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumIops
Specifies the throughput reservation for the policy, in 8KB-normalized IOPS.

```yaml
Type: UInt64
Parameter Sets: Arguments
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the policy to create.

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

### -ParentPolicy
Specifies the parent policy of the policy that this cmdlet creates.
The object must specify the **PolicyId** field.

```yaml
Type: CimInstance
Parameter Sets: Arguments
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy
Specifies the storage QoS Policy that this cmdlet creates in the policy manager.
Must be a valid MSFT_StorageQoSPolicy instance that specifies **MaximumIops** and **MinimumIops**.

```yaml
Type: CimInstance
Parameter Sets: Object
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PolicyId
Specifies the GUID of the policy that this cmdlet creates.

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

### -PolicyType
Specifies the type of the policy that this cmdlet creates.
The acceptable values for this parameter are: Aggregated and Dedicated.
In an aggregated policy, the maximum and minimum throughputs apply to the aggregate throughput of all initiators.
In a dedicated policy, the minimum and maximum throughputs apply to each initiator individually.

```yaml
Type: PolicyType
Parameter Sets: Arguments
Aliases:
Accepted values: Aggregated, Dedicated

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-StorageQoSFlow](./Get-StorageQoSFlow.md)

[Get-StorageQosPolicy](./Get-StorageQosPolicy.md)

[Get-StorageQosVolume](./Get-StorageQosVolume.md)

[Remove-StorageQosPolicy](./Remove-StorageQosPolicy.md)

[Set-StorageQosPolicy](./Set-StorageQosPolicy.md)

