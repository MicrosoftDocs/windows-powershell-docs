---
external help file: WSS_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: A8231A90-0A08-46D7-A01F-FC691605B16D
manager: dansimp
---

# Get-WssBackupPolicy

## SYNOPSIS
Gets the current scheduled backup policy.

## SYNTAX

```
Get-WssBackupPolicy
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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Disable-WssBackupPolicy](./Disable-WssBackupPolicy.md)

[Resume-WssBackupPolicy](./Resume-WssBackupPolicy.md)

[Set-WssBackupPolicy](./Set-WssBackupPolicy.md)

[Suspend-WssBackupPolicy](./Suspend-WssBackupPolicy.md)

