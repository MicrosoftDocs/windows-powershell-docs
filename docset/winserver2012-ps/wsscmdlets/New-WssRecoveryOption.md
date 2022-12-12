---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/new-wssrecoveryoption?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# New-WssRecoveryOption

## SYNOPSIS
Creates a recovery configuration for a file restore operation.

## SYNTAX

```
New-WssRecoveryOption [-OverwriteExisting] [-RestoreAcl]
```

## DESCRIPTION
The **New-WssRecoveryOption** cmdlet creates a recovery configuration that a later file restore operation can use to determine which files to restore.

## EXAMPLES

### Example 1: Create a recovery configuration
```
PS C:\> $RecoverOpt15 = New-WssRecoveryOption -RestoreAcl
```

This command creates a configuration for a file restore operation that includes the ACL along with files and stores the configuration in the variable named $RecoverOpt15.

## PARAMETERS

### -OverwriteExisting
Indicates that the restore operation overwrites existing files.

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

### -RestoreAcl
Indicates that the cmdlet restores an access control list (ACL) along with files.
An ACL is a list of the users and groups that have permission to view or change a file.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssRecoveryItem](./Get-WssRecoveryItem.md)

