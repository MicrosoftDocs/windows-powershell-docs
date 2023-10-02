---
external help file: Failoverv2_Cmdlets.xml
Module Name: FailoverClusters
online version: https://learn.microsoft.com/powershell/module/failoverclusters/start-clustergroup?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Start-ClusterGroup

## SYNOPSIS
Starts one or more clustered roles, also known as resource groups, on a failover cluster.

## SYNTAX

```
Start-ClusterGroup [[-Name] <String>] [-Cluster <String>] [-IgnoreLocked] [-InputObject <PSObject>]
 [-Wait <Int32>]
```

## DESCRIPTION
The **Start-ClusterGroup** cmdlet starts one or more clustered roles, also known as resource groups, on a failover cluster.
With this cmdlet, a clustered role can be started again after stopping it for maintenance or diagnosis.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Start-ClusterGroup FileServer1
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
FileServer1                node1                                         Online
```

This example starts the clustered file server, or resource group, called FileServer1.

### EXAMPLE 2
```
PS C:\>Start-ClusterGroup FileServer1 -Wait 0
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
FileServer1                node1                                        Pending
```

This example starts the clustered file server, or resource group, called FileServer1.
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
Specifies the clustered role to start.

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
Specifies the name of the clustered role to start.

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

[Stop-ClusterGroup](./Stop-ClusterGroup.md)

