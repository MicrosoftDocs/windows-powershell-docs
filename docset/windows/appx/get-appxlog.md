---
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
keywords: powershell, cmdlet
manager: jasgro
Module Name: Appx
ms.assetid: 91B9C397-BE94-4631-8739-F41DC41CA31E
ms.author: v-anbarr
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer:
ms.sitesec: library
ms.technology: powershell-windows
ms.topic: reference
online version:
schema: 2.0.0
title: Get-AppxLog
---

# Get-AppxLog

## SYNOPSIS
Gets an app package installation log.

## SYNTAX

### All (Default)
```
Get-AppxLog [-All] [<CommonParameters>]
```

### ActivityId
```
Get-AppxLog [-ActivityId <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AppxLog** cmdlet gets the app package installation log created during the deployment of an app package.
An app package has an .appx file name extension.
The log contains errors, warnings, and additional information about the processes initiated by cmdlets in the Appx Windows PowerShell® module.

When Add-AppxPackage or Remove-AppxPackage report a failure, they return the **ActivityID** to use with **Get-AppxLog**.

For more information about common error codes, see [Troubleshooting packaging, deployment, and query of Windows Store apps](http://go.microsoft.com/fwlink/?LinkId=271201).

## EXAMPLES

### Example 1: Get logs for the most recent deployment
```
PS C:\> Get-AppxLog
```

This command gets the logs associated with the most recent deployment operation.

### Example 2: Get logs for all logs
```
PS C:\> Get-AppxLog -All
```

This command gets all the app package installation logs on the computer.

## PARAMETERS

### -ActivityId
Specifies an activity ID.
This cmdlet uses the ID to get the log for a particular app package installation.

```yaml
Type: String
Parameter Sets: ActivityId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -All
Indicates that the cmdlet gets all logs on the computer.
You can get additional information when you run this cmdlets from Windows PowerShell as an administrator.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.Diagnostics.Eventing.Reader.EventLogRecord

## NOTES

## RELATED LINKS

[Package Manager API](http://go.microsoft.com/fwlink/?LinkId=245447)

[How to Add and Remove Apps](http://go.microsoft.com/fwlink/?LinkID=231020)

[Troubleshooting packaging, deployment, and query of Windows Store apps](http://go.microsoft.com/fwlink/?LinkId=271201)

[Get-AppxPackage](./Get-AppxPackage.md)

[Get-AppxPackageManifest](./Get-AppxPackageManifest.md)

[Get-AppxLastError](./Get-AppxLastError.md)

