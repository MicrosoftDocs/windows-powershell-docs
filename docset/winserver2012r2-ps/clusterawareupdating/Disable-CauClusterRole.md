---
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/clusterawareupdating/disable-cauclusterrole?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-CauClusterRole
---

# Disable-CauClusterRole

## SYNOPSIS
Suspends the self-updating functionality on the specified cluster.

## SYNTAX

```
Disable-CauClusterRole [[-ClusterName] <String>] [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Disable-CauClusterRole** suspends the self-updating functionality on the specified cluster.
The self-updating functionality of the cluster can be re-enabled with the Enable-CauClusterRole cmdlet.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Disable-CauClusterRole -ClusterName CONTOSO-FC1 -Force
```

This example prevents the CAU clustered role on the CONTOSO-FC1 cluster from performing Updating Runs.
The cmdlet changes the status of the CAU clustered role to Offline.
The cmdlet runs without displaying confirmation prompts.

## PARAMETERS

### -ClusterName
Specifies the name of the cluster on which to disable the self-updating functionality.
This parameter is only required when this cmdlet is not run on a failover cluster node, or this cmdlet is used to reference a failover cluster different from where the cmdlet is run.

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
Runs the cmdlet without prompting for confirmation.
By default the cmdlet will ask for confirmation from the user before proceeding.

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
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Enable-CauClusterRole](./Enable-CauClusterRole.md)

[Get-CauClusterRole](./Get-CauClusterRole.md)

[Remove-CauClusterRole](./Remove-CauClusterRole.md)

[Set-CauClusterRole](./Set-CauClusterRole.md)

