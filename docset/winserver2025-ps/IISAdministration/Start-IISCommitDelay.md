---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.IIS.Powershell.Commands.dll-Help.xml
Module Name: IISAdministration
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/iisadministration/start-iiscommitdelay?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-IISCommitDelay
---

# Start-IISCommitDelay

## SYNOPSIS
Instructs the IIS configuration system to delay the commitment of changes.

## SYNTAX

```
Start-IISCommitDelay [<CommonParameters>]
```

## DESCRIPTION
The **Start-IISCommitDelay** cmdlet instructs the Internet Information Services (IIS) configuration system to delay the commitment of changes.
The commitment of changes is delayed until the **Stop-IISCommitDelay** cmdlet is executed.

## EXAMPLES

### Example 1: Delay the commit of changes
```
PS C:\> Start-IISCommitDelay
```

This command delays the modification of IIS configuration settings until the **Stop-IISCommitDelay** cmdlet is executed.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Stop-IISCommitDelay](./Stop-IISCommitDelay.md)

[IIS Administration Cmdlets for Windows PowerShell](./iisadministration.md)

