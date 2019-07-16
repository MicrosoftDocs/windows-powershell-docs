---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Reset-ClusterVMMonitoredState
ms.reviewer:
ms.assetid: CFCF68B3-A7E4-42E9-A185-61DF7D0CA4B2
---

# Reset-ClusterVMMonitoredState

## SYNOPSIS
Resets the Application Critical state of a virtual machine, so that the virtual machine is no longer marked as being in a critical state in the cluster.

## SYNTAX

```
Reset-ClusterVMMonitoredState [-Wait <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The **Reset-ClusterVMMonitoredState** cmdlet resets the Application Critical state of a virtual machine, so that the virtual machine is no longer marked as being in a critical state in the cluster.
Note: This cmdlet can only be run locally on the virtual machine or through Windows PowerShell® remoting to the virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Reset-ClusterVMMoniteredState
```

This example resets the state of the virtual machine and clears the critical state.

## PARAMETERS

### -Wait


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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-ClusterVMMonitoredItem](./Add-ClusterVMMonitoredItem.md)

[Get-ClusterVMMonitoredItem](./Get-ClusterVMMonitoredItem.md)

[Remove-ClusterVMMonitoredItem](./Remove-ClusterVMMonitoredItem.md)

