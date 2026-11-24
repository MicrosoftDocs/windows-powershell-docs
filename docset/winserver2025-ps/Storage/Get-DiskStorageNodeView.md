---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-diskstoragenodeview?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DiskStorageNodeView
---

# Get-DiskStorageNodeView

## SYNOPSIS
Gets the view of a disk from a storage node.

## SYNTAX

```
Get-DiskStorageNodeView [[-StorageNode] <CimInstance>] [[-Disk] <CimInstance>] [[-CimSession] <CimSession>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DiskStorageNodeView** cmdlet gets the view of a disk from the perspective of the specified storage node.

## EXAMPLES

### Example 1: Get the node view for a disk on a storage node
```
PS C:\>Get-Disk -Number 11 | Get-DiskStorageNodeView
StorageNodeObjectId: {1}\\Contoso-C1\ROOT/Microsoft/Windows/Storage/Providers_v2\SPACES_StorageNode.ObjectId="{57e

eb746-cb28-4a7e-90bb-3d124ffcb0f7}:SN:Contoso-04"





DiskNumber        : 11

HealthStatus      : Healthy

OperationalStatus : Online

IsReadOnly        : False

IsOffline         : False

OfflineReason     :

StorageNode       : MSFT_StorageNode (ObjectId = "{1}\\Contoso-C1\ROOT/Microsoft/Window...)

Disk              : MSFT_Disk (ObjectId = "{1}\\Contoso-C1\ROOT/Microsoft/Window...)
```

This command gets the disk numbered 11 by using **Get-Disk**, and then passes it to the current cmdlet by using the pipeline operator.
The current cmdlet gets the storage node on which disk 11 is present.
The command displays some node specific properties.

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

### -Disk
Specifies a disk object.
To obtain a **Disk** object, use the Get-Disk cmdlet.

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
Specifies a disk object.
To obtain a **StorageNode** object, use the Get-StorageNode cmdlet.

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

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

[Get-Disk](./Get-Disk.md)

[Get-StorageNode](./Get-StorageNode.md)

