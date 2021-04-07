---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
manager: jasgro
Module Name: FailoverClusters
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/failoverclusters/block-clusteraccess?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Block-ClusterAccess
---

# Block-ClusterAccess

## SYNOPSIS
Prevents the specified user or users from accessing a failover cluster.

## SYNTAX

```
Block-ClusterAccess [-User] <StringCollection> [-InputObject <PSObject>] [-Cluster <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Block-ClusterAccess** cmdlet prevents the specified user or users from accessing a failover cluster.
If you do not want to completely block access and instead want to limit a user to using Windows PowerShell® to view cluster settings (not change settings), then use the **Grant-ClusterAccess** cmdlet with the **Readonly** parameter.

## EXAMPLES

### Example 1
```
PS C:\> Block-ClusterAccess -User contoso\johnj99
```

This example prevents the user named johnj99 on the contoso domain from gaining access to the local cluster.

## PARAMETERS

### -Cluster
Specifies the name of the cluster on which to run this cmdlet.
If the input for this parameter is `.` or it is omitted, then the cmdlet runs on the local cluster.

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

### -InputObject
Specifies the cluster on which to block access for the given user.

```yaml
Type: PSObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -User
Specifies the user for whom to block cluster access.

```yaml
Type: StringCollection
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-ClusterAccess](./Get-ClusterAccess.md)

[Grant-ClusterAccess](./Grant-ClusterAccess.md)

[Remove-ClusterAccess](./Remove-ClusterAccess.md)

