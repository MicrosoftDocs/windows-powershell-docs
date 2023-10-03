---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://learn.microsoft.com/powershell/module/failoverclusters/add-clusteriscsitargetserverrole?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ClusteriSCSITargetServerRole

## SYNOPSIS
Creates a highly available iSCSI Target server.

## SYNTAX

```
Add-ClusteriSCSITargetServerRole [[-Name] <String>] [-Cluster <String>] [-IgnoreNetwork <StringCollection>]
 [-InputObject <PSObject>] [-StaticAddress <StringCollection>] [-Wait <Int32>] -Storage <StringCollection>
```

## DESCRIPTION
The **Add-ClusteriSCSITargetServerRole** cmdlet creates a highly available iSCSI Target server.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-ClusteriSCSITargetServerRole -Storage "Cluster Disk 5"
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
CLiSCSITarget              node1                                          Online
```

This example creates a clustered iSCSI Target server using Cluster Disk 5, and assigns a default name.

### EXAMPLE 2
```
PS C:\>Add-ClusteriSCSITargetServerRole -Storage "Cluster Disk 5" -Name MyiSCSITarget
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
MyiSCSITarget              node1                                          Online
```

This example creates a clustered iSCSI Target server using Cluster Disk 5, and assigns the name MyiSCSITarget.

### EXAMPLE 3
```
PS C:\>Add-ClusteriSCSITargetServerRole -Storage "Cluster Disk 5" -Wait 0
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
CLiSCSITarget              node1                                          Pending
```

This example creates a clustered iSCSI Target server using Cluster Disk 5, and assigns a default name.
The cmdlet completes without waiting for all resources to come online.

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
Specifies the cluster on which to create the highly available iSCSI Target server.

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
Specifies the name of the highly available iSCSI Target server to create.

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
Specifies the cluster disk resource to be added to the created highly available iSCSI Target server.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: True
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

[Get-ClusterResource](./Get-ClusterResource.md)

[New-IscsiServerTarget](../iscsitarget/New-IscsiServerTarget.md)

