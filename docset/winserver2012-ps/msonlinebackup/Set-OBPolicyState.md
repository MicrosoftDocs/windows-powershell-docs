---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 9FB0B515-DE34-4B43-A8FA-A4E970C3F895
---

# Set-OBPolicyState

## SYNOPSIS
Sets the PolicyState of the current backup policy object.
The state can be either Valid or Paused.

## SYNTAX

```
Set-OBPolicyState [-Policy] <CBPolicy> [-State] <OMPolicyStates> [-Confirm] [-WhatIf]
```

## DESCRIPTION
This cmdlet can be used to set the current state of the backup policy.
The state can be either Valid or Paused.

A Valid state means that the backups will happen based on the defined schedule and that backups will be retained based on the retention policy.

A Paused state means that backups will not occur according to the defined schedule that the current backups will be retained until the backup policy is changed to Valid state or is deleted.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> $P = Get-OBPolicy
PS C:\> Set-OBPolicyState   $P "Valid"
PS C:\> Set-OBPolicy   $P
```

This example sets the OBPolicyState to Valid and updates the OBPolicy object.

### EXAMPLE 2
```
PS C:\> $P = Get-OBPolicy
PS C:\> Set-OBPolicyState   $P "Paused"
PS C:\> Set-OBPolicy   $P
```

This example sets the OBPolicyState to Paused and updates the OBPolicy object.

### EXAMPLE 3
```
PS C:\> Get-OBPolicy | Set-OBPolicyState -State "Paused" | Set-OBPolicy
```

This example sets the OBPolicyState to Paused and updates the OBPolicy object using pipelines.

## PARAMETERS

### -Policy
Specifies the backup policy (OBPolicy) object on which to set the PolicyState.

```yaml
Type: CBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -State
The current PolicyState of the backup policy.

```yaml
Type: OMPolicyStates
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Internal.CloudBackup.Commands.OBPolicy

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBPolicyState

## NOTES

## RELATED LINKS

[Get-OBPolicy](./Get-OBPolicy.md)

[Set-OBPolicy](./Set-OBPolicy.md)

