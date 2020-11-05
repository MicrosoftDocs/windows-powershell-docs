---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: BE89DFE6-70CF-4A30-BE4F-DC8679C8776E
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Stop-ClusterGroup

## SYNOPSIS
Stops one or more clustered roles, also known as resource groups, on a failover cluster.

## SYNTAX

```
Stop-ClusterGroup [[-Name] <String>] [-Cluster <String>] [-IgnoreLocked] [-InputObject <PSObject>]
 [-Wait <Int32>]
```

## DESCRIPTION
The **Stop-ClusterGroup** cmdlet stops one or more clustered roles, also known as resource groups, on a failover cluster.

If maintenance on a clustered role is needed, the clustered role can be stopped in an orderly fashion by using this cmdlet.

## EXAMPLES

### Example 1
```
PS C:\>Stop-ClusterGroup FileServer1
Name                       OwnerNode                            State 
----                       ---------                            ----- 
FileServer1                 node1                              Offline
```

This example stops the clustered role, or resource group, called FileServer1 on the local cluster.

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
Specifies the clustered role to stop.

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
Specifies the name of the clustered role to stop.

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

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Add-ClusterGroup](./Add-ClusterGroup.md)

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Remove-ClusterGroup](./Remove-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

