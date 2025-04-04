---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/get-netintent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetIntent
---

# Get-NetIntent

## SYNOPSIS
Gets the current set of intents configured on the node or cluster.

## SYNTAX

### ComputerName (Default)

```
Get-NetIntent [[-ComputerName] <String>] [-Name <String>] [-GlobalOverrides] [<CommonParameters>]
```

### Cluster

```
Get-NetIntent [-ClusterName] <String> [-Name <String>] [-GlobalOverrides] [<CommonParameters>]
```

## DESCRIPTION

The `Get-NetIntent` cmdlet retrieves the current network intents that have been configured either on
a standalone host or a cluster.

## EXAMPLES

### Example 1

```powershell
Get-NetIntent -ComputerName "Server01" -Name "MyIntent"
```

This example retrieves the network intent `MyIntent` on the standalone host `Server01`.

## PARAMETERS

### -ComputerName

Specifies the computer name of the target host on which the network intent configuration will be
applied. For standalone hosts, use the local computer name; for scenarios where the script is
executed remotely, ensure the current user has administrative privileges on the target machine.

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

Specifies the name of the cluster for which the network intent is being defined. When used, the
intent "floats" across the cluster. Any node with matching physical adapter names will automatically
apply the intended configuration.

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

### -Name

Defines a unique name that identifies the network intent. Since intents are uniquely determined by
their list of physical adapters, the name is used as an identifier to ensure that each intent is
distinct.

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

### -GlobalOverrides

Retrieves the global override settings of the network intent.

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

[Add-NetIntent](Add-NetIntent.md)

[Copy-NetIntent](Copy-NetIntent.md)

[Get-NetIntentStatus](Get-NetIntentStatus.md)

[Remove-NetIntent](Remove-NetIntent.md)

[Set-NetIntent](Set-NetIntent.md)
