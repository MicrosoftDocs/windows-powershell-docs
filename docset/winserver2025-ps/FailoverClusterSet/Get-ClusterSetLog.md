---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusterSet
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/failoverclusterset/get-clustersetlog?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ClusterSetLog
---

# Get-ClusterSetLog

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### InputObject (Default)
```
Get-ClusterSetLog [-Node <StringCollection>] [-IncludeClusterLog] [-IncludeManagementClusterLog]
 [-TimeSpanInMinutes <UInt32>] [-DestinationFolderPath <String>] [-UseLocalTime] [-SkipClusterSetState]
 [-NoCollateLogs] [<CommonParameters>]
```

### ClusterSetCimSession
```
Get-ClusterSetLog [-ClusterSetCimSession <CimSession>] [-Node <StringCollection>] [-IncludeClusterLog]
 [-IncludeManagementClusterLog] [-TimeSpanInMinutes <UInt32>] [-DestinationFolderPath <String>] [-UseLocalTime]
 [-SkipClusterSetState] [-NoCollateLogs] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -ClusterSetCimSession
{{ Fill ClusterSetCimSession Description }}

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: ClusterSetCimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DestinationFolderPath
{{ Fill DestinationFolderPath Description }}

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Destination

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeClusterLog
{{ Fill IncludeClusterLog Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeManagementClusterLog
{{ Fill IncludeManagementClusterLog Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoCollateLogs
{{ Fill NoCollateLogs Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
{{ Fill Node Description }}

```yaml
Type: System.Collections.Specialized.StringCollection
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipClusterSetState
Generate the cluster set log without retrieving cluster set state information.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: scs

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TimeSpanInMinutes
{{ Fill TimeSpanInMinutes Description }}

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: TimeSpan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseLocalTime
Generate the cluster log using local time instead of GMT.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: lt

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimSession

## OUTPUTS

### System.IO.FileInfo

## NOTES

## RELATED LINKS

[https://go.microsoft.com/fwlink/?LinkId=216212](https://go.microsoft.com/fwlink/?LinkId=216212)

