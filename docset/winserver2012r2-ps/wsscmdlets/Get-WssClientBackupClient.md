---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssclientbackupclient?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssClientBackupClient
---

# Get-WssClientBackupClient

## SYNOPSIS
Gets a list of clients that the server can back up.

## SYNTAX

```
Get-WssClientBackupClient [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssClientBackupClient** cmdlet gets a list of the clients that the server can back up.
You can use the Enable-WssClientBackup cmdlet to enable client backup for a specific computer.

## EXAMPLES

### Example 1: Get the clients that the server can back up
```
PS C:\> Get-WssClientBackupClient
```

This command gets the list of clients that the server can back up.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.PCBackup.ObjectModel.PCBackupClient
This cmdlet returns PC backup clients.

## NOTES

## RELATED LINKS

[Enable-WssClientBackup](./Enable-WssClientBackup.md)

