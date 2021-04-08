---
author: Kateyanne
external help file: WSS_Cmdlets.xml
manager: dansimp
Module Name: WssCmdlets
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/wsscmdlets/get-wssbackupdisk?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WssBackupDisk

## SYNOPSIS
Gets a list of online hard disks that can be backup targets and can store server backups..

## SYNTAX

```
Get-WssBackupDisk
```

## DESCRIPTION
The **Get-WssBackupDisk** cmdlet gets all online hard disks that can be  backup targets and can store server backups.

## EXAMPLES

### Example 1: Get a list of backup targets
```
PS C:\> $ContosoBUDisk215 = Get-WssBackupDisk
```

This command gets the list of currently available backup targets and stores the list in the variable named $ContosoBUDisk215.

## PARAMETERS

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Initialize-WssBackupDisk](./Initialize-WssBackupDisk.md)



