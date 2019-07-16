---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.FailoverClusters.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-ClusterCheckpoint
ms.reviewer:
ms.assetid: 4C3E1376-B8DE-4B3E-87F3-E351F369E314
---

# Add-ClusterCheckpoint

## SYNOPSIS
Adds a cryptographic key checkpoint or registry checkpoint for a resource.

## SYNTAX

```
Add-ClusterCheckpoint [[-ResourceName] <String>] [-CryptoCheckpointName <String>]
 [-CryptoCheckpointType <String>] [-CryptoCheckpointKey <String>] [-RegistryCheckpoint <String>]
 [-InputObject <PSObject>] [-Cluster <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-ClusterCheckpoint** cmdlet adds a cryptographic key checkpoint or registry checkpoint for a resource.

Checkpoints help provide failover support for applications that store configuration information locally instead of or in addition to storing information in the cluster configuration database.
Applications might store information locally in two ways.
One way is to store configuration information in the registry on the local server; another way is to use cryptographic keys on the local server.

## EXAMPLES

### Example 1: Add registry checkpoint
```
PS C:\> Add-ClusterCheckpoint -ResourceName "Cluster Name" -RegistryCheckpoint "software\clusname"
Resource                                                    Name 
--------                                                    ---- 
Cluster Name                                                software\clusname
```

This example adds a registry checkpoint called software\clusname for the resource named cluster name.

### Example 2: Add cryptographic checkpoint
```
PS C:\> Get-ClusterResource -Name "Cluster Name" | Add-ClusterCheckpoint -CryptoCheckpointName "Microsoft Base Cryptographic Provider v1.0"  -CryptoCheckpointType 1 -CryptoCheckpointKey "Crypto"
Resource                      Name                          Type                          Key 
--------                      ----                          ----                          --- 
Cluster Name                  Microsoft Base Cryptograph... 1                             Crypto
```

This example adds a cryptographic checkpoint for the resource named Cluster Name.

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

### -CryptoCheckpointKey
Specifies the key of a cryptographic key checkpoint to add.

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

### -CryptoCheckpointName
Specifies the name of a cryptographic key checkpoint to add.

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

### -CryptoCheckpointType
Specifies the type of a cryptographic key checkpoint to add.
Options depend on the cryptographic provider.

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

### -InputObject
Specifies the cluster on which to run the cmdlet or the cluster resource for which the checkpoint should be added.

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

### -RegistryCheckpoint
Specifies the name of the registry checkpoint to add.

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

### -ResourceName
Specifies the resource for which a checkpoint should be added.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.FailoverClusters.PowerShell.Cluster

### Microsoft.FailoverClusters.PowerShell.ClusterResource

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-ClusterCheckpoint](./Get-ClusterCheckpoint.md)

[Get-ClusterResource](./Get-ClusterResource.md)

[Remove-ClusterCheckpoint](./Remove-ClusterCheckpoint.md)

