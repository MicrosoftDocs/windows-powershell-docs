---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/get-wbfilespec?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WBFileSpec
---

# Get-WBFileSpec

## SYNOPSIS
Gets the list of backup file specifications associated with a backup policy.

## SYNTAX

```
Get-WBFileSpec [-Policy] <WBPolicy> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Get-WBFileSpec** cmdlet gets the list of **WBFileSpec** objects that contain backup file specifications for a **WBPolicy** object that contains a backup policy.
A **WBFileSpec** object defines the items to include in or exclude from backups that you create by using the backup policy.

Use the [New-WBFileSpec](./New-WBFileSpec.md) and [Add-WBFileSpec](./Add-WBFileSpec.md) cmdlets to define and apply changes to the backup policy.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get backup file specifications for a backup policy
```
PS C:\> $Filespeclist = Get-WBFileSpec -Policy $Policy
```

This command gets the list of file specifications in the **WBPolicy** object in the variable named $Policy and assigns them to the $Filespeclist array.

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

### -Policy
Specifies the **WBPolicy** object that contains the backup policy for which to display backup file specifications.

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

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-WBFileSpec](./Add-WBFileSpec.md)

[Get-WBFileSpec](./Get-WBFileSpec.md)

[New-WBPolicy](./New-WBPolicy.md)

[Remove-WBFileSpec](./Remove-WBFileSpec.md)

