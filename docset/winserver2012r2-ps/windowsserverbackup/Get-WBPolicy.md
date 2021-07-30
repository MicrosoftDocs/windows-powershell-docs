---
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 10/30/2017
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/get-wbpolicy?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WBPolicy
---

# Get-WBPolicy

## SYNOPSIS
Retrieves the current backup policy for the computer.

## SYNTAX

```
Get-WBPolicy [-Editable] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBPolicy** cmdlet retrieves the backup policy object for the computer.
Use the **Editable** parameter to return the policy information in edit mode.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Editable
This cmdlet uses the **Editable** parameter to set the **WBPolicy** object in edit mode.

## OUTPUTS

### WBPolicy
This cmdlet displays the **WBPolicy** object.
The cmdlet returns a null value if no backup policy is set.

## NOTES
* If you use the **Editable** parameter to make changes, set the updated policy as the current policy by using the Set-WBPolicy cmdlet.

## RELATED LINKS

[New-WBPolicy](./New-WBPolicy.md)

[Remove-WBPolicy](./Remove-WBPolicy.md)

[Set-WBPolicy](./Set-WBPolicy.md)

