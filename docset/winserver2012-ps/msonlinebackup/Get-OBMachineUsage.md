---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 5A36C2B9-10C3-459A-9B45-A7DE75FAEC3C
manager: dansimp
---

# Get-OBMachineUsage

## SYNOPSIS
Gets the amount of storage consumed on mob_name_1 by data backed-up from this server.

## SYNTAX

```
Get-OBMachineUsage
```

## DESCRIPTION
The **Get-OBMachineUsage** cmdlet gets the amount of storage consumed on mob_name_1 by data backed-up from this server.
This would represent the data available across all recoverable points.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-OBMachineUsage
```

This example gets the storage consumed on mob_name_1 by the current protected server.

## PARAMETERS

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBMachineUsage

## NOTES

## RELATED LINKS

[Get-OBMachineSetting](./Get-OBMachineSetting.md)

[Set-OBMachineUsage](00000000-0000-0000-0000-000000000000)

