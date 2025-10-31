---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webappdomain?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebAppDomain
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
IIS:\> Get-WebAppDomain -ProcessId 5872 -ApplicationPool "DefaultAppPool"
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

