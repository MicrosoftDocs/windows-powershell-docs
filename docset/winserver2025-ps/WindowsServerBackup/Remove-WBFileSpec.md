---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/remove-wbfilespec?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WBFileSpec
---

# Remove-WBFileSpec

## SYNOPSIS
Removes a backup file specification from a backup policy.

## SYNTAX

```
Remove-WBFileSpec [-Policy] <WBPolicy> [-FileSpec] <WBFileSpec> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WBFileSpec** cmdlet removes a **WBFileSpec** object that contains a backup file specification from a **WBPolicy** object that contains a backup policy.
A backup file specification contains a list of items to include in or exclude from backups that use the backup policy.

Before you can remove a backup file specification from a **WBPolicy** object, you must put the **WBPolicy** object in edit mode.
To put the **WBPolicy** object in edit mode for a policy that you set as the scheduled backup policy, use the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet with the *Editable* parameter.
The [New-WBPolicy](./New-WBPolicy.md) cmdlet creates a new **WBPolicy** object that is already in edit mode.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Remove a backup file specification from a backup policy
```
PS C:\> $Filespeclist = Get-WBFileSpec -Policy $Policy
PS C:\> Remove-WBFileSpec -Policy $Policy -FileSpec $Filespeclist[1]
```

This example removes a backup file specification from a backup policy.

The first command gets a list of the backup file specifications from the backup policy in the variable named $Policy.
The command assigns the backup file specifications to the array in the variable named $Filespeclist.

The second command removes the backup file specification in the first element of $Filespeclist from the policy stored in the $Policy variable.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSpec
Specifies a backup file specification object to remove from the **WBPolicy** object.

```yaml
Type: WBFileSpec
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Policy
Specifies a backup policy object that contains the backup policy that this cmdlet updates.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBPolicy

### Microsoft.Windows.ServerBackup.Commands.WBFileSpec

This cmdlet removes a **WBFileSpec** object from a **WBPolicy** object.

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-WBFileSpec](./Get-WBFileSpec.md)

[Get-WBPolicy](./Get-WBPolicy.md)

