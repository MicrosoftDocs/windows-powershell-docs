---
external help file: ClusterAwareUpdating.dll-Help.xml
Module Name: ClusterAwareUpdating
online version: 
schema: 2.0.0
title: Test-CauSetup
ms.author: v-anbarr
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 540A8005-6F06-46B8-A97D-1EFF34CE7B6C
---

# Test-CauSetup

## SYNOPSIS
Tests whether a cluster is properly set up to apply software updates using Cluster-Aware Updating (CAU).

## SYNTAX

```
Test-CauSetup [[-ClusterName] <String>] [[-Credential] <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-CauSetup** cmdlet tests whether a failover cluster is properly set up to apply software updates using Cluster-Aware Updating (CAU).
The cmdlet performs a Best Practices Analyzer (BPA) scan of the failover cluster and network environment by invoking the ClusterAwareUpdating BPA model that is installed with CAU.
To view the results of a BPA scan that is performed by **Test-CauSetup**, including possible problems and resolution steps, run the **Get-BpaResult** cmdlet.

Note: You must run **Test-CauSetup** with local administrative credentials.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Test-CauSetup -ClusterName CONTOSO-FC1
Test-CauSetup completed successfully. To view the results, run the "Get-BpaResult Microsoft/Windows/ClusterAwareUpdating" Windows PowerShell cmdlet.
```

This example tests whether failover cluster CONTOSO-FC1 is properly set up for CAU.

## PARAMETERS

### -ClusterName
Specifies the name of the cluster on which to test for proper setup.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.ClusterAwareUpdating.CauBpaProgress

## NOTES

## RELATED LINKS

[Invoke-BpaModel](http://technet.microsoft.com/library/ee617290.aspx)

[Get-BpaResult](http://technet.microsoft.com/library/ee617286.aspx)

