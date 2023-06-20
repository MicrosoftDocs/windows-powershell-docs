---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/initialize-wssbackupdisk?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Initialize-WssBackupDisk
---

# Initialize-WssBackupDisk

## SYNOPSIS
Prepares a disk for, or removes a disk from, a sbs_sbs8_1 backup.

## SYNTAX

### AddParamSet (Default)
```
Initialize-WssBackupDisk [-Force] [-Disk] <Disk> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveParamSet
```
Initialize-WssBackupDisk [-Force] [-Disk] <Disk> [-Remove] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Initialize-WssBackupDisk** cmdlet prepares a disk to use as storage for a sbs_sbs8_1 backup or removes a disk from a sbs_sbs8_2 backup.
When the cmdlet prepares a disk for backup storage, it automatically formats the disk.

## EXAMPLES

### Example 1: Initialize a backup disk
```
PS C:\>$ContosoBUDisk515 = Get-WssDisk
PS C:\> Initialize-WssBackupDisk -Disk $ContosoDisk515[0] -Name "ContosoWSEBackup40"
```

This example initializes a sbs_sbs8_2 backup disk.

The first command gets a list of available disks and stores it in the variable named $ContosoBUDisk515.

The second command initializes the first backup disk (located in position 0) in the array in $ContosoDisk515 and gives the new backup disk the name ContosoWSEBackup40.

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

### -Disk
Specifies the disk to add to or remove from a sbs_sbs8_2 backup.

```yaml
Type: Disk
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -Name
Specifies the name of the backup disk.

```yaml
Type: String
Parameter Sets: AddParamSet
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remove
Indicates that the cmdlet removes the disk from  a sbs_sbs8_2 backup.

```yaml
Type: SwitchParameter
Parameter Sets: RemoveParamSet
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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

### Disk

## NOTES

## RELATED LINKS

[Get-WssBackupDisk](./Get-WssBackupDisk.md)

