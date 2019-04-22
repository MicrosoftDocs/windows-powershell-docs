---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 32BF3229-650F-4BCA-A587-4275CE671964
manager: dansimp
---

# Get-OBPolicy

## SYNOPSIS
Gets the current backup policy set for the server.

## SYNTAX

```
Get-OBPolicy
```

## DESCRIPTION
The **Get-OBPolicy** cmdlet gets the current backup policy that is set for the server, including the details about scheduling backups, files included in the backup, and retention policy.

Once the changes have been made to the policy object, the updated policy should be set as the current one using the Set-OBPolicy cmdlet.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-OBPolicy
```

This example returns a saved policy.

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBPolicy[]

## NOTES

## RELATED LINKS

[Set-OBPolicy](./Set-OBPolicy.md)

