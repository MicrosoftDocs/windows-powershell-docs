---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: BF74FF84-49EE-4D60-8C82-83E6B9C8D8CA
manager: dansimp
---

# Remove-WBFileSpec

## SYNOPSIS
Removes a backup file specification from a backup policy.

## SYNTAX

```
Remove-WBFileSpec [-Policy] <WBPolicy> [-FileSpec] <WBFileSpec> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-WBFileSpec** cmdlet removes a **WBFileSpec** object that contains a backup file specification from a **WBPolicy** object that contains a backup policy.
A backup file specification contains a list of items to include in or exclude from backups that use the backup policy.

Before you can remove a backup file specification from a **WBPolicy** object, you must put the **WBPolicy** object in edit mode.
To put the **WBPolicy** object in edit mode for a policy that you set as the scheduled backup policy, use the Get-WBPolicy cmdlet with the **-Editable** parameter.
The New-WBPolicy cmdlet creates a new **WBPolicy** object that is already in edit mode.

To use Windows Server® 2012 Backup cmdlets, you must be a member of the Administrators group or Backup Operators group.

## EXAMPLES

### Example 1: Remove a backup file specification from a backup policy
```
PS C:\>$Filespeclist = Get-WBFileSpec -Policy $policy PS C:\>Remove-WBFileSpec -Policy $policy -FileSpec $Filespeclist[1]

None
```

This example removes a backup file specification from a backup policy.

The first command gets a list of the backup file specifications from the backup policy in the variable named **$Policy**.
The command assigns the backup file specifications to the array in the variable named **$Filespeclist**.

The second command removes the backup file specification in the first element of **$Filespeclist** from the policy in **$Policy**.

## PARAMETERS

### -FileSpec
Specifies a backup file specification object to remove from the **WBPolicy** object.

```yaml
Type: WBFileSpec
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Policy
Specifies a backup policy object that contains the backup policy to update.

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

### WBFileSpec, WBPolicy
The Remove-WBFileSpec cmdlet removes a **WBFileSpec** object from a **WBPolicy** object.

## OUTPUTS

### None
None

## NOTES

## RELATED LINKS

[Get-WBFileSpec](./Get-WBFileSpec.md)

[Get-WBPolicy](./Get-WBPolicy.md)

