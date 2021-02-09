---
external help file: Microsoft.Windows.Appx.PackageManager.Commands.dll-help.xml
Module Name: Appx
online version: 
schema: 2.0.0
title: Get-AppxLog
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 91B9C397-BE94-4631-8739-F41DC41CA31E
---

# Get-AppxLog

## SYNOPSIS
Gets an app package (.appx) installation log.

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
The **Get-AppxLog** function gets the app package (.appx) installation log created during the deployment of an app package (.appx).
The log contains errors, warnings, and additional information about the processes initiated by cmdlets in the Appx PowerShell module.

When Add-AppxPackage or Remove-AppxPackage report a failure, they will return the ActivityID to use with Get-AppxLog.

For more information about common error codes, see Troubleshooting packaging, deployment, and query of Windows Store appshttp://go.microsoft.com/fwlink/?LinkId=271201.

## EXAMPLES

### Example 1
```
PS C:\>Get-AppxLog
```

This example gets the logs associated with the most recent deployment operation.

### Example 2
```
PS C:\>Get-AppxLog -All
```

This example gets all the app package installation logs on the computer.

## PARAMETERS

### -ActivityId
Gets the log for a particular app package (.appx) installation.

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
Gets all logs on the computer.
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

[Package Manager API](https://go.microsoft.com/fwlink/?LinkId=245447)

[How to Add and Remove Apps](https://go.microsoft.com/fwlink/?LinkID=231020)

[Troubleshooting packaging, deployment, and query of Windows Store apps](https://go.microsoft.com/fwlink/?LinkId=271201)

[Get-AppxPackage](./Get-AppxPackage.md)

[Get-AppxPackageManifest](./Get-AppxPackageManifest.md)

[Remove-AppxPackage](./Remove-AppxPackage.md)

[Add-AppxPackage](./Add-AppxPackage.md)

[Get-AppxLastError](./Get-AppxLastError.md)

