---
external help file: Failoverv2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 1E1D49DC-53B6-4EB5-9B1A-6583EB55ECA8
manager: dansimp
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-ClusterGroup

## SYNOPSIS
Gets information about one or more clustered roles (resource groups) in a failover cluster.

## SYNTAX

```
Get-ClusterGroup [[-Name] <StringCollection>] [-Cluster <String>] [-InputObject <PSObject>] [-VMId <Guid>]
```

## DESCRIPTION
The **Get-ClusterGroup** cmdlet gets information about one or more clustered roles (resource groups) in a failover cluster.

A resource group is the unit of failover.
During failover, all resources in the resource group move together.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-ClusterGroup
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
Available Storage          node1                                         Online 
Cluster Group              node2                                         Online 
cluster1FS                 node1                                         Online 
cluster1FS-Other           node1                                         Online
```

This example lists the state and owner node of each clustered role, or resource group, in the local cluster.

### EXAMPLE 2
```
PS C:\>Get-ClusterGroup -Name "Cluster Group" | Get-ClusterResource
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster Disk 1      Online              Cluster Group       Physical Disk 
Cluster IP Address  Online              Cluster Group       IP Address 
Cluster IP Addre... Online              Cluster Group       IPv6 Address 
Cluster Name        Online              Cluster Group       Network Name
```

This example lists the resources in Cluster Group on the local cluster.

### EXAMPLE 3
```
PS C:\>Get-ClusterNode -Name node1 | Get-ClusterGroup
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
Cluster Group              node1                                         Online
```

This example lists the clustered services and applications, or resource groups, that are currently owned by node1 in the local cluster.

### EXAMPLE 4
```
PS C:\>Get-ClusterGroup -Name FileServer1 | Format-List -Process *
Cluster                :  Cluster1 
IsCoreGroup            : False 
OwnerNode              :  node1 
State                  : Online 
Name                   :  FileServer1 
Description            : 
PersistentState        : 0 
FailoverThreshold      : 4294967295 
FailoverPeriod         : 6 
AutoFailbackType       : 0 
FailbackWindowStart    : 4294967295 
FailbackWindowEnd      : 4294967295 
AntiAffinityClassNames : {} 
Id                     :  189ec8ad-1831-4f57-9bb0-3ffb9cbb9227
```

This example displays the properties of a clustered file server, or resource group, called FileServer1, in the form of a list.

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
Specifies the cluster or cluster node on which to enumerate the clustered roles.

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
Specifies the name of the clustered role to get.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -VMId
Specifies the virtual machine identifier (ID).

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Format-List](http://go.microsoft.com/fwlink/?LinkID=113302)

[Add-ClusterGroup](./Add-ClusterGroup.md)

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Remove-ClusterGroup](./Remove-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

[Stop-ClusterGroup](./Stop-ClusterGroup.md)

