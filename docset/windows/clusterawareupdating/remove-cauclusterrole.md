---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ClusterAwareUpdating.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-CauClusterRole
ms.reviewer:
ms.assetid: 0B25A6D2-2FEB-468B-A8AC-9970D818FCA8
---

# Remove-CauClusterRole

## SYNOPSIS
Removes the CAU clustered role from the specified failover cluster.

## SYNTAX

```
Remove-CauClusterRole [[-ClusterName] <String>] [[-Credential] <PSCredential>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-CauClusterRole** cmdlet removes the Cluster-Aware Updating (CAU) clustered role from the specified failover cluster.
To run CAU from a cluster, ensure that the CAU clustered role is configured in that cluster.

The **Remove-CauClusterRole** cmdlet removes the virtual computer object (VCO) in Active Directory for the CAU clustered role, unless you previously prestaged or specified the VCO by using the **Add-CauClusterRole** cmdlet with the *VirtualComputerObjectName* parameter.

## EXAMPLES

### Example 1: Remove an instance of a CAU clustered role configured on the specified cluster
```
PS C:\> Remove-CauClusterRole -ClusterName "CONTOSO-FC1" -Force
```

This command removes the instance of the CAU clustered role that is configured on the cluster named CONTOSO-FC1.
Because the command specifies the *Force* parameter, the cmdlet runs without displaying confirmation prompts.

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
Forces the command to run without asking for user confirmation.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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

