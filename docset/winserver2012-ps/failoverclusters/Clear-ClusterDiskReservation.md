---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: A99C3621-A137-4EB1-9AC1-A05115BDDFD3
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Clear-ClusterDiskReservation

## SYNOPSIS
Clears the persistent reservation on a disk in a failover cluster.

## SYNTAX

```
Clear-ClusterDiskReservation [[-Node] <StringCollection>] [-Force] -Disk <UInt32[]>
```

## DESCRIPTION
The **Clear-ClusterDiskReservation** cmdlet clears the persistent reservation on a disk in a failover cluster.
This cmdlet prompts for confirmation unless you specify the **Force** parameter.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### Example 1
```
PS C:\>Clear-ClusterDiskReservation -Disk 5
```

This example clears the persistent reservation on Disk 5 on the local node after asking for user confirmation.

### Example 2
```
C:\PS>Clear-ClusterDiskReservation -Disk 6 -Node node2 -Force
```

This example clears the persistent reservation on Disk 6 on the node named node2 without asking for user confirmation.

## PARAMETERS

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

[Clear-ClusterNode](./Clear-ClusterNode.md)

[Remove-Cluster](./Remove-Cluster.md)

