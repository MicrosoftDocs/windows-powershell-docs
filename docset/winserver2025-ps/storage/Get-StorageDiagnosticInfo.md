---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: StorageScripts-help.xml
Module Name: Storage
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/storage/get-storagediagnosticinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-StorageDiagnosticInfo
---

# Get-StorageDiagnosticInfo

## SYNOPSIS
Gets Storage diagnostic information.

## SYNTAX

### ByStorageSubSystem
```
Get-StorageDiagnosticInfo -InputObject <CimInstance> -DestinationPath <String> [-TimeSpan <UInt32>]
 [-ActivityId <String>] [-ExcludeOperationalLog] [-ExcludeDiagnosticLog] [-IncludeLiveDump]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystemFriendlyName
```
Get-StorageDiagnosticInfo [-StorageSubSystemFriendlyName] <String> -DestinationPath <String>
 [-TimeSpan <UInt32>] [-ActivityId <String>] [-ExcludeOperationalLog] [-ExcludeDiagnosticLog]
 [-IncludeLiveDump] [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystemName
```
Get-StorageDiagnosticInfo -StorageSubSystemName <String> -DestinationPath <String> [-TimeSpan <UInt32>]
 [-ActivityId <String>] [-ExcludeOperationalLog] [-ExcludeDiagnosticLog] [-IncludeLiveDump]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByStorageSubSystemUniqueId
```
Get-StorageDiagnosticInfo -StorageSubSystemUniqueId <String> -DestinationPath <String> [-TimeSpan <UInt32>]
 [-ActivityId <String>] [-ExcludeOperationalLog] [-ExcludeDiagnosticLog] [-IncludeLiveDump]
 [-CimSession <CimSession>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-StorageDiagnosticInfo** cmdlet gets Storage event logs, trace logs (if present), and live dumps of all nodes in the specified Storage subsystem.
Event logs are gathered into one .evtx file per machine, and trace logs are gathered in .etw format.
The cmdlet copies this information to path specified by the *DestinationPath* parameter.

By default, this cmdlet gathers information for the past 24 hours.
To specify a different number of hours, use the *TimeSpan* parameter.

## EXAMPLES

### Example 1: Get all logs and dumps for a cluster subsystem
```
PS C:\>Get-StorageDiagnosticInfo -StorageSubSystemName "VMMCluster.contoso.corp.microsoft.com" -DestinationPath "\\FileShare1\Debug\"
```

This command gets all types of logs and dumps for the specified Storage cluster subsystem.

## PARAMETERS

### -ActivityId


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

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -CimSession


```yaml
Type: CimSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationPath


```yaml
Type: String
Parameter Sets: (All)
Aliases: Path

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeDiagnosticLog


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

### -ExcludeOperationalLog


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

### -IncludeLiveDump


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
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance
Parameter Sets: ByStorageSubSystem
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystemFriendlyName


```yaml
Type: String
Parameter Sets: ByStorageSubSystemFriendlyName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageSubSystemName


```yaml
Type: String
Parameter Sets: ByStorageSubSystemName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageSubSystemUniqueId


```yaml
Type: String
Parameter Sets: ByStorageSubSystemUniqueId
Aliases: StorageSubSystemId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit


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

### -TimeSpan


```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

* When used in Failover Cluster, cmdlets from the Storage module operate on cluster level (all servers in the cluster).

## RELATED LINKS

