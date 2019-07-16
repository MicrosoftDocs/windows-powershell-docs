---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsErrorReporting.PowerShell.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-WindowsErrorReporting
ms.reviewer:
ms.assetid: 74E8A514-C0CF-4AFD-ABF7-40377A5D4F6C
---

# Get-WindowsErrorReporting

## SYNOPSIS
Retrieves the Windows Error Reporting status.

## SYNTAX

```
Get-WindowsErrorReporting [<CommonParameters>]
```

## DESCRIPTION
The **Get-WindowsErrorReporting** cmdlet retrieves the Windows Error Reporting (WER) status for the server.

Windows Error Reporting is a flexible feedback infrastructure that gathers information about hardware and software problems, reports the information to Microsoft, and gives users any available solutions.
Windows Error Reporting generates reports in response to system events, such as application crashes or kernel faults.

Use [Enable-WindowsErrorReporting](./Enable-WindowsErrorReporting.md) to enable Windows Error Reporting.
After you enable it, WER sends information about application failures to Microsoft.
Use [Disable-WindowsErrorReporting](./Disable-WindowsErrorReporting.md) to disable WER.

## EXAMPLES

### Example 1: Get the Windows Error Reporting status
```
PS C:\> Get-WindowsErrorReporting
```

This command gets the Windows Error Reporting status, which is either enabled or disabled.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Disable-WindowsErrorReporting](./Disable-WindowsErrorReporting.md)

[Enable-WindowsErrorReporting](./Enable-WindowsErrorReporting.md)

