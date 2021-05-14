---
external help file: WSS_Cmdlets.xml
Module Name: WssCmdlets
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/start-wssclientbackuprepair?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Start-WssClientBackupRepair

## SYNOPSIS
Starts an attempt to repair the database of client computer backups.

## SYNTAX

```
Start-WssClientBackupRepair [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Start-WssClientBackupRepair** cmdlet starts an attempt to repair the database of client computer backups.
You can use this cmdlet in the event that the database becomes corrupt or unusable.

## EXAMPLES

### Example 1: Start client backup database repair
```
PS C:\> Start-WssClientBackupRepair
```

This command starts an attempt to repair the client backup database.

## PARAMETERS

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

[Stop-WssClientBackupRepair](./Stop-WssClientBackupRepair.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

