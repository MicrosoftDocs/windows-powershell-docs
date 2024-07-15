---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-storageenclosurestoragenodeview?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageEnclosureStorageNodeView
---

# Get-StorageEnclosureStorageNodeView

## SYNOPSIS
Gets the node view of a Storage enclosure.

## SYNTAX

```
Get-StorageEnclosureStorageNodeView [[-StorageNode] <CimInstance>] [[-StorageEnclosure] <CimInstance>]
 [[-CimSession] <CimSession>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageEnclosureStorageNodeView** cmdlet gets the node view of a Storage enclosure.

## EXAMPLES

### Example 1: Get enclosure details on a storage node
```
PS C:\>Get-StorageNode -Name "StorageNode21" | Get-StorageEnclosureStorageNodeView
```

This command gets all storage enclosure details connected to storage node named StorageNode21.

### Example 2: Get storage enclosure details for all healthy enclosures
```
PS C:\>Get-StorageEnclosure -HealthStatus Healthy | Get-StorageEnclosureStorageNodeView
```

This command gets all Healthy storage enclosure details across all nodes in the cluster.

### Example 3: Get storage enclosure details across all nodes
```
PS C:\>Get-StorageEnclosureStorageNodeView
```

This command gets all storage enclosure details across all nodes in the cluster.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageEnclosure
Specifies the Storage enclosure.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageNode
Specifies the Storage node.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### MSFT_StorageNodeToStorageEnclosure[]
This cmdlet returns an array of **StorageNodeToStorageEnclosure** objects.

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-DiskStorageNodeView](./Get-DiskStorageNodeView.md)

[Get-PhysicalDiskStorageNodeView](./Get-PhysicalDiskStorageNodeView.md)

