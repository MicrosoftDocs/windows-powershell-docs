---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/remove-netintent?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-NetIntent
---

# Remove-NetIntent

## SYNOPSIS
Removes the requested network intent.

## SYNTAX

### ComputerName (Default)

```
Remove-NetIntent [-Name] <String> [[-ComputerName] <String>] [-SkipServiceStop <Boolean>]
 [<CommonParameters>]
```

### Cluster

```
Remove-NetIntent [-Name] <String> [-ClusterName] <String> [-SkipServiceStop <Boolean>]
 [<CommonParameters>]
```

### Global

```
Remove-NetIntent [-GlobalOverrides] [-SkipServiceStop <Boolean>] [<CommonParameters>]
```

## DESCRIPTION

The `Remove-NetIntent` cmdlet removes the specified network intent.

- For clusters, if `-ClusterName` is specified, the removal affects all nodes within the given
  cluster.
- For standalone nodes, only the network intents for the specified node will be removed.

Note that `Remove-NetIntent` does not remove the provisioning on the target hosts. The device
administrator must manually remove any old intent configurations from the node.

## EXAMPLES

### Example 1

```powershell
Remove-NetIntent -Name "MyIntent" -ComputerName "Server01"
```

This example removes the network intent named `MyIntent` from the standalone computer `Server01`.

## PARAMETERS

### -Name

Specifies the name of the network intent to be removed.

```yaml
Type: String
Parameter Sets: ComputerName, Cluster
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies the name of the computer from which the network intent should be removed.

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

Specifies the name of the cluster from which the network intent should be removed. The removal will
affect all nodes in the specified cluster.

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

Indicates that global overrides should be removed. This affects all configurations using these
global overrides.

```yaml
Type: SwitchParameter
Parameter Sets: Global
Aliases:

Required: False
Position: 2
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipServiceStop

Specifies whether to skip stopping the service during the removal process. If set to `$true`, the
service will not be stopped.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
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

[Get-NetIntent](Get-NetIntent.md)

[Get-NetIntentStatus](Get-NetIntentStatus.md)

[Set-NetIntent](Set-NetIntent.md)
