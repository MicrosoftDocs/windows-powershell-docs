---
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 03/14/2025
online version: https://learn.microsoft.com/powershell/module/networkatc/get-allnetintents?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AllNetIntents
---

# Get-AllNetIntents

## SYNOPSIS
Looks up all intent request configurations available.

## SYNTAX

```
Get-AllNetIntents [[-ClusterName] <String>] [[-ComputerName] <String>] [-GlobalOverrides]
 [<CommonParameters>]
```

## DESCRIPTION

The `Get-AllNetIntents` cmdlet retrieves all network intent configurations
available based on the computer name or cluster name.

## EXAMPLES

### Example 1

```powershell
Get-AllNetIntents -ComputerName "Server01"
```

This example retrieves all network intent configurations from the `Server01` standalone host.

## PARAMETERS

### -ClusterName

Specifies the name of the cluster for which the network intent is to be
retrieved. When used, the intent "floats" across the cluster.

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

Specifies the computer name of the target host on which the network
intent configuration is to be retrieved. For standalone hosts, use the local
computer name; for scenarios where the script is executed remotely, ensure the
current user has administrative privileges on the target machine.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GlobalOverrides

Retrieves the global override settings.

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

## RELATED LINKS
