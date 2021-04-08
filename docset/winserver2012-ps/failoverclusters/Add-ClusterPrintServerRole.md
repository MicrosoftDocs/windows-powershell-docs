---
author: Kateyanne
external help file: Failoverv2_Cmdlets.xml
manager: dansimp
Module Name: FailoverClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/failoverclusters/add-clusterprintserverrole?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ClusterPrintServerRole

## SYNOPSIS
Creates a clustered print server, a resource group that includes a printer and a disk for storing print job information and printer drivers.

## SYNTAX

```
Add-ClusterPrintServerRole [[-Name] <String>] [-Cluster <String>] [-IgnoreNetwork <StringCollection>]
 [-InputObject <PSObject>] [-StaticAddress <StringCollection>] [-Storage <StringCollection>] [-Wait <Int32>]
```

## DESCRIPTION
The **Add-ClusterPrintServerRole** cmdlet creates a clustered print server (a resource group that includes a printer and a disk for storing print job information and printer drivers).

When adding a clustered print server, specify a name for the print server, any IP address information that is not automatically supplied by your DHCP settings, and the storage volume or volumes that the clustered print server should use for print job information and printer drivers.

Note: This cmdlet has been deprecated and is only supported on firstref_server_7 and lower.

## EXAMPLES

### Example 1
```
PS C:\>Add-ClusterPrintServerRole -Storage "Cluster Disk 5"
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
cluster1PS                 node1                                         Online
```

This example creates a clustered print server using Cluster Disk 5, and assigns a default name.

### Example 2
```
PS C:\>Add-ClusterPrintServerRole -Storage "Cluster Disk 5" -Name MyPrintServer
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
MyPrintServer              node1                                         Online
```

This example creates a clustered print server using Cluster Disk 5, and assigns the name MyPrintServer.

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

### -IgnoreNetwork
Specifies one or more networks to ignore when running the cmdlet.
Networks with DHCP enabled are always included, but other networks need a static address to be specified using the **StaticAddress** parameter or should be explicitly ignored with this **IgnoreNetwork** parameter.

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

### -InputObject
Specifies the cluster on which to create the highly available print server.

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
Specifies the name of the highly available print server to create.

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

### -StaticAddress
Specifies one or more static addresses to use when running the cmdlet.
Networks with DHCP enabled are always included, but other networks need a static address to be specified using the **StaticAddress** parameter or should be explicitly ignored with this **IgnoreNetwork** parameter.

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

### -Storage
Specifies the cluster disk resource to be added to the created highly available print server.

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

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Remove-ClusterGroup](./Remove-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

[Stop-ClusterGroup](./Stop-ClusterGroup.md)

