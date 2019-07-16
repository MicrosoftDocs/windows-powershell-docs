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
title: Add-ClusteriSCSITargetServerRole
ms.reviewer:
ms.assetid: 4590635E-C5D5-4696-B149-1D87ABB340E9
---

# Add-ClusteriSCSITargetServerRole

## SYNOPSIS
Creates a highly available iSCSI Target server.

## SYNTAX

```
Add-ClusteriSCSITargetServerRole -Storage <StringCollection> [-StaticAddress <StringCollection>]
 [-IgnoreNetwork <StringCollection>] [[-Name] <String>] [-Wait <Int32>] [-InputObject <PSObject>]
 [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-ClusteriSCSITargetServerRole** cmdlet creates a highly available iSCSI Target server.

## EXAMPLES

### Example 1: Create a clustered target server
```
PS C:\> Add-ClusteriSCSITargetServerRole -Storage "Cluster Disk 5"
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
CLiSCSITarget              node1                                          Online
```

This example creates a clustered iSCSI Target server using Cluster Disk 5, and assigns a default name.

### Example 2
```
PS C:\> Add-ClusteriSCSITargetServerRole -Storage "Cluster Disk 5" -Name MyiSCSITarget
Name                       OwnerNode                                      State 
----                       ---------                                      ----- 
MyiSCSITarget              node1                                          Online
```

This example creates a clustered iSCSI Target server using Cluster Disk 5, and assigns the name MyiSCSITarget.

### Example 3
```
PS C:\> Add-ClusteriSCSITargetServerRole -Storage "Cluster Disk 5" -Wait 0
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
Position: 0
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[Get-ClusterResource](./Get-ClusterResource.md)

