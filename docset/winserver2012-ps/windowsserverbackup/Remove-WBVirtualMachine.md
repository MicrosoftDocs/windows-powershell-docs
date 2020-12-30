---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 2543A3EF-3DC4-4783-80A4-B960FAF3DFA6
manager: dansimp
---

# Remove-WBVirtualMachine

## SYNOPSIS
Removes the list of virtual machines from the backup policy.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-WBVirtualMachine [-Policy] <WBPolicy> [-All] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-WBVirtualMachine [-Policy] <WBPolicy> [[-VirtualMachine] <WBVirtualMachine[]>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-WBVirtualMachine** cmdlet removes the list of virtual machines from the backup policy contained in the **WBPolicy** object.

## EXAMPLES

### Example 1: Remove virtual machines from the backup policy
```
PS C:\>$Policy = Get-WBPolicy PS C:\> Remove-WBVirtualMachines $Policy -All
```

This example removes all virtual machines from the backup policy.

The first command calls the Get-WBPolicy cmdlet and assigns the result to the **$Policy** variable.

The second command removes the virtual machines from the backup policy in the **$Policy** variable.

## PARAMETERS

### -All
Indicates whether to remove all virtual machines from the backup contained in the **WBPolicy** object.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy
Specifies the **WBPolicy** object that contains the backup policy to update.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachine
Specifies an array of one or more virtual machines to be removed from the backup policy contained in the **WBPolicy** object.

```yaml
Type: WBVirtualMachine[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 2
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

### Windows.ServerBackup.Commands.WBPolicy

## OUTPUTS

### Windows.ServerBackup.Commands.WBVirtualMachine[]

## NOTES

## RELATED LINKS

[Add-WBVirtualMachine](./Add-WBVirtualMachine.md)

[Get-WBVirtualMachine](./Get-WBVirtualMachine.md)

