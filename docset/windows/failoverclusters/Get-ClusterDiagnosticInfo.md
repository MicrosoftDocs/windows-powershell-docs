---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-kaunu
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: 
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-ClusterDiagnosticInfo
ms.reviewer:
ms.assetid: 540818BC-21E2-4CFC-BDD0-5E18EFC43EEC
---

# Get-ClusterDiagnosticInfo

## SYNOPSIS
Gets diagnostics for a cluster a cluster that contains VMs and produces a zip file containing the data.

## SYNTAX

### Write
```
Get-ClusterDiagnosticInfo [[-WriteToPath] <String>] [[-Cluster] <String>] [[-ZipPrefix] <String>]
 [-HoursOfEvents <Int32>] [-IncludeEvents] [<CommonParameters>]
```

### Read
```
Get-ClusterDiagnosticInfo -ReadFromPath <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-ClusterDiagnosticInfo** cmdlet gets diagnostics for a cluster that contains virtual machines and produces a zip file containing the data.

## EXAMPLES

### Example 1: Write diagnostic info to the specified path
```
PS C:\> Get-ClusterDiagnosticInfo -WriteToPath "C:\Users\MyUser\HealthTest\"
Writing to path : C:\Users\MyUser\HealthTest\
```

This command gets and writes the cluster Diagnostics to the folder C:\Users\MyUser\HealthTest\.

## PARAMETERS

### -Cluster
Specifies the name of the cluster the cmdlet gets.

```yaml
Type: String
Parameter Sets: Write
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HoursOfEvents
Specifies the number of hours in the past that this cmdlet gathers system event logs.

```yaml
Type: Int32
Parameter Sets: Write
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeEvents
Indicates that this cmdlet gathers system event logs.

```yaml
Type: SwitchParameter
Parameter Sets: Write
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReadFromPath
Specifies the path to read from when examining previously collected log files.

```yaml
Type: String
Parameter Sets: Read
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WriteToPath
Specifies the path to create the ZIP file that contains all of the logs.

```yaml
Type: String
Parameter Sets: Write
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ZipPrefix
Specifies the name to prepend to the ZIP file that is produced.

```yaml
Type: String
Parameter Sets: Write
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Failover Clusters](./failoverclusters.md)

