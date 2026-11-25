---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/get-iisapppool?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IISAppPool
---

# Get-IISAppPool

## SYNOPSIS
Gets configuration information for an IIS Application Pool.

## SYNTAX

```
Get-IISAppPool [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IISAppPool** cmdlet gets information about application pools and their current status and other key information.
If a specific application pool or a comma delimited list of application pools are requested, only those whose names are passed as an argument are returned.
Otherwise all the application pools are returned.

## EXAMPLES

### Example 1: Get information about specific app pool(s)
```powershell
PS C:\> Get-IISAppPool "DefaultAppPool","NewAppPool"
Name                 Status       CLR Ver  Pipeline Mode  Start Mode
----                 ------       -------  -------------  ----------
DefaultAppPool       Started      v4.0     Integrated     OnDemand
NewAppPool           Started      v4.0     Integrated     OnDemand
```

This command gets the configuration information for the pools DefaultAppPool and NewAppPool.

### Example 2: Get information about all application pools
```powershell
PS C:\> Get-IISAppPool
Name                 Status       CLR Ver  Pipeline Mode  Start Mode
----                 ------       -------  -------------  ----------
DefaultAppPool       Started      v4.0     Integrated     OnDemand
.NET v4.5 Classic    Started      v4.0     Classic        OnDemand
.NET v4.5            Started      v4.0     Integrated     OnDemand
PattiFul             Stopped      v4.0     Integrated     OnDemand
```

This command gets the configuration information for all application pools.

## PARAMETERS

### -Name
Specifies the name of the application pool(s) in which the configuration information is returned.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

[Web Administration Cmdlets for Windows PowerShell](../webadministration/WebAdministration.md)

