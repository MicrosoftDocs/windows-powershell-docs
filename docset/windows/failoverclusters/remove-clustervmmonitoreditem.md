---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: coreyp
author: coreyp-at-msft
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
title: Remove-ClusterVMMonitoredItem
ms.assetid: AF287F10-AB05-4217-9C72-AC4D2A851DCA
---

# Remove-ClusterVMMonitoredItem

## SYNOPSIS
Removes monitoring of a service or event that is currently being monitored on a virtual machine.

## SYNTAX

### VirtualMachine (Default)
```
Remove-ClusterVMMonitoredItem [-InputObject <PSObject>] [-Service <StringCollection>] [-EventLog <String>]
 [-EventSource <String>] [-EventId <Int32>] [[-VirtualMachine] <String>] [-Wait <Int32>] [-Cluster <String>]
 [<CommonParameters>]
```

### VMId
```
Remove-ClusterVMMonitoredItem [-InputObject <PSObject>] [-Service <StringCollection>] [-EventLog <String>]
 [-EventSource <String>] [-EventId <Int32>] [-VMId <Guid>] [-Wait <Int32>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ClusterVMMonitoredItem** cmdlet removes monitoring of a service or event that is currently being monitored.
After removal, if the service fails or the event occurs, the system will no longer take an action, such as restarting the virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Get-ClusterVMMonitoredItem -VirtualMachine VM1 | Remove-ClusterVMMonitoredItem -VirtualMachine VM1
```

This example removes all of the items being monitored on the virtual machine named VM1.

### Example 2
```
PS C:\> Remove-ClusterVMMonitoredItem -VirtualMachine VM1 -Service spooler
```

This example removes monitoring on the print spooler service on the virtual machine named VM1.

## PARAMETERS

### -Cluster


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

### -EventId


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

### -EventLog


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

### -EventSource


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

### -InputObject


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

### -Service


```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMId


```yaml
Type: Guid
Parameter Sets: VMId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachine


```yaml
Type: String
Parameter Sets: VirtualMachine
Aliases: VM

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterVMMonitoredItem

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-ClusterVMMonitoredItem](./Add-ClusterVMMonitoredItem.md)

[Get-ClusterVMMonitoredItem](./Get-ClusterVMMonitoredItem.md)

[Reset-ClusterVMMonitoredState](./Reset-ClusterVMMonitoredState.md)

