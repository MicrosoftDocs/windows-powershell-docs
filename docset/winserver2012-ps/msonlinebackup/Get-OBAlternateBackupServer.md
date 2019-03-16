---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: F727BBC2-04C3-4845-8946-DE1B0064D963
---

# Get-OBAlternateBackupServer

## SYNOPSIS
Gets the array of OBAlternateBackupServer objects.

## SYNTAX

```
Get-OBAlternateBackupServer
```

## DESCRIPTION
The **Get-OBAlternateBackupServer** gets the array of OBBackupServer objects.
This array represents all of the servers that are associated with the specified backup account except for the local server.
Valid credentials are required in order to obtain this array.

ps_mob_user_group_remark

## EXAMPLES

### Example 1: Get all backup servers
```
PS C:\>Get-OBAlternateBackupServer
```

This command gets all of the backup servers that are associated with the backup account.

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBBackupServer

## NOTES

## RELATED LINKS

[ConvertTo-SecureString](http://go.microsoft.com/fwlink/?LinkID=113291)

[New-Object](http://go.microsoft.com/fwlink/?LinkID=113355)

