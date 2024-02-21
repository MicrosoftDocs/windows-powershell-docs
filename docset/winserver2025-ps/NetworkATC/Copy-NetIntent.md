---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 02/21/2024
online version: https://learn.microsoft.com/powershell/module/networkatc/copy-netintent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-NetIntent
---

# Copy-NetIntent

## SYNOPSIS
Moves (or copies) net intent across different hosts or clusters

## SYNTAX

### LocalToLocal (Default)

```
Copy-NetIntent [[-Name] <String>] [-SourceComputerName] <String> [-DestinationComputerName] <String>
 [-RemoveSource <Boolean>] [-Wait] [<CommonParameters>]
```

### ClusterToCluster

```
Copy-NetIntent [[-Name] <String>] [-SourceClusterName] <String> [-DestinationClusterName] <String>
 [-RemoveSource <Boolean>] [-Wait] [<CommonParameters>]
```

### ClusterToLocal

```
Copy-NetIntent [[-Name] <String>] [-SourceClusterName] <String> [-DestinationComputerName] <String>
 [-RemoveSource <Boolean>] [-Wait] [<CommonParameters>]
```

### LocalToCluster

```
Copy-NetIntent [[-Name] <String>] [-SourceComputerName] <String> [-DestinationClusterName] <String>
 [-RemoveSource <Boolean>] [-Wait] [<CommonParameters>]
```

### GlobalClusterToLocal

```
Copy-NetIntent [-GlobalOverrides] [-SourceClusterName] <String> [-DestinationComputerName] <String>
 [-RemoveSource <Boolean>] [-Wait] [<CommonParameters>]
```

### GlobalClusterToCluster

```
Copy-NetIntent [-GlobalOverrides] [-SourceClusterName] <String> [-DestinationClusterName] <String>
 [-RemoveSource <Boolean>] [-Wait] [<CommonParameters>]
```

### GlobalLocalToCluster

```
Copy-NetIntent [-GlobalOverrides] [-SourceComputerName] <String> [-DestinationClusterName] <String>
 [-RemoveSource <Boolean>] [-Wait] [<CommonParameters>]
```

### GlobalLocalToLocal

```
Copy-NetIntent [-GlobalOverrides] [-SourceComputerName] <String> [-DestinationComputerName] <String>
 [-RemoveSource <Boolean>] [-Wait] [<CommonParameters>]
```

## DESCRIPTION

{{ Fill in the Description }}

## EXAMPLES

### EXAMPLE 1

```
Copy-NetIntent
```

## PARAMETERS

### -DestinationClusterName

The name of the cluster that the intent is copied to.

```yaml
Type: System.String
Parameter Sets: ClusterToCluster, LocalToCluster, GlobalClusterToCluster, GlobalLocalToCluster
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationComputerName

The name of the computer that the intent is copied to.

```yaml
Type: System.String
Parameter Sets: LocalToLocal, ClusterToLocal, GlobalClusterToLocal, GlobalLocalToLocal
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalOverrides

{{ Fill GlobalOverrides Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: GlobalClusterToLocal, GlobalClusterToCluster, GlobalLocalToCluster, GlobalLocalToLocal
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name

The name of the intent to be copied.

```yaml
Type: System.String
Parameter Sets: LocalToLocal, ClusterToCluster, ClusterToLocal, LocalToCluster
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -RemoveSource

Indicates that the source needs to be removed after the copy.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceClusterName

The name of the cluster that the intent is copied from.

```yaml
Type: System.String
Parameter Sets: ClusterToCluster, ClusterToLocal, GlobalClusterToLocal, GlobalClusterToCluster
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceComputerName

The name of the computer that the intent is copied from.

```yaml
Type: System.String
Parameter Sets: LocalToLocal, LocalToCluster, GlobalLocalToCluster, GlobalLocalToLocal
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

{{ Fill Wait Description }}

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

The copy & removal operation of the intent is not a transacted operation\`.

## RELATED LINKS
