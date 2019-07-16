---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-ClusterGenericServiceRole
ms.reviewer:
ms.assetid: 188158B2-1000-46CE-BBF0-13D0A8191AD4
---

# Add-ClusterGenericServiceRole

## SYNOPSIS
Configures high availability for a service that was not originally designed to run in a failover cluster.

## SYNTAX

```
Add-ClusterGenericServiceRole -ServiceName <String> [-CheckpointKey <StringCollection>]
 [-Storage <StringCollection>] [-StaticAddress <StringCollection>] [-IgnoreNetwork <StringCollection>]
 [[-Name] <String>] [-Wait <Int32>] [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-ClusterGenericServiceRole** cmdlet configures high availability for a service that was not originally designed to run in a failover cluster.
The cluster software will start the service, then periodically query the Service Controller, which is a feature of the operating system, to determine whether the service appears to be running.
If so, then it is presumed to be online, and will not be restarted or failed over.

Note: This cmdlet cannot be run remotely without Credential Security Service Provider (CredSSP) authentication on the server computer.

## EXAMPLES

### Example 1: Configure a service that uses default values
```
PS C:\> Add-ClusterGenericServiceRole -ServiceName "Service1"
Name                       OwnerNode                           State 
----                       ---------                           ----- 
cluster1GenSvc             node1                              Online
```

This example configures Service1 as a generic clustered service, using defaults for the name and IP address, and does not assign a disk.

### Example 2: Configure a service that uses default values and a specified disk
```
PS C:\> Add-ClusterGenericServiceRole -ServiceName "Service1" -Storage "Cluster Disk 6"
Name                       OwnerNode                           State 
----                       ---------                           ----- 
cluster1GenSvc             node1                              Online
```

This example configures Service1 as a generic clustered service using Cluster Disk 6, and assigns defaults for the name and IP address.

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

### -IgnoreNetwork
Specifies one or more networks to ignore when running the cmdlet.
Networks with DHCP enabled are always included, but other networks need a static address to be specified using the *StaticAddress* parameter or should be explicitly ignored with this *IgnoreNetwork* parameter.

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
Specifies the cluster on which to create the highly available service.

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
Specifies the name of the highly available service to create.

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

### -ServiceName
Specifies the service name to use for the highly available service.

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

### -StaticAddress
Specifies one or more static addresses to use when running the cmdlet.
Networks with DHCP enabled are always included, but other networks need a static address to be specified using the *StaticAddress* parameter or should be explicitly ignored with this *IgnoreNetwork* parameter.

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
Specifies the cluster disk resource to be added to the created highly available service.

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
If the *Wait* parameter is not specified, then the cmdlet waits for completion.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Add-ClusterGenericApplicationRole](./Add-ClusterGenericApplicationRole.md)

[Add-ClusterGenericScriptRole](./Add-ClusterGenericScriptRole.md)

[Get-ClusterGroup](./Get-ClusterGroup.md)

[Move-ClusterGroup](./Move-ClusterGroup.md)

[Remove-ClusterGroup](./Remove-ClusterGroup.md)

[Start-ClusterGroup](./Start-ClusterGroup.md)

[Stop-ClusterGroup](./Stop-ClusterGroup.md)

