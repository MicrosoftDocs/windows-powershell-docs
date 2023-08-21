---
external help file: WSBackup_Cmdlets.xml
Module Name: WindowsServerBackup
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/get-wbfilespec?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WBFileSpec

## SYNOPSIS
Gets the list of backup file specifications associated with a backup policy.

## SYNTAX

```
Get-WBFileSpec [-Policy] <WBPolicy> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Get-WBFileSpec** cmdlet gets the list of **WBFileSpec** objects that contain backup file specifications for a **WBPolicy** object that contains a backup policy.
A **WBFileSpec** object defines the items to include in or exclude from backups that you create by using the backup policy.

Use the New-WBFileSpec and Add-WBFileSpec cmdlets to define and apply changes to the backup policy.

To use this cmdlet, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Get backup file specifications for a backup policy
```
PS C:\> $Filespeclist = Get-WBFileSpec -Policy $Policy

A list of file specs in the WBPolicy object.
```

This command gets the list of file specifications in the **WBPolicy** object in the variable named **$Policy** and assigns them to the **$Filespeclist** array.

## PARAMETERS

### -Policy
Specifies the **WBPolicy** object that contains the backup policy for which to display backup file specifications.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### WBPolicy
The Get-WBFileSpec cmdlet queries the **WBPolicy** object that contains the specified backup policy.

## OUTPUTS

### WBFileSpec []
The Get-WBFileSpec cmdlet displays the list of **WBFileSpec** objects that contain backup file specifications for a **WBPolicy** object that contains a backup policy.

## NOTES

## RELATED LINKS

[Add-WBFileSpec](./Add-WBFileSpec.md)

[Get-WBFileSpec](./Get-WBFileSpec.md)

[New-WBPolicy](./New-WBPolicy.md)

[Remove-WBFileSpec](./Remove-WBFileSpec.md)

