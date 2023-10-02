---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://learn.microsoft.com/powershell/module/failoverclusters/reset-clustervmmonitoredstate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Reset-ClusterVMMonitoredState

## SYNOPSIS
Resets the Application Critical state of a virtual machine, so that the virtual machine is no longer marked as being in a critical state in the cluster.

## SYNTAX

```
Reset-ClusterVMMonitoredState [[-VirtualMachine] <String>] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Reset-ClusterVMMonitoredState** cmdlet resets the Application Critical state of a virtual machine, so that the virtual machine is no longer marked as being in a critical state in the cluster.
Note: This cmdlet can only be run locally on the virtual machine or through Windows PowerShell® remoting to the virtual machine.

## EXAMPLES

### Example 1
```
PS C:\>Reset-ClusterVMMoniteredState
```

This example resets the state of the virtual machine and clears the critical state.

## PARAMETERS

### -InputObject
Specifies the cluster on which to run the cmdlet and the clustered virtual machine to reset.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualMachine
Specifies the name of the clustered virtual machine to reset.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-ClusterVMMonitoredItem](./Add-ClusterVMMonitoredItem.md)

[Get-ClusterVMMonitoredItem](./Get-ClusterVMMonitoredItem.md)

[Remove-ClusterVMMonitoredItem](./Remove-ClusterVMMonitoredItem.md)

