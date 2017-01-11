---
author: brianlic-msft
description: 
external help file: ClusterStorageSpacesDirect.cdxml-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-ClusterStorageSpacesDirect
ms.assetid: 673957AC-F14D-4DD3-9D16-81BDF98A6CCD
---

# Get-ClusterStorageSpacesDirect

## SYNOPSIS
Gets the S2D settings from a cluster.

## SYNTAX

```
Get-ClusterStorageSpacesDirect [-Node <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-ClusterStorageSpacesDirect** cmdlet gets the Storage Spaces Direct (S2D) settings from a cluster.

## EXAMPLES

### Example 1: Get the Storage Spaces Direct settings from a cluster
```
PS C:\>Get-ClusterStorageSpacesDirect -Cluster "K0617-C1.contoso.com"
S2DCacheBehavior             : Default
S2DCacheDesiredState         : ReadWrite
S2DCacheMetadataReserveBytes : 34359738368
S2DEnabled                   : 1
```

This command sets the S2D settings from the K0617-C1.contoso.com cluster.

### Example 2: Get the Storage Spaces Direct settings from a cluster by using the pipeline operator for input
```
PS C:\>Get-Cluster "K0617-C1.contoso.com" | Get-ClusterStorageSpacesDirect
S2DCacheBehavior             : Default
S2DCacheDesiredState         : ReadWrite
S2DCacheMetadataReserveBytes : 34359738368
S2DEnabled                   : 1
```

This command gets the S2D settings from cluster K0617-C1.contoso.com and pipes the cluster object to **Get-ClusterStorageSpacesDirect**.

## PARAMETERS

### -AsJob
{{Fill AsJob Description}}

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

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Node
{{Fill Node Description}}

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

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-ClusterStorageSpacesDirect](./Disable-ClusterStorageSpacesDirect.md)

[Enable-ClusterStorageSpacesDirect](./Enable-ClusterStorageSpacesDirect.md)

[Set-ClusterStorageSpacesDirect](./Set-ClusterStorageSpacesDirect.md)

[Get-Cluster](./Get-Cluster.md)

