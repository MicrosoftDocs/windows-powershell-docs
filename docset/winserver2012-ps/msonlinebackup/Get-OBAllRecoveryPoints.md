---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 854F08E2-CAB0-4565-B7CF-D811A26E7954
---

# Get-OBAllRecoveryPoints

## SYNOPSIS
Shows the user a list of recovery points for each successful backup that was completed from a specific server.

## SYNTAX

```
Get-OBAllRecoveryPoints
```

## DESCRIPTION
The **Get-OBAllRecoveryPoints** cmdlet gets all available recovery points.
During recovery after the authentication process is complete, a list of recovery points for each successful backup that was completed from a specific server is shown to the user.
The user can choose to restore data from within a specific recovery point.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-OBAllRecoveryPoints
```

This example gets all recovery points available to recover.

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBBackupInfo

## NOTES

## RELATED LINKS

[00000000-0000-0000-0000-000000000000](00000000-0000-0000-0000-000000000000)

