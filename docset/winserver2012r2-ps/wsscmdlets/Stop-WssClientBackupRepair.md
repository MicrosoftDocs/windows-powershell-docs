---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/stop-wssclientbackuprepair?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-WssClientBackupRepair
---

# Stop-WssClientBackupRepair

## SYNOPSIS
Stops the attempt to repair a database of client computer backups.

## SYNTAX

```
Stop-WssClientBackupRepair [<CommonParameters>]
```

## DESCRIPTION
The **Stop-WssClientBackupRepair** cmdlet stops the attempt to repair the database of client computer backups.
You can use the Start-WssClientBackupRepair cmdlet to start an attempt to repair a database that is corrupt or unusable.

## EXAMPLES

### Example 1: Stop a client backup database repair
```
PS C:\> Stop-WssClientBackupRepair
```

This command stops the attempt to repair the client backup database.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Start-WssClientBackupRepair](./Start-WssClientBackupRepair.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

