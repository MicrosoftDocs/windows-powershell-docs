---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/get-wbpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WBPolicy
---

# Get-WBPolicy

## SYNOPSIS
Gets the current backup policy for the computer.

## SYNTAX

```
Get-WBPolicy [-Editable] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBPolicy** cmdlet gets the backup policy object for the computer.
Use the *Editable* parameter to return the policy information in edit mode.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get a current backup policy
```
PS C:\> Get-WBPolicy
```

This command gets information about the backup policy object.
The information includes all the settings for the backup policy, such as what items to back up, when to run backups, and where to store backups.

### Example 2: Get a current backup policy in edit mode
```
PS C:\> Get-WBPolicy -Editable
```

This command gets information about the backup policy object, and it makes the policy editable.

## PARAMETERS

### -Editable
Indicates that the cmdlet returns a current backup policy in edit mode.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES
* If you use the *Editable* parameter to make changes, set the updated policy as the current policy by using the Set-WBPolicy cmdlet.

## RELATED LINKS

[New-WBPolicy](./New-WBPolicy.md)

[Remove-WBPolicy](./Remove-WBPolicy.md)

[Set-WBPolicy](./Set-WBPolicy.md)

