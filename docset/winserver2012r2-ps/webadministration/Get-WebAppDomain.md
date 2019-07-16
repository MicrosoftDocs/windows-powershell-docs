---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
online version: 
schema: 2.0.0
title: Get-WebAppDomain
description: 
keywords: powershell, cmdlet
author: andreabarr
manager: jasgro
ms.date: 2017-10-30
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 089DFEB5-D3C7-42E6-A304-A8F1DA9BC837
ms.author: v-anbarr
ms.reviewer: brianlic
---

# Get-WebAppDomain

## SYNOPSIS
Gets the application domains in which the specified IIS worker process is running.

## SYNTAX

```
Get-WebAppDomain [-InputObject <PSObject>] [-ApplicationPool <String>] [-ProcessId <UInt32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebAppDomain** cmdlet gets the application domains in which the specified Internet Information Services (IIS) worker process is running.

## EXAMPLES

### Example 1: Get the application domain of a running worker process
```
IIS:\>Get-WebAppDomain -ProcessId 5872 -ApplicationPool "DefaultAppPool" 
IIS:\> Get-ChildItem IIS:\AppPools\DefaultAppPool\WorkerProcesses
```

The first command gets the application domains loaded in the specified worker process.
The second command gets the process ID from the WorkerProcesses node below the AppPools node.

## PARAMETERS

### -ApplicationPool
Specifies the application pool for which application domains are returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases: apppool, pool

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object from which parameter data is received.

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

### -ProcessId
Specifies the ID of the worker process for which the application domain is returned.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: proc, procid, pid, wp

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

