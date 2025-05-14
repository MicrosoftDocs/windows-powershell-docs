---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/resume-wbvolumerecovery?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-WBVolumeRecovery
---

# Resume-WBVolumeRecovery

## SYNOPSIS
Resumes a volume recovery operation from a removable device and specific media.

## SYNTAX

```
Resume-WBVolumeRecovery [<CommonParameters>]
```

## DESCRIPTION
The **Resume-WBVolumeRecovery** cmdlet resumes a volume recovery operation performed from a removable device and specific media.
If the requested media is not inserted, the cmdlet returns an error with a description of the requested media.
Otherwise, the cmdlet returns confirmation that the recovery operation resumed.

## EXAMPLES

### Example 1: Resume a volume recovery operation
```
PS C:\> Resume-WBVolumeRecovery
```

This command resumes the volume recovery operation.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Start-WBVolumeRecovery](./Start-WBVolumeRecovery.md)

