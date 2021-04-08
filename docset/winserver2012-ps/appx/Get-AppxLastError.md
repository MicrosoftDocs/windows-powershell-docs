---
author: Kateyanne
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
manager: dansimp
Module Name: Appx
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/appx/get-appxlasterror?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-AppxLastError

## SYNOPSIS
Get the last error reported in the app package installation logs.

## SYNTAX

```
Get-AppxLastError [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppxLastError** cmdlet gets the last error reported in the app package installation logs for the current Windows PowerShell® session.
An app package has an .appx file name extension.

## EXAMPLES

### Example 1: Get the last error
```
PS C:\>Get-AppxLastError
```

This command gets the last error reported in the app installation logs.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Diagnostics.Eventing.Reader.EventLogRecord

## NOTES

## RELATED LINKS

[PackageManager class](https://go.microsoft.com/fwlink/?LinkId=245447)

[Sideload Apps with DISM](https://go.microsoft.com/fwlink/?LinkID=231020)

