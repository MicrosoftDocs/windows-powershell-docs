---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 09/27/2022
online version: https://learn.microsoft.com/powershell/module/clusterawareupdating/enable-cauclusterrole?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-CauClusterRole
---

# Enable-CauClusterRole

## SYNOPSIS
Re-enables the self-updating functionality on the specified cluster.

## SYNTAX

```
Enable-CauClusterRole [[-ClusterName] <String>] [-Credential <PSCredential>] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Enable-CauClusterRole` cmdlet re-enables the self-updating functionality on the specified
cluster. The self-updating functionality of the cluster can be disabled with the
`Disable-CauClusterRole` cmdlet.

## EXAMPLES

### Example 1: Enable a CAU clustered role on the specified cluster

```powershell
Enable-CauClusterRole -ClusterName "CONTOSO-FC1" -Force
```

This command enables the CAU clustered role on the CONTOSO-FC1 cluster to begin performing Updating
Runs. The cmdlet changes the status of the CAU clustered role to Running. Because the command
specified the **Force** parameter, the cmdlet runs without displaying confirmation prompts.

## PARAMETERS

### -ClusterName

Specifies the name of the cluster on which to enable the self-updating functionality. This parameter
is only required when this cmdlet isn't run on a failover cluster node, or this cmdlet is used to
reference a failover cluster different from where the cmdlet is run.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the administrative credentials for the target cluster.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet isn't run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-CauClusterRole](./Add-CauClusterRole.md)

[Disable-CauClusterRole](./Disable-CauClusterRole.md)

[Get-CauClusterRole](./Get-CauClusterRole.md)

[Remove-CauClusterRole](./Remove-CauClusterRole.md)

[Set-CauClusterRole](./Set-CauClusterRole.md)

