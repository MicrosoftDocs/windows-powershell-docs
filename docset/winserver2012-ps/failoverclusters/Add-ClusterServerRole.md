---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-clusterserverrole?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ClusterServerRole

## SYNOPSIS
Creates a highly available basic server that contains only a client access point and storage.

## SYNTAX

```
Add-ClusterServerRole [[-Name] <String>] [-Cluster <String>] [-IgnoreNetwork <StringCollection>]
 [-InputObject <PSObject>] [-StaticAddress <StringCollection>] [-Storage <StringCollection>] [-Wait <Int32>]
```

## DESCRIPTION
The **Add-ClusterServerRole** cmdlet creates a highly available basic server that contains only a client access point and storage.
After adding the basic server, other resources can be added to create a functional clustered role.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### Example 1
```
PS C:\>Add-ClusterServerRole
Name                       OwnerNode                            State 
----                       ---------                            ----- 
cluster1Other              node2                               Online
```

This example establishes a default name for a clustered server.
It does not specify any storage.
Storage and other resources can be added later.

### Example 2
```
PS C:\>Add-ClusterServerRole -Storage "Cluster Disk 3" -Name MainSrv1
Name                       OwnerNode                            State 
----                       ---------                            ----- 
MainSrv1                   node2                               Online
```

This example creates a clustered service or application using Cluster Disk 3, and assigns the name MainSrv1.

### Example 3
```
PS C:\>Add-ClusterServerRole -Storage "Cluster Disk 4","Cluster Disk 5" -Name MainSrv2
Name                       OwnerNode                            State 
----                       ---------                            ----- 
MainSrv2                   node2                               Online
```

This example creates a clustered service or application using Cluster Disk 4 and Cluster Disk 5, and assigns the name MainSrv2.

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
Specifies the cluster on which to create the highly available role or application.

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
Specifies the name of the highly available server to create.

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
Specifies the cluster disk resource to be added to the created highly available server.

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

