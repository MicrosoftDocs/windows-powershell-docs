---
author: Kateyanne
external help file: Failoverv2_Cmdlets.xml
manager: dansimp
Module Name: FailoverClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/failoverclusters/get-clusterresourcetype?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ClusterResourceType

## SYNOPSIS
Gets information about one or more resource types in a failover cluster.

## SYNTAX

```
Get-ClusterResourceType [[-Name] <StringCollection>] [-Cluster <String>] [-InputObject <PSObject>]
```

## DESCRIPTION
The **Get-ClusterResourceType** cmdlet gets information about one or more resource types in a failover cluster.
Obtain information such as the name of the dynamic-link library (DLL) through which the Cluster service communicates with a particular resource type.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-ClusterResourceType
Name                                    DisplayName 
----                                    ----------- 
DFS Replicated Folder                   DFS Replicated Folder 
DHCP Service                            DHCP Service 
Distributed File System                 Distributed File System 
Distributed Transaction Coordinator     Distributed Transaction Coordinator 
File Server                             File Server 
File Share Witness                      File Share Quorum Witness 
Generic Application                     Generic Application 
Generic Script                          Generic Script 
Generic Service                         Generic Service 
IP Address                              IP Address 
IPv6 Address                            IPv6 Address 
IPv6 Tunnel Address                     IPv6 Tunnel Address 
Microsoft iSNS                          iSNSClusRes 
MSMQ                                    (Resource Type Unavailable) 
MSMQTriggers                            (Resource Type Unavailable) 
Network Name                            Network Name 
NFS Share                               NFS Share 
Physical Disk                           Physical Disk 
Print Spooler                           Print Spooler 
Virtual Machine                         Virtual Machine 
Virtual Machine Configuration           Virtual Machine Configuration 
Volume Shadow Copy Service Task         Volume Shadow Copy Service Task 
WINS Service                            WINS Service
```

This example lists all the resource types that can be used in configurations on the local cluster.

### EXAMPLE 2
```
PS C:\>Get-ClusterResourceType -Name "File Server" | Format-List -Property *
Cluster                : Cluster1 
DisplayName            : File Server 
Name                   : file server 
DllName                : clusres.dll 
Description            : 
AdminExtensions        : {} 
LooksAlivePollInterval : 5000 
IsAlivePollInterval    : 60000 
PendingTimeout         : 180000 
DeadlockTimeout        : 300000 
Id                     : f582c84f-0066-0069-6c65-207365727665
```

This example gets information about the File Server resource type on the local cluster, and displays the information in the form of a list.

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
Specifies the cluster on which to enumerate the cluster resource types.

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
Specifies the name of the cluster resource type to get.

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

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResourceType

## NOTES

## RELATED LINKS

[Add-ClusterResourceType](./Add-ClusterResourceType.md)

[Remove-ClusterResourceType](./Remove-ClusterResourceType.md)

