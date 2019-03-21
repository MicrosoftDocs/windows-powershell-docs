---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: EB5C55D0-F158-4BAD-8363-7C7CDA8E882C
ms.manager: dansimp
---

# Get-OBRetentionPolicy

## SYNOPSIS
Gets the current retention policy for backups from the backup policy (OBPolicy object).

## SYNTAX

```
Get-OBRetentionPolicy [-Policy] <CBPolicy>
```

## DESCRIPTION
The **Get-OBRetentionPolicy** cmdlet gets the current retention policy for backups from the backup policy (OBPolicy object).
The retention policy allows the number of retention days to be set to one of the following values: `7`, `15`, `30`.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-OBPolicy | Get-OBRetentionPolicy
```

This example returns a saved retention policy.

## PARAMETERS

### -Policy
Specify the OBPolicy object for which the OBRetentionPolicy should be retrieved.

```yaml
Type: CBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBPolicy

## NOTES

## RELATED LINKS

[Get-OBPolicy](./Get-OBPolicy.md)

