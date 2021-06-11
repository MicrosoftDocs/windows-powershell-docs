---
description: Use this topic to help manage MDOP technologies with Windows PowerShell.
external help file: Microsoft.AppV.AppVClientPowerShell.dll-Help.xml
ms.date: 12/05/2016
ms.devlang: powershell
schema: 2.0.0
title: Get-AppvClientMode
---

# Get-AppvClientMode

## SYNOPSIS
Displays the mode for the App-V Client.

## SYNTAX

```
Get-AppvClientMode [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppvClientMode** cmdlet displays the mode that the Microsoft Application Virtualization (App-V) Client is currently set to.
Valid values are Normal and Uninstall.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AppV.AppvClientPowerShell.AppvClientMode
This cmdlet generat **AppvClientMode** object that describes the current Appv Client mode, either Normal or Uninstall.

## NOTES

## RELATED LINKS

[Set-AppvClientMode](./set-appvclientmode.md)
