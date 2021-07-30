---
external help file: WssCmdlets.dll-Help.xml
Module Name: WSSCmdlets
ms.date: 12/05/2017
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssfilehistoryconfiguration?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WssFileHistoryConfiguration
---

# Get-WssFileHistoryConfiguration

## SYNOPSIS
Gets the File History configurations settings for the server.

## SYNTAX

```
Get-WssFileHistoryConfiguration [<CommonParameters>]
```

## DESCRIPTION
The **Get-WssFileHistoryConfiguration** cmdlet gets the File History configuration settings for the server.
You can use the Set-WssFileHistoryConfiguration cmdlet to change the File History configuration settings.

## EXAMPLES

### Example 1: Get the File History configurations settings
```
PS C:\> Get-WssFileHistoryConfiguration
```

This command gets the File History configuration settings for the server.

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsServerSolutions.DataProtection.FileBackup.ConfigurationSet
This cmdlet generates file history configuration settings.

## NOTES

## RELATED LINKS

[Set-WssFileHistoryConfiguration](./Set-WssFileHistoryConfiguration.md)

[Get-WssFileHistoryManagementStatus](./Get-WssFileHistoryManagementStatus.md)

