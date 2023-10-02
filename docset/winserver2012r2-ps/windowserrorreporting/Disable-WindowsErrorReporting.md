---
external help file: Microsoft.WindowsErrorReporting.PowerShell.dll-Help.xml
Module Name: WindowsErrorReporting
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/windowserrorreporting/disable-windowserrorreporting?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WindowsErrorReporting
---

# Disable-WindowsErrorReporting

## SYNOPSIS
Disables Windows Error Reporting.

## SYNTAX

```
Disable-WindowsErrorReporting [<CommonParameters>]
```

## DESCRIPTION
The **Disable-WindowsErrorReporting** cmdlet disables Windows Error Reporting (WER) on the server.

Windows Error Reporting is a flexible feedback infrastructure that gathers information about hardware and software problems, reports the information to Microsoft, and provides users with any available solutions.
Windows Error Reporting generates reports in response to system events, such as application crashes or kernel faults.

To get the current WER status, use the Get-WindowsErrorReporting cmdlet.
If you disable WER, you can use the Enable-WindowsErrorReporting cmdlet to re-enable it.
After you run this cmdlet, WER once again sends information about application failures to Microsoft.

## EXAMPLES

### Example 1: Disable Windows Error Reporting
```
PS C:\> Disable-WindowsErrorReporting
```

This command disables Windows Error Reporting.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Boolean
The **Disable-WindowsErrorReporting** cmdlet returns $True if successful; otherwise, it returns $False.

## NOTES

## RELATED LINKS

[Enable-WindowsErrorReporting](./Enable-WindowsErrorReporting.md)

[Get-WindowsErrorReporting](./Get-WindowsErrorReporting.md)


