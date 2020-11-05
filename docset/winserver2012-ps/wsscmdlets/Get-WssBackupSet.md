---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: DB52B2F9-16B3-401F-9814-8A9C026C8EE6
manager: dansimp
---

# Get-WssBackupSet

## SYNOPSIS
Gets a collection of backup sets from a server backup.

## SYNTAX

```
Get-WssBackupSet [[-BackupTarget] <BackupTarget>] [[-MachineName] <String>]
```

## DESCRIPTION
The **Get-WssBackupSet** cmdlet gets a collection of backup sets from a server backup.
A backup set is the output of a successful backup operation.

## EXAMPLES

### Example 1: Get backup sets from a server backup
```
PS C:\> Get-WssBackupSet -BackupTarget $ContosoWest01
```

This command gets a list of backup sets from the server backup that is stored in the variable named **$ContosoWest01**.

## PARAMETERS

### -BackupTarget
Specifies the target volume from which to get the backup sets.

```yaml
Type: BackupTarget
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MachineName
Specifies the name of the server whose data is in the backup set.

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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WssBackupJob](./Get-WssBackupJob.md)

[Start-WssBackupJob](./Start-WssBackupJob.md)

[Stop-WssBackupJob](./Stop-WssBackupJob.md)

