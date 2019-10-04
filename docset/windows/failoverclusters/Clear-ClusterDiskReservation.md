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
title: Clear-ClusterDiskReservation
ms.reviewer:
ms.assetid: A99C3621-A137-4EB1-9AC1-A05115BDDFD3
---

# Clear-ClusterDiskReservation

## SYNOPSIS
Clears the persistent reservation on a disk in a failover cluster.

## SYNTAX

```
Clear-ClusterDiskReservation [[-Node] <StringCollection>] -Disk <UInt32[]> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Clear-ClusterDiskReservation** cmdlet clears the persistent reservation on a disk in a failover cluster.
This cmdlet prompts for confirmation unless you specify the **Force** parameter.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### Example 1
```
PS C:\> Clear-ClusterDiskReservation -Disk 5
```

This example clears the persistent reservation on Disk 5 on the local node after asking for user confirmation.

### Example 2
```
C:\PS>Clear-ClusterDiskReservation -Disk 6 -Node node2 -Force
```

This example clears the persistent reservation on Disk 6 on the node named node2 without asking for user confirmation.

## PARAMETERS

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

### -Disk
Specifies the disk number on which to clear the persistent reservations.
This is the disk number as it appears in Disk Management on the node.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Runs the cmdlet without prompting for confirmation.
By default the cmdlet will ask for confirmation from the user before proceeding.

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

### -Node
Specifies the name of the cluster node on which to clear the disk reservation.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Clear-ClusterNode](./Clear-ClusterNode.md)

[Remove-Cluster](./Remove-Cluster.md)

