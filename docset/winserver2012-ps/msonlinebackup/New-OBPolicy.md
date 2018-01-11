---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 6EBCD1D7-551C-4A2A-8116-4E54C635608F
---

# New-OBPolicy

## SYNOPSIS
Generates an empty OBPolicy object.

## SYNTAX

```
New-OBPolicy
```

## DESCRIPTION
The **New-OBPolicy** cmdlet creates a new, empty backup policy (OBPolicy object).

Other cmdlets can be used to define what items will be included or excluded in backups, when the backups will run, and where backups will be stored.
Then, use the Set-OBPolicy cmdlet to make the new policy the one that will be used for scheduled backups.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>New-OBPolicy
```

This example creates a new empty backup policy.

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBPolicy

## NOTES

## RELATED LINKS

[Set-OBPolicy](./Set-OBPolicy.md)

