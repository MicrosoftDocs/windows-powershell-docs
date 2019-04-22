---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 3A030267-1460-464D-91F7-63407B0D7ADB
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Remove-ClusterSharedVolume

## SYNOPSIS
Removes a volume from the Cluster Shared Volumes in a failover cluster, and places it in Available Storage in the cluster.

## SYNTAX

```
Remove-ClusterSharedVolume [[-Name] <StringCollection>] [-Cluster <String>] [-InputObject <PSObject>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-ClusterSharedVolume** cmdlet removes a volume from the Cluster Shared Volumes in a failover cluster, and places it in Available Storage in the cluster.
After placing a volume in Available Storage, you can use the volume when you configure a new clustered role.

## EXAMPLES

### Example 1
```
PS C:\>Remove-ClusterSharedVolume -Name "Cluster Disk 3"
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster Disk 3      Online              Available Storage   Physical Disk
```

This example removes the CSV named Cluster Disk 3 from the Cluster Shared Volumes on the local cluster, and places it in Available Storage.

### Example 2
```
PS C:\>Get-ClusterSharedVolume -Name "Cluster Disk 4" | Remove-ClusterSharedVolume
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster Disk 4      Online              Available Storage   Physical Disk
```

This example removes the CSV named Cluster Disk 4 from the Cluster Shared Volumes on the local cluster, and places it in Available Storage.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

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
Specifies the Cluster Shared Volume to remove.

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

### -Name
Specifies the name of the Cluster Shared Volume to remove.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[Add-ClusterSharedVolume](./Add-ClusterSharedVolume.md)

[Get-ClusterSharedVolume](./Get-ClusterSharedVolume.md)

[Move-ClusterSharedVolume](./Move-ClusterSharedVolume.md)

