---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Policy.cdxml-help.xml
Module Name: StorageQoS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storageqos/set-storageqospolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-StorageQosPolicy
---

# Set-StorageQosPolicy

## SYNOPSIS
Modifies an existing Storage QoS policy.

## SYNTAX

### Name (Default)
```
Set-StorageQosPolicy -Name <String[]> [[-NewName] <String>] [[-MaximumIops] <UInt64>] [[-MinimumIops] <UInt64>]
 [[-MaximumIOBandwidth] <UInt64>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Id
```
Set-StorageQosPolicy -PolicyId <Guid[]> [[-NewName] <String>] [[-MaximumIops] <UInt64>]
 [[-MinimumIops] <UInt64>] [[-MaximumIOBandwidth] <UInt64>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-StorageQosPolicy -InputObject <CimInstance[]> [[-NewName] <String>] [[-MaximumIops] <UInt64>]
 [[-MinimumIops] <UInt64>] [[-MaximumIOBandwidth] <UInt64>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-StorageQosPolicy** cmdlet modifies an existing Storage Quality of Service (Storage QoS) policy.

For more information about Storage QoS, see Storage Quality of Servicehttps://technet.microsoft.com/en-us/library/Mt126108 (https://technet.microsoft.com/en-us/library/Mt126108).

## EXAMPLES

### Example 1: Increase the IOPS limit on a policy
```
PS C:\>
Get-StorageQosPolicy -Name "Policy1" | Set-StorageQosPolicy -MaximumIops 200
```

This command increases the IOPS limit on a policy named Policy01 to 200 8KB-normalized IOPS.

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

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaximumIOBandwidth
Specifies the bandwidth limit for the policy, in bytes per second.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MinimumIops
Specifies the throughput reservation for the policy, in 8KB-normalized IOPS.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the policy to be modified.
Accepts wildcard patterns.

```yaml
Type: String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewName
Specifies a new name for the policy.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -PolicyId
Specifies the policy ID of the policy to be modified.

```yaml
Type: Guid[]
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-StorageQoSFlow](./Get-StorageQoSFlow.md)

[Get-StorageQosPolicy](./Get-StorageQosPolicy.md)

[Get-StorageQosVolume](./Get-StorageQosVolume.md)

[New-StorageQosPolicy](./New-StorageQosPolicy.md)

[Remove-StorageQosPolicy](./Remove-StorageQosPolicy.md)

