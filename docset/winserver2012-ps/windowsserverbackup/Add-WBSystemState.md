---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: D07120D5-2D09-439C-B265-3FA1B5387302
manager: dansimp
---

# Add-WBSystemState

## SYNOPSIS
Adds the system state components to the backup policy.

## SYNTAX

```
Add-WBSystemState [-Policy] <WBPolicy>
```

## DESCRIPTION
The **Add-WBSystemState** cmdlet adds the system state components to a policy contained in the specified **WBPolicy** object.
Use backups created through this policy to perform a system state recovery.

The **WBPolicy** object must be in edit mode.
To put the **WBPolicy** object in edit mode for a policy that is set as the scheduled backup policy, use the Get-WBPolicy cmdlet with the **Editable** parameter.
The New-WBPolicy cmdlet creates a new **WBPolicy** object that is already in edit mode.

To use this or any other Windows Server 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Add system state to the backup policy
```
PS C:\>$Policy = Get-WBPolicy PS C:\> Add-WBSystemState -Policy $Policy
```

This example adds a setting to the **WBPolicy** object to include the system state in backups that you create by using this policy.

The first command stores the result of the **Get-WBPolicy** cmdlet in the variable named **$Policy**.

The second command adds the system state to the backup policy in the **$Policy** variable.

## PARAMETERS

### -Policy
Specifies a **WBPolicy** object that contains the backup policy to update.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### WBPolicy
The Add-WBSystemState**Add-WBSystemState** cmdlet accepts a **WBPolicy** object as input.

## OUTPUTS

### None
None

## NOTES

## RELATED LINKS

[Get-WBPolicy](./Get-WBPolicy.md)

[Get-WBSystemState](./Get-WBSystemState.md)

[Remove-WBSystemState](./Remove-WBSystemState.md)

