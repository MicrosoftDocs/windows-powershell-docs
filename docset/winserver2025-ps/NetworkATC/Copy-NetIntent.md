---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/copy-netintent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-NetIntent
---

# Copy-NetIntent

## SYNOPSIS
Moves or copies network intents across different hosts or clusters.

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

The `Copy-NetIntent` cmdlet copies or moves a network intent from one host or
cluster to another. The source intent is removed if the **RemoveSource**
parameter is provided.

## EXAMPLES

### EXAMPLE 1

```powershell
Copy-NetIntent -Name "MyIntent" -SourceComputerName "Server01" -DestinationComputerName "Server02"
```

This example copies a network intent from the standalone device `Server01` to
the standalone destination device `Server02`.

## PARAMETERS

### -Name

Defines a unique name that identifies the network intent. Since intents are
uniquely determined by their list of physical adapters, the name is used as an
identifier to ensure that each intent is distinct.

```yaml
Type: String
Parameter Sets: LocalToLocal, ClusterToCluster, ClusterToLocal, LocalToCluster
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -GlobalOverrides

Specifies that global override settings during the copy operation for any local
settings.

```yaml
Type: SwitchParameter
Parameter Sets: GlobalClusterToLocal, GlobalClusterToCluster, GlobalLocalToCluster, GlobalLocalToLocal
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SourceComputerName

Specifies the name of the source computer that holds the network intent to be copied.

```yaml
Type: String
Parameter Sets: LocalToLocal, LocalToCluster, GlobalLocalToCluster, GlobalLocalToLocal
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceClusterName

Specifies the name of the source cluster that contains the network intent to be copied.

```yaml
Type: String
Parameter Sets: ClusterToCluster, ClusterToLocal, GlobalClusterToLocal, GlobalClusterToCluster
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationComputerName

Specifies the name of the destination computer where the network intent is to be copied.

```yaml
Type: String
Parameter Sets: LocalToLocal, ClusterToLocal, GlobalClusterToLocal, GlobalLocalToLocal
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationClusterName

Specifies the name of the destination cluster to which the network intent is to be copied.

```yaml
Type: String
Parameter Sets: ClusterToCluster, LocalToCluster, GlobalClusterToCluster, GlobalLocalToCluster
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSource

Indicates whether the original network intent should be removed from the source
after the copy operation is completed.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

When specified, the command will wait for the network configuration commands to
complete or for status confirmation before returning control.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction,
-ErrorVariable, -InformationAction, -InformationVariable, -OutVariable,
-OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.
For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

## OUTPUTS

## NOTES

The copy and removal operation of the intent isn't a transacted operation.

## RELATED LINKS

- [Add-NetIntent](Add-NetIntent.md)

- [Get-NetIntent](Get-NetIntent.md)

- [Get-NetIntentStatus](Get-NetIntentStatus.md)

- [Remove-NetIntent](Remove-NetIntent.md)

- [Set-NetIntent](Set-NetIntent.md)
