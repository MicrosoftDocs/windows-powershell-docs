---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/start-networkatc?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-NetworkAtc
---

# Start-NetworkAtc

## SYNOPSIS
Starts the Network ATC service on specified hosts.

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

The `Start-NetworkATC` cmdlet starts the ATC service on all hosts for a cluster or a given single
node.

## EXAMPLES

### Example 1

```powershell
Start-NetworkAtc -ComputerName "Server01"
```

This example starts the Network ATC service on the host specified by the computer name `Server01`.

## PARAMETERS

### -ComputerName

Specifies the name of the computer on which to start the Network ATC service.

```yaml
Type: String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName

Specifies the name of the cluster on which to start the Network ATC service on all hosts.

```yaml
Type: String
Parameter Sets: Cluster
Aliases:

Required: True
Position: 1
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Stop-NetworkAtc](Stop-NetworkAtc.md)
