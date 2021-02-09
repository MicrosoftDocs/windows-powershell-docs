---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 10357DDB-98F1-4554-8CF8-7877C733E8E5
manager: dansimp
---

# Initialize-WssBackupDisk

## SYNOPSIS
Prepares a disk for, or removes a disk from, a sbs_sbs8_1 backup.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Initialize-WssBackupDisk [-Disk] <Disk> [-Name] <String> [-Force] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Initialize-WssBackupDisk [-Disk] <Disk> [-Remove] [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Initialize-WssBackupDisk** cmdlet prepares a disk to use as storage for a sbs_sbs8_1 backup or removes a disk from a sbs_sbs8_2 backup.
When the cmdlet prepares a disk for backup storage, it automatically formats the disk.

## EXAMPLES

### Example 1: Initialize a backup disk
```
PS C:\>$ContosoBUDisk515 = Get-WssDisk PS C:\>Initialize-WssBackupDisk -Disk $ContosoDisk515[0] -Name "ContosoWSEBackup40"
```

This example initializes a sbs_sbs8_2 backup disk.

The first command gets a list of available disks and stores it in the variable named $ContosoBUDisk515.

The second command initializes the first backup disk (located in position 0) in the array in $ContosoDisk515 and gives the new backup disk the name ContosoWSEBackup40.

## PARAMETERS

### -Disk
Specifies the disk to add to or remove from a sbs_sbs8_2 backup.

```yaml
Type: Disk
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remove
Indicates that the cmdlet removes the disk from  a sbs_sbs8_2 backup.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
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

## OUTPUTS

### Disk

## NOTES

## RELATED LINKS

[Get-WssBackupDisk](./Get-WssBackupDisk.md)

