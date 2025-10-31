---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsErrorReporting.PowerShell.dll-Help.xml
Module Name: WindowsErrorReporting
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/windowserrorreporting/get-windowserrorreporting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WindowsErrorReporting
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Disable-WindowsErrorReporting](./Disable-WindowsErrorReporting.md)

[Enable-WindowsErrorReporting](./Enable-WindowsErrorReporting.md)

