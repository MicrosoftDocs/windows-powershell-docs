---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
ms.date: 10/21/2022
online version: https://learn.microsoft.com/powershell/module/failoverclusters/set-clusterlog?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ClusterLog
---

# Set-ClusterLog

## SYNOPSIS
Sets the size and level of detail for the cluster log.

## SYNTAX

```
Set-ClusterLog [-Size <Int32>] [-Level <Int32>] [-InputObject <PSObject>] [-Cluster <String>]
 [<CommonParameters>]
```

## DESCRIPTION

The `Set-ClusterLog` cmdlet sets the size and level of detail for the cluster log. The default
level, `3`, includes errors, warnings, and additional information.

## EXAMPLES

### Example 1

```powershell
Set-ClusterLog -Level 1
```

This example sets the cluster log to a detail level of `1`.

### Example 2

```powershell
Set-ClusterLog -Size 1024
```

This example sets the cluster log size to 1024 MB.

## PARAMETERS

### -Cluster

Specifies the name of the cluster on which to run this cmdlet. If the input for this parameter is
`.` or it is omitted, then the cmdlet runs on the local cluster.

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

Specifies the cluster from which to generate cluster logs.

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

### -Level

Specifies the log level to set for the cluster. The acceptable values for this parameter are: `0`
to `5`.

| Level  | Error  | Warning  | Info  | Verbose | Debug |
|:-----|:-----|:-----|:-----|:-----|:-----|
|0 (Disabled) ||||||
|1 |&#x2714;||||
|2 |&#x2714;|&#x2714;|||
|3 (Default) |&#x2714;|&#x2714;|&#x2714;||
|4 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|5 |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|

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

### -Size

Specifies the log size to set for the cluster. The acceptable values for this parameter in Windows
2016 are: `8` MB to `1024` MB. The acceptable values for this parameter in Windows 2019 are:
`8` MB to `2048` MB.

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
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## NOTES

## RELATED LINKS

[Get-ClusterLog](./Get-ClusterLog.md)
