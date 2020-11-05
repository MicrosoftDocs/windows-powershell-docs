---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: EFB4B84F-A21E-41B8-956D-5FC700220CB3
manager: dansimp
---

# Disable-WssBackupPolicy

## SYNOPSIS
Disables and removes a scheduled server backup policy.

## SYNTAX

```
Disable-WssBackupPolicy [-BackupPolicy] <ScheduledBackupPolicy> [-Force] [-PassThru] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Disable-WssBackupPolicy** cmdlet disables and removes a scheduled server backup policy.
When you disable a scheduled server backup policy, the scheduled daily backups in the backup policy do not run.

## EXAMPLES

### Example 1: Remove a scheduled server backup policy
```
PS C:\>$ContosoBUPolicy25 = Get-WssBackupPolicy PS C:\> Disable-WssBackupPolicy -BackupPolicy $ContosoBUPolicy25
```

This example disables and removes a scheduled server backup policy.

The first command gets the backup policy for the computer and stores the result in the **$ContosoBUPolicy25** variable

The second command disables and removes the backup policy stored in **$ContosoBUPolicy25**.

## PARAMETERS

### -BackupPolicy
Specifies the scheduled backup policy to disable and remove.

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

### -PassThru
Indicates that the cmdlet creates an object that you can use in a pipeline.
By default, this cmdlet does not generate any output.

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

[Get-WssBackupPolicy](./Get-WssBackupPolicy.md)

[Resume-WssBackupPolicy](./Resume-WssBackupPolicy.md)

[Set-WssBackupPolicy](./Set-WssBackupPolicy.md)

[Suspend-WssBackupPolicy](./Suspend-WssBackupPolicy.md)



