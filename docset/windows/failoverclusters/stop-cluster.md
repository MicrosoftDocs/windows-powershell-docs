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
title: Stop-Cluster
ms.reviewer:
ms.assetid: EBEA18FB-46A5-4826-8C80-7DD9FD6EEEE1
---

# Stop-Cluster

## SYNOPSIS
Stops the Cluster service on all nodes in a failover cluster, which will stop all services and applications configured in the cluster.

## SYNTAX

### Cluster name (Default)
```
Stop-Cluster [[-Cluster] <String>] [-Force] [-Wait <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Stop-Cluster [-Force] [-Wait <Int32>] [-InputObject <PSObject>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-Cluster** cmdlet stops the Cluster service on all nodes in a failover cluster, which will stop all services and applications configured in the cluster.
A node can only function as part of the cluster when the Cluster service is running on that node.

## EXAMPLES

### Example 1: Stop Cluster service on all nodes of the local cluster
```
PS C:\> Stop-Cluster
```

This example stops the Cluster service on all nodes in the local cluster, which will stop all services and applications configured in the cluster.

### Example 2: Stop Cluster service on all nodes of a cluster
```
PS C:\> Stop-Cluster -Name cluster1
```

This example stops the Cluster service on all nodes in the cluster named cluster1, which will stop all services and applications configured in the cluster.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

```yaml
Type: String
Parameter Sets: Cluster name
Aliases: Name

Required: False
Position: 0
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -InputObject
Specifies the cluster to stop.

```yaml
Type: PSObject
Parameter Sets: InputObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Wait
{{Fill Wait Description}}

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
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-Cluster](./Get-Cluster.md)

[New-Cluster](./New-Cluster.md)

[Remove-Cluster](./Remove-Cluster.md)

[Start-Cluster](./Start-Cluster.md)

[Test-Cluster](./Test-Cluster.md)

