---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssclientbackupoperationstatus?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssClientBackupOperationStatus
---

# Get-WssClientBackupOperationStatus

## SYNOPSIS
Gets the status of backup-related operations.

## SYNTAX

```
Get-WssClientBackupOperationStatus [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssClientBackupOperationStatus** cmdlet gets the status of backup-related operations for the server.

## EXAMPLES

### Example 1: Get status for backup operations
```
PS C:\> Get-WssClientBackupOperationStatus
```

This command gets the status of backup-related operations for the current server.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.OperationStatusResponse

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.BackupUtil.WcfContracts.OperationStatusResponse
This cmdlet generates client backup operation status.

## NOTES

## RELATED LINKS

[Disable-WssClientBackup](./Disable-WssClientBackup.md)

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

[Get-WssClientBackup](./Get-WssClientBackup.md)

[Set-WssClientBackup](./Set-WssClientBackup.md)

[Start-WssClientBackup](./Start-WssClientBackup.md)

[Stop-WssClientBackup](./Stop-WssClientBackup.md)

