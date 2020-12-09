---
external help file: Microsoft.IIS.PowerShell.Provider.dll-Help.xml
ms.assetid: DB6C2AC0-0C2C-4897-A23D-4BA2E92E72B4
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-WebAppPoolState

## SYNOPSIS
Gets the run-time state of an IIS application pool.

## SYNTAX

```
Get-WebAppPoolState [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
Gets the run-time state of an IIS application pool.

## EXAMPLES

### -------------- EXAMPLE 1: Get the runtime state of the DefaultAppPool --------------
```
IIS:\>Get-WebAppPoolState DefaultAppPool
```

Gets the run-time state of the DefaultAppPool.

Value

-----

Started

## PARAMETERS

### -Name
The name of the application pool for which the state is returned.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

