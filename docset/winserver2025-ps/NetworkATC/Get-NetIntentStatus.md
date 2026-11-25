---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/new-netintentstatus?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetIntentStatus
---

# Get-NetIntentStatus

## SYNOPSIS
Displays the consolidated status of all the intent configurations for a node or across multiple nodes in a cluster.

## SYNTAX

### ComputerName (Default)

```
Get-NetIntentStatus [[-Name] <String>] [[-ComputerName] <String>] [-GlobalOverrides]
 [<CommonParameters>]
```

### Cluster

```
Get-NetIntentStatus [[-Name] <String>] [-ClusterName] <String> [-GlobalOverrides]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-NetIntentStatus` cmdlet retrieves the status of all the network intent
configurations for a standalone host or a cluster.

## EXAMPLES

### Example 1

```powershell
Get-NetIntentStatus -Name "MyIntent" -ComputerName "Server01"
```

This example retrieves the status of the network intent configuration `MyIntent`
for the computer named `Server01`.

## PARAMETERS

### -Name

Defines a unique name that identifies the network intent. Since intents are uniquely determined by
their list of physical adapters, the name is used as an identifier to ensure that each intent is
distinct.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies the computer name of the target host on which the network intent status is to be
retrieved. For standalone hosts, use the local computer name; for scenarios where the script is
executed remotely, ensure the current user has administrative privileges on the target machine.

```yaml
Type: String
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName

Specifies the name of the cluster for which the network intent status is to be retrieved. When used,
the intent "floats" across the cluster. Any node with matching physical adapter names will
automatically apply the intended configuration.

```yaml
Type: String
Parameter Sets: Cluster
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalOverrides

Retrieves the global override settings of the network intent status.

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

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-NetIntent](Get-NetIntent.md)
