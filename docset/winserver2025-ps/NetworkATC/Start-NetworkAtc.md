---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkatc/start-networkatc?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-NetworkAtc
---

# Start-NetworkAtc

## SYNOPSIS
Starts the Atc Service on all hosts for a cluster or a given single node.

## SYNTAX

### ComputerName (Default)

```
Start-NetworkAtc [[-ComputerName] <String>] [<CommonParameters>]
```

### Cluster

```
Start-NetworkAtc [-ClusterName] <String> [<CommonParameters>]
```

## DESCRIPTION

Starts the Atc Service on all hosts for a cluster or a given single node.

## EXAMPLES

### Example 1

```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -ClusterName

{{ Fill ClusterName Description }}

```yaml
Type: System.String
Parameter Sets: Cluster
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

{{ Fill ComputerName Description }}

```yaml
Type: System.String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 1
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

## OUTPUTS

## NOTES

## RELATED LINKS
