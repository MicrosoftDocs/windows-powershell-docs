---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
Module Name: WebAdministration
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/webadministration/get-webrequest?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WebRequest
---

# Get-WebRequest

## SYNOPSIS
Gets the IIS requests that are currently being run.

## SYNTAX

```
Get-WebRequest [-InputObject <PSObject>] [-AppPool <String>] [-Process <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WebRequest** cmdlet gets Internet Information Services (IIS) requests that are currently being run.

## EXAMPLES

### Example 1: Get requests that are currently being run
```
IIS:\> Get-Item -AppPool "IIS:\AppPools\DefaultAppPool" | Get-WebRequest
```

This command gets a list of IIS requests that are currently being run.

## PARAMETERS

### -AppPool
Specifies the application pool from which request information is retrieved.

```yaml
Type: String
Parameter Sets: (All)
Aliases: pool

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

### -Process
Specifies a process ID for which request information is retrieved.

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

[Invoke-WebRequest](https://go.microsoft.com/fwlink/?LinkId=821826)

