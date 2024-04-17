---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
Module Name: Appx
ms.date: 05/15/2023
online version: https://learn.microsoft.com/powershell/module/appx/get-appxlasterror?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AppxLastError
---

# Get-AppxLastError

## SYNOPSIS
Get the last error reported in the app package installation logs.

## SYNTAX

```
Get-AppxLastError [<CommonParameters>]
```

## DESCRIPTION

The `Get-AppxLastError` cmdlet gets the last error reported in the app package installation logs
for the current Windows PowerShell session. An app package has an `.msix` or `.appx` file
extension.

## EXAMPLES

### Example 1: Get the last error

```powershell
Get-AppxLastError
```

This command gets the last error reported in the app installation logs.

## PARAMETERS

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Diagnostics.Eventing.Reader.EventLogRecord

## NOTES

## RELATED LINKS

[Package Manager API](https://go.microsoft.com/fwlink/?LinkId=245447)

[How to Deploy App Packages](https://go.microsoft.com/fwlink/?LinkID=231020)

[Get-AppxPackage](./Get-AppxPackage.md)

[Get-AppxPackageManifest](./Get-AppxPackageManifest.md)

[Get-AppxLog](./Get-AppxLog.md)
