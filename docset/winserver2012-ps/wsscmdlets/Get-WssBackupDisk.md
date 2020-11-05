---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: C23AC990-B422-4923-B01F-07D3C7E49D1F
manager: dansimp
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



