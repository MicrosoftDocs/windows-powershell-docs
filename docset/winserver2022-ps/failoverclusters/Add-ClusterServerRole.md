---
description: Add-ClusterServerRole
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 07/26/2022
online version: https://docs.microsoft.com/powershell/module/failoverclusters/add-clusterserverrole?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ClusterServerRole
---

# Add-ClusterServerRole

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

```
Add-ClusterServerRole [-DnsName <String>] [-NetworkNameName <String>] [-Storage <StringCollection>]
[-StaticAddress <StringCollection>] [-IgnoreNetwork <StringCollection>] [[-Name] <String>]
[-Wait <Int32>] [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
Add-ClusterServerRole
```

This example establishes a default name for a clustered server.
It does not specify any storage.
Storage and other resources can be added later.

### Example 2
```powershell
Add-ClusterServerRole -Storage "Cluster Disk 3" -Name MainSrv1
```

This example creates a clustered service or application using Cluster Disk 3, and assigns the name
MainSrv1.

### Example 3
```powershell
Add-ClusterServerRole -Storage "Cluster Disk 4","Cluster Disk 5" -Name MainSrv2
```

This example creates a clustered service or application using Cluster Disk 4 and Cluster Disk 5, and
assigns the name MainSrv2.

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

### -DnsName
{{ Fill DnsName Description }}

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
Specifies one or more networks to ignore when running the cmdlet. Networks with DHCP enabled are
always included, but other networks need a static address to be specified using the
**StaticAddress** parameter or should be explicitly ignored with this **IgnoreNetwork** parameter.

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
Specifies the cluster on which to create the server role.

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
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkNameName
{{ Fill NetworkNameName Description }}

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
Specifies one or more static addresses to use when running the cmdlet. Networks with DHCP enabled
are always included, but other networks need a static address to be specified using the
**StaticAddress** parameter or should be explicitly ignored with this **IgnoreNetwork** parameter.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Management.Automation.PSObject

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterGroup

## NOTES

## RELATED LINKS

[https://go.microsoft.com/fwlink/?LinkId=216195](https://go.microsoft.com/fwlink/?LinkId=216195)

