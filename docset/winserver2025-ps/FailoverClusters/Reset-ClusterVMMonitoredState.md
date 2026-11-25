---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/reset-clustervmmonitoredstate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Reset-ClusterVMMonitoredState
---

# Reset-ClusterVMMonitoredState

## SYNOPSIS
Resets the Application Critical state of a virtual machine, so that the virtual machine is no longer
marked as being in a critical state in the cluster.

## SYNTAX

```
Reset-ClusterVMMonitoredState [-Wait <Int32>] [<CommonParameters>]
```

## DESCRIPTION

The `Reset-ClusterVMMonitoredState` cmdlet resets the Application Critical state of a virtual
machine, so that the virtual machine is no longer marked as being in a critical state in the
cluster. Note: This cmdlet can only be run locally on the virtual machine or through Windows
PowerShell remoting to the virtual machine.

## EXAMPLES

### Example 1

```powershell
Reset-ClusterVMMoniteredState
```

This example resets the state of the virtual machine and clears the critical state.

## PARAMETERS

### -Wait

Specifies the time in seconds to wait for the cmdlet. If the **Wait** parameter isn't specified,
then the cmdlet waits for completion. If `-Wait 0` is specified, then the call is initiated and the
cmdlet returns without waiting.

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-ClusterVMMonitoredItem](./Add-ClusterVMMonitoredItem.md)

[Get-ClusterVMMonitoredItem](./Get-ClusterVMMonitoredItem.md)

[Remove-ClusterVMMonitoredItem](./Remove-ClusterVMMonitoredItem.md)
