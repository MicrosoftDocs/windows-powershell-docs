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
title: Enable-WindowsErrorReporting
ms.reviewer:
ms.assetid: C9A65367-A3AC-4220-BCE2-F5F5A49E6324
---

# Enable-WindowsErrorReporting

## SYNOPSIS
Enables Windows Error Reporting.

## SYNTAX

```
Enable-WindowsErrorReporting [<CommonParameters>]
```

## DESCRIPTION
The **Enable-WindowsErrorReporting** cmdlet enables Windows Error Reporting (WER) on the server.

Windows Error Reporting is a flexible feedback infrastructure that gathers information about hardware and software problems, reports the information to Microsoft, and gives users any available solutions.
Windows Error Reporting generates reports in response to system events, such as application crashes or kernel faults.

To get the current WER status, use the [Get-WindowsErrorReporting](./Get-WindowsErrorReporting.md) cmdlet.
If you enable WER, you can use the [Disable-WindowsErrorReporting](./Disable-WindowsErrorReporting.md) cmdlet to disable it.
After you run this cmdlet, WER no longer sends information about application failures to Microsoft.

## EXAMPLES

### Example 1: Enable Windows Error Reporting
```
PS C:\> Enable-WindowsErrorReporting
```

This command enables Windows Error Reporting.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Boolean
The **Enable-WindowsErrorReporting** cmdlet returns $True if it is successful.
Otherwise, it returns $False.

## NOTES

## RELATED LINKS

[Disable-WindowsErrorReporting](./Disable-WindowsErrorReporting.md)

[Get-WindowsErrorReporting](./Get-WindowsErrorReporting.md)

