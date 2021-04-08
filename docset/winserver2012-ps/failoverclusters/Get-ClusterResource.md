---
author: Kateyanne
external help file: Failoverv2_Cmdlets.xml
manager: dansimp
Module Name: FailoverClusters
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/failoverclusters/get-clusterresource?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ClusterResource

## SYNOPSIS
Gets information about one or more resources in a failover cluster.

## SYNTAX

```
Get-ClusterResource [[-Name] <StringCollection>] [-Cluster <String>] [-InputObject <PSObject>] [-VMId <Guid>]
```

## DESCRIPTION
The **Get-ClusterResource** cmdlet gets information about one or more resources in a failover cluster.

To set a common property for a clustered resource, use this cmdlet to get the object for the clustered resource, and then set the appropriate property on that object directly.
To get and set more specific information about a clustered resource, use this cmdlet with Get-ClusterParameter and Set-ClusterParameter.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-ClusterResource
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster Disk 1      Online              Cluster Group       Physical Disk 
Cluster Disk 2      Online              Available Storage   Physical Disk 
Cluster Disk 3      Online              Available Storage   Physical Disk 
Cluster Disk 4      Online              Available Storage   Physical Disk 
Cluster Disk 5      Online              Available Storage   Physical Disk 
Cluster Disk 6      Online              Available Storage   Physical Disk 
Cluster Disk 7      Online              Available Storage   Physical Disk 
Cluster IP Address  Online              Cluster Group       IP Address 
Cluster IP Addre... Online              Cluster Group       IPv6 Address 
Cluster Name        Online              Cluster Group       Network Name
```

This example lists all cluster resources on the local cluster.

### EXAMPLE 2
```
PS C:\>Get-ClusterResource -Name "Cluster Disk 2" | Format-List -Property *
Cluster                :  cluster1 
IsCoreResource         : False 
IsNetworkClassResource : False 
IsStorageClassResource : True 
OwnerNode              :  node2 
ResourceType           : Physical Disk 
State                  : Online 
OwnerGroup             : Available Storage 
Name                   :  Cluster Disk 2 
MaintenanceMode        : False 
MonitorProcessId       : 524 
Description            : 
SeparateMonitor        : False 
PersistentState        : 1 
LooksAlivePollInterval : 4294967295 
IsAlivePollInterval    : 4294967295 
RestartAction          : 2 
RestartThreshold       : 1 
RestartDelay           : 500 
RestartPeriod          : 900000 
RetryPeriodOnFailure   : 3600000 
PendingTimeout         : 180000 
DeadlockTimeout        : 300000 
ResourceSpecificStatus : 
Id                     :  6e394089-145a-4279-b75d-b14015cc36e4
```

This example displays information about Cluster Disk 2, on the local cluster, in the form of a list.

### EXAMPLE 3
```
PS C:\>Get-ClusterResource -Name "Cluster Disk 2" | Get-ClusterParameter
Object              Name                Value               Type 
------              ----                -----               ---- 
Cluster Disk 2      DiskIdType          0                   UInt32 
Cluster Disk 2      DiskSignature       2654136047          UInt32 
Cluster Disk 2      DiskIdGuid                              String 
Cluster Disk 2      DiskRunChkDsk       0                   UInt32 
Cluster Disk 2      DiskUniqueIds       {16, 0, 0, 0...}    ByteArray 
Cluster Disk 2      DiskVolumeInfo      {1, 0, 0, 0...}     ByteArray 
Cluster Disk 2      DiskArbInterval     3                   UInt32 
Cluster Disk 2      DiskPath                                String 
Cluster Disk 2      DiskReload          0                   UInt32 
Cluster Disk 2      MaintenanceMode     0                   UInt32 
Cluster Disk 2      MaxIoLatency        1000                UInt32 
Cluster Disk 2      CsvEnforseWriteT... 0                   UInt32 
Cluster Disk 2      DiskPnpUpdate       {0, 0, 0, 0...}     ByteArray
```

This example displays detailed parameters for Cluster Disk 2 on the local cluster.

### EXAMPLE 4
```
PS C:\>Get-ClusterGroup -Name FileServer1 | Get-ClusterResource
Name                State               Group               ResourceType 
----                -----               -----               ------------ 
Cluster Disk 1      Online              FileServer1         Physical Disk 
Cluster IP Address  Online              FileServer1         IP Address 
Cluster IP Addre... Online              FileServer1         IPv6 Address 
FileServer1         Online              FileServer1         Network Name
```

This example lists cluster resources in cluster group named FileServer1, a clustered file server on the local cluster.

### EXAMPLE 5
```
PS C:\>Get-ClusterResource -Name "Cluster Disk 2" | ForEach-Object -Process {$_.RestartDelay = 600}
```

This example sets the common property RestartDelay for the Cluster Disk 2 resource on the local cluster to 600.

### Example 6
```
PS C:\>Get-ClusterResource -Name "cluster pool 1" | Format-List -Property OwnerNode
OwnerNode : cluster-node1
```

This example shows how to display the owner of a cluster pooled disk.

### Example 7
```
PS C:\>Get-ClusterResource -Name *print-VM1 | Get-VM | Stop-VM -Verbose
VERBOSE: Current VMobject  = Microsoft.HyperV.PowerShell.VirtualMachine[] 
VERBOSE: Stop-VM will shutdown the virtual machine "print-VM1". 
 
Confirm 
Hyper-V cannot shut down virtual machine print-VM1 because the Shutdown integration service is unavailable. To avoid 
potential data loss, you can pause or save the state of the virtual machine. The other option is to turn off the 
virtual machine, but data loss might occur. 


[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):Y
```

This example enumerates the cluster resources for wildcard characters *print-VM1 and stops the corresponding virtual machines.
Verbose mode is turned on for details of the operation.

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
Specifies the cluster node or cluster group on which to enumerate cluster resources.

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
Specifies the name of the cluster resource to get.

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

### Microsoft.FailoverClusters.PowerShell.ClusterResource

### Microsoft.FailoverClusters.PowerShell.ClusterNode

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## NOTES

## RELATED LINKS

[ForEach-Object](https://go.microsoft.com/fwlink/?LinkID=113300)

[Format-List](https://go.microsoft.com/fwlink/?LinkID=113302)

[Add-ClusterResource](./Add-ClusterResource.md)

[Move-ClusterResource](./Move-ClusterResource.md)

[Remove-ClusterResource](./Remove-ClusterResource.md)

[Resume-ClusterResource](./Resume-ClusterResource.md)

[Start-ClusterResource](./Start-ClusterResource.md)

[Stop-ClusterResource](./Stop-ClusterResource.md)

[Suspend-ClusterResource](./Suspend-ClusterResource.md)

