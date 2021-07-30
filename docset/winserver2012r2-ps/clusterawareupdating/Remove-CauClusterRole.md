---
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/clusterawareupdating/remove-cauclusterrole?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CauClusterRole
---

# Remove-CauClusterRole

## SYNOPSIS
Removes the Cluster-Aware Updating (CAU) clustered role from the specified failover cluster.

## SYNTAX

```
Remove-CauClusterRole [[-ClusterName] <String>] [[-Credential] <PSCredential>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-CauClusterRole** cmdlet removes the Cluster-Aware Updating (CAU) clustered role from the specified failover cluster.
To run CAU from a cluster, ensure that the CAU clustered role is configured in that cluster.

Note: The **Remove-CauClusterRole** cmdlet removes the virtual computer object (VCO) in Active Directory for the CAU clustered role, unless you previously prestaged or specified the VCO by running the **Add-CauClusterRole** cmdlet with the **VirtualComputerObjectName** parameter.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Remove-CauClusterRole -ClusterName CONTOSO-FC1 -Force
```

This example removes the instance of the CAU clustered role that is configured on the cluster named CONTOSO-FC1.
The example runs without displaying confirmation prompts.

## PARAMETERS

### -ClusterName
Specifies the name of the cluster from which to remove the CAU clustered role.
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
Position: 1
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
Aliases: f

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Add-CauClusterRole](./Add-CauClusterRole.md)

[Disable-CauClusterRole](./Disable-CauClusterRole.md)

[Enable-CauClusterRole](./Enable-CauClusterRole.md)

[Get-CauClusterRole](./Get-CauClusterRole.md)

[Set-CauClusterRole](./Set-CauClusterRole.md)

