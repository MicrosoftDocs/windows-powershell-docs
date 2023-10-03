---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/start-wssserverfilerestore?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Start-WssServerFileRestore
---

# Start-WssServerFileRestore

## SYNOPSIS
Starts a file restore operation.

## SYNTAX

```
Start-WssServerFileRestore [-BackupSet] <BackupSet>
 [-RecoveryItems] <System.Collections.Generic.IList`1[Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.RecoveryItem]>
 [[-RecoveryLocation] <String>] [-RecoveryOption] <RecoveryOptions> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-WssServerFileRestore** cmdlet starts a file restore operation on a sbs_sbs8_2 server.

## EXAMPLES

### Example 1: Restore files on a server
```
PS C:\> $Items = Get-WssRecoveryItem
PS C:\> $Option = New-WssRecoveryOption
PS C:\> $Backupsets = Get-WssBackupSet
PS C:\> Start-WssServerFileRestore -BackupSet $Backupsets[1] -RecoveryItems $Items -RecoveryOption $Option
```

This example restores files on a sbs_sbs8_2 server.

The first command uses the **Get-WssRecoveryItem** cmdlet to retrieve the recovery items, and stores the result in the variable named **Items**.

The second command uses **New-WssRecoveryOption** to create a recovery configuration for a file restore operation, and stores the result in the variable named **Option**.

The third command uses **Get-WssBackupSet** to retrieve a collection of backup sets, and stores the collection in a variable named **Backupsets**.

The fourth command uses **Start-WssServerFileRestore** to start a file restore operation on the server using the second backup set.

## PARAMETERS

### -BackupSet
Specifies a backup set from which to restore the recovery items.

```yaml
Type: BackupSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -RecoveryItems
Specifies a list of items to restore.

```yaml
Type: System.Collections.Generic.IList`1[Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.RecoveryItem]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecoveryLocation
Specifies the location to which to restore the items.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryOption
Specifies the restore options, such as whether to overwrite existing files or to restore file permissions.

```yaml
Type: RecoveryOptions
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

