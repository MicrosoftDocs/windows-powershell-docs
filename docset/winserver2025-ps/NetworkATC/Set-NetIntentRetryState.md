---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/set-netintentretrystate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetIntentRetryState
---

# Set-NetIntentRetryState

## SYNOPSIS
Changes the provisioning state of the goal state for the network intent on a given host.

## SYNTAX

### ComputerName (Default)

```
Set-NetIntentRetryState [-ComputerName <String>] -Name <String> [-Wait] [<CommonParameters>]
```

### Global

```
Set-NetIntentRetryState [-ClusterName <String>] [-ComputerName <String>] [-NodeName <String>]
 [-Wait] [-GlobalOverrides] [<CommonParameters>]
```

### Cluster

```
Set-NetIntentRetryState [-ClusterName <String>] -Name <String> -NodeName <String> [-Wait]
 [<CommonParameters>]
```

## DESCRIPTION

The `Set-NetIntentRetryState` cmdlet changes the provisioning state of the goal
state for a network intent on a given host. This is useful for resetting failed
provisioning attempts, as it resets the **RetryRequired** state.

## EXAMPLES

### Example 1

```powershell
Set-NetIntentRetryState -ComputerName "Server01" -Name "MyIntent" -Wait
```

This example resets the provisioning state for the network intent named
`MyIntent` on the computer `Server01` and waits for the operation to complete.

## PARAMETERS

### -ClusterName

Specifies the name of the cluster.

```yaml
Type: String
Parameter Sets: Global, Cluster
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

Specifies the name of the computer.

```yaml
Type: String
Parameter Sets: ComputerName, Global
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

Specifies the name of the network intent to be reset.

```yaml
Type: String
Parameter Sets: ComputerName, Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeName

Specifies the name of the node within the cluster.

```yaml
Type: String
Parameter Sets: Global
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

Indicates that the cmdlet should wait for the operation to complete before
returning control to the command line.

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

### -GlobalOverrides

Indicates the global overrides that should be applied when resetting the provisioning state.

```yaml
Type: SwitchParameter
Parameter Sets: Global
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

## RELATED LINKS
