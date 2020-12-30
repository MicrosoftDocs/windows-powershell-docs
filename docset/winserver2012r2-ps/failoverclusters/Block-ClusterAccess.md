---
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
Module Name: FailoverClusters
online version: 
schema: 2.0.0
title: Block-ClusterAccess
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/30/2017
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 497979FE-F7A1-49A7-B1BB-000D83D54E84
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
If you do not want to completely block access and instead want to limit a user to using Windows PowerShell® to view cluster settings (not change settings), then use the Grant-ClusterAccess cmdlet with the **Readonly** parameter.

## EXAMPLES

### Example 1
```
PS C:\>Block-ClusterAccess -User contoso\johnj99
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-ClusterAccess](./Get-ClusterAccess.md)

[Grant-ClusterAccess](./Grant-ClusterAccess.md)

[Remove-ClusterAccess](./Remove-ClusterAccess.md)

