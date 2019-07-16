---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: 32B27EBC-9C40-4566-9116-B852FF150C96
manager: dansimp
---

# Resume-WssBackupPolicy

## SYNOPSIS
Resumes a scheduled task that runs a server backup in TaskScheduler.

## SYNTAX

```
Resume-WssBackupPolicy [-BackupPolicy] <ScheduledBackupPolicy> [-Force] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Resume-WssBackupPolicy** cmdlet resumes a scheduled task that runs a server backup in TaskScheduler.

## EXAMPLES

### Example 1: Resume a server backup
```
PS C:\>$ContosoBUPolicy25 = Get-WssBackupPolicy PS C:\> Resume-WssBackupPolicy -BackupPolicy $ContosoBUPolicy215
```

This example resumes a scheduled task.

The first command gets the backup policy for the computer and stores the result in the **$ContosoBUPolicy25** variable

The second command resumes the backup of the backup policy stored in **$ContosoBUPolicy215**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy to resume.

```yaml
Type: ScheduledBackupPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## NOTES

## RELATED LINKS

[Disable-WssBackupPolicy](./Disable-WssBackupPolicy.md)

[Get-WssBackupPolicy](./Get-WssBackupPolicy.md)

[Set-WssBackupPolicy](./Set-WssBackupPolicy.md)

[Suspend-WssBackupPolicy](./Suspend-WssBackupPolicy.md)

