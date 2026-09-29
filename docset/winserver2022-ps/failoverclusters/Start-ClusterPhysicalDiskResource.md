---
description: Start-ClusterPhysicalDiskResource
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 07/26/2022
online version: https://docs.microsoft.com/powershell/module/failoverclusters/start-clusterphysicaldiskresource?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-ClusterPhysicalDiskResource
---

# Start-ClusterPhysicalDiskResource

## SYNOPSIS
Starts a physical disk resource within a failover cluster.

## SYNTAX

```
Start-ClusterPhysicalDiskResource [[-Name] <String>] [-RecoveryPassword <StringCollection>]
 [-RecoveryKeyPath <StringCollection>] [-Wait <Int32>] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The `Start-ClusterPhysicalDiskResource` cmdlet brings a physical disk online in a failover cluster.

## EXAMPLES

### Example 1
```powershell
{{ Add example code here }}
```

{{ Add example description here }}

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
Specifies the name of the physical disk resource to bring online.

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
{{ Fill Name Description }}

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

### -RecoveryKeyPath
{{ Fill RecoveryKeyPath Description }}

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

### -RecoveryPassword
{{ Fill RecoveryPassword Description }}

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Management.Automation.PSObject

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.ClusterSharedVolume

## NOTES

## RELATED LINKS

[https://go.microsoft.com/fwlink/?LinkId=216254](https://go.microsoft.com/fwlink/?LinkId=216254)

