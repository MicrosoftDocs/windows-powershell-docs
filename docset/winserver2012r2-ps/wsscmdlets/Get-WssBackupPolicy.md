---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://learn.microsoft.com/powershell/module/wsscmdlets/get-wssbackuppolicy?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssBackupPolicy
---

# Get-WssBackupPolicy

## SYNOPSIS
Gets the current scheduled backup policy.

## SYNTAX

```
Get-WssBackupPolicy [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssBackupPolicy** cmdlet gets the current scheduled backup policy.
The cmdlet returns an empty scheduled backup policy if no backup policy is configured.

## EXAMPLES

### Example 1 Get the current scheduled backup policy
```
PS C:\> $ContosoBUPol12 = Get-WssBackupPolicy
```

This command gets the currently scheduled backup policy and stores it in the **$ContosoBUPol12** variable.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.ServerBackup.ObjectModel.ScheduledBackupPolicy
This cmdlet returns the server backup policy that specifies backup options such as backup targets, backup volume and schedule time.

## NOTES

## RELATED LINKS

[Disable-WssBackupPolicy](./Disable-WssBackupPolicy.md)

[Resume-WssBackupPolicy](./Resume-WssBackupPolicy.md)

[Set-WssBackupPolicy](./Set-WssBackupPolicy.md)

[Suspend-WssBackupPolicy](./Suspend-WssBackupPolicy.md)

