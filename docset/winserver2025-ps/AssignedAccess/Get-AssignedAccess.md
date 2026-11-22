---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: AssignedAccess-help.xml
Module Name: AssignedAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/assignedaccess/get-assignedaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-AssignedAccess
---

# Get-AssignedAccess

## SYNOPSIS
Gets the current configuration for assigned access.

## SYNTAX

```
Get-AssignedAccess [<CommonParameters>]
```

## DESCRIPTION
The **Get-AssignedAccess** cmdlet gets the current configuration for assigned access, including the user name, user SID, app friendly name, and app ID.

Assigned Access cmdlets are supported on Windows 10 and Windows 11 client operating systems only.

## EXAMPLES

### Example 1: Get the configuration for assigned access
```
PS C:\> Get-AssignedAccess

User Name: MYPC\UserName
User SID:  S-1-5-21-594534509-2542345234-234523453-1004
AUMID:     Microsoft.Media.PlayReadyClient_2.3.1678.0_x64__8wekyb3d8bbwe
App Name:  Microsoft.Media.PlayReadyClient
```

This command gets the current configuration for assigned access.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Clear-AssignedAccess](./Clear-AssignedAccess.md)

[Set-AssignedAccess](./Set-AssignedAccess.md)

