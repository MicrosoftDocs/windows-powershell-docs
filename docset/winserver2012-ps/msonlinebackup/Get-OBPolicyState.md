---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 32D99A4A-5C67-4A77-A74C-CF9462FAEE70
manager: dansimp
---

# Get-OBPolicyState

## SYNOPSIS
Gets the PolicyState of the current backup policy.
The state can be either Valid or Paused.

## SYNTAX

```
Get-OBPolicyState [-Policy] <CBPolicy>
```

## DESCRIPTION
This cmdlet can be used to get the current state of the backup policy.
The state can be either Valid or Paused.

A Valid state means that the backups will happen based on the defined schedule and that backups will be retained based on the retention policy.

A Paused state means that backups will not occur according to the defined schedule that the current backups will be retained until the backup policy is changed to Valid state or is deleted.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> $P = Get-OBPolicy
PS C:\> Get-OBPolicyState   $P
```

This example shows how to get the current state of the backup policy.

## PARAMETERS

### -Policy
Specifies the backup policy (OBPolicy) object from which to get the PolicyState.

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

### Microsoft.Internal.CloudBackup.Commands.OBPolicy

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBPolicyState

## NOTES

## RELATED LINKS

[Get-OBPolicy](./Get-OBPolicy.md)
