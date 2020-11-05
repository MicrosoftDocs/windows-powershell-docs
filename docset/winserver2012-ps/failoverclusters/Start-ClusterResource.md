---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 18DB4B43-DD14-431D-93E4-27AF88CB1780
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Start-ClusterResource

## SYNOPSIS
Brings a resource online in a failover cluster.

## SYNTAX

```
Start-ClusterResource [[-Name] <String>] [-Cluster <String>] [-IgnoreLocked] [-InputObject <PSObject>]
 [-Wait <Int32>]
```

## DESCRIPTION
The **Start-ClusterResource** cmdlet brings a resource online in a failover cluster.
Before the resource is brought online, any resources that it depends are brought online.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Start-ClusterResource -Name "IP Address 172.24.11.0"
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
IP Address 172.2...  Online              cluster1FS12        IP Address
```

This example brings the resource called IP Address 172.24.11.0 online on the local cluster.
Before bringing the resource online, this cmdlet brings online any resources on which the resource depends.

### EXAMPLE 2
```
PS C:\>Start-ClusterResource -Name "IP Address 172.24.11.0" -Wait 0
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
IP Address 172.2...  OnlinePending       cluster1FS12        IP Address
```

This example brings the resource called IP Address 172.24.11.0 online on the local cluster.
Before bringing the resource online, this cmdlet brings online any resources on which the resource depends.
The Windows PowerShell® prompt returns as soon as the action has been initiated.

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

### -IgnoreLocked
Specifies that locked groups are ignored when running the cmdlet.

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
Specifies the cluster resource to bring online.

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
Specifies the name of the cluster resource to bring online.
This can also be the name of a Cluster Shared Volume (CSV).

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

### -Wait
Specifies the time in seconds to wait for the cmdlet.
If the **Wait** parameter is not specified, then the cmdlet waits for completion.
If `-Wait 0` is specified, then the call is initiated and the cmdlet returns without waiting.

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

## INPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## NOTES

## RELATED LINKS

[Add-ClusterResource](./Add-ClusterResource.md)

[Get-ClusterResource](./Get-ClusterResource.md)

[Move-ClusterResource](./Move-ClusterResource.md)

[Remove-ClusterResource](./Remove-ClusterResource.md)

[Resume-ClusterResource](./Resume-ClusterResource.md)

[Stop-ClusterResource](./Stop-ClusterResource.md)

[Suspend-ClusterResource](./Suspend-ClusterResource.md)

