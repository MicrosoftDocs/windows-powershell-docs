---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.WindowsErrorReporting.PowerShell.dll-Help.xml
Module Name: WindowsErrorReporting
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/windowserrorreporting/enable-windowserrorreporting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WindowsErrorReporting
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Boolean
The **Enable-WindowsErrorReporting** cmdlet returns $True if it is successful.
Otherwise, it returns $False.

## NOTES

## RELATED LINKS

[Disable-WindowsErrorReporting](./Disable-WindowsErrorReporting.md)

[Get-WindowsErrorReporting](./Get-WindowsErrorReporting.md)

