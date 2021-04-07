---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
manager: jasgro
Module Name: WindowsServerBackup
ms.author: v-kaunu
ms.date: 12/27/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/resume-wbbackup?view=windowsserver2019-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-WBBackup
---

# Resume-WBBackup

## SYNOPSIS
Resumes a backup operation to a removable device after you add media to the device.

## SYNTAX

```
Resume-WBBackup [-ForceFormat] [<CommonParameters>]
```

## DESCRIPTION
The **Resume-WBBackup** cmdlet resumes a backup operation when you are backing up to a removable device and must add new media.

If the media that you add contain data and you must format the media, call this cmdlet with the *ForceFormat* parameter.
If the device does not contain media, the cmdlet returns with an error message that describes the missing media.
If the device contains media, the cmdlet returns confirmation that the backup has resumed.

## EXAMPLES

### Example 1: Resume a backup
```
PS C:\> Resume-WBBackup
```

This command resumes a backup operation.

## PARAMETERS

### -ForceFormat
Indicates that the cmdlet formats the media that contains data.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### ForceFormat
If the media contain data and need formatting, call this cmdlet with the *ForceFormat* parameter.

## OUTPUTS

### System.String, System.Exception
If the removable device does not contain the requested media, the cmdlet returns with an error message that describes the missing media.
If the device contains media, the cmdlet returns confirmation that the backup has resumed.

## NOTES

## RELATED LINKS

[Start-WBBackup](./Start-WBBackup.md)

