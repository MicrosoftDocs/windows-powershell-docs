---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webapppoolstate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebAppPoolState
---

# Get-WebAppPoolState

## SYNOPSIS
Gets the run-time state of an IIS application pool.

## SYNTAX

```
Get-WebAppPoolState [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebAppPoolState** cmdlet gets the run-time state of an Internet Information Services (IIS) application pool.

## EXAMPLES

### Example 1: Get the run-time state of the DefaultAppPool
```
IIS:\> Get-WebAppPoolState -Name "DefaultAppPool"
Value

-----

Started
```

This command gets the run-time state of the DefaultAppPool.

## PARAMETERS

### -Name
Specifies the name of the application pool for which the state is returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
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

