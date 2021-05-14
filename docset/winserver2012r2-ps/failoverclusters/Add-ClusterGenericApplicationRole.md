---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/failoverclusters/add-clustergenericapplicationrole?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ClusterGenericApplicationRole
---

# Add-ClusterGenericApplicationRole

## SYNOPSIS
Configures high availability for an application that was not originally designed to run in a failover cluster.

## SYNTAX

```
Add-ClusterGenericApplicationRole -CommandLine <String> [-Parameters <String>]
 [-CheckpointKey <StringCollection>] [-Storage <StringCollection>] [-StaticAddress <StringCollection>]
 [-IgnoreNetwork <StringCollection>] [[-Name] <String>] [-Wait <Int32>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-ClusterGenericApplicationRole** cmdlet configures high availability for an application that was not originally designed to run in a failover cluster.

If an application is run as a Generic Application, the cluster software will start the application, then periodically query the operating system to see whether the application appears to be running.
If so, then it is presumed to be online and will not be restarted or failed over.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### Example 1
```
PS C:\>Add-ClusterGenericApplicationRole -CommandLine NewApplication.exe
Name                       OwnerNode                           State 
----                       ---------                           ----- 
cluster1GenApp             node2                              Online
```

This example configures NewApplication.exe as a generic clustered application.
A default name will be used for client access and this application requires no storage.

### Example 2
```
PS C:\>Add-ClusterGenericApplicationRole -CommandLine NewApplication.exe -Storage "Cluster Disk 4" -Name NewApplication
Name                       OwnerNode                           State 
----                       ---------                           ----- 
NewApplication                 node2                          Online
```

This example configures NewApplication.exe as a generic clustered application using Cluster Disk 4, and assigns the name NewApplication.

### Example 3
```
PS C:\>Add-ClusterGenericApplicationRole -CommandLine NewApplication.exe -Wait 0
Name                       OwnerNode                           State 
----                       ---------                           ----- 
cluster1GenApp             node2                             Pending
```

This example configures NewApplication.exe as a generic clustered application and assigns the name NewApplication.
The cmdlet completes without waiting for all resources to come online.

## PARAMETERS

### -CheckpointKey
Specifies a comma-separated list of registry checkpoint keys to add for this highly available generic application.
All registry paths are relative to HKEY_LOCAL_MACHINE.

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

### -CommandLine
Specifies the Windows PowerShell® command line to use for the highly available generic application.
If the full path is specified, then the current directory is parsed out of the Windows PowerShell command line.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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
Specifies the cluster on which to create the highly available application.

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
Specifies the name of the highly available application to create.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameters
Specifies the parameters to use for the highly available generic application.

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
Specifies the cluster disk resource to be added to the created highly available application.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Add-ClusterGenericScriptRole](./Add-ClusterGenericScriptRole.md)

[Add-ClusterGenericServiceRole](./Add-ClusterGenericServiceRole.md)

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Remove-ClusterGroup](./Remove-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

[Stop-ClusterGroup](./Stop-ClusterGroup.md)

