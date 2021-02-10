---
external help file: WSBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 861E1FC3-13D5-4D49-ABE3-0769B0C688FB
manager: dansimp
---

# Get-WBVirtualMachine

## SYNOPSIS
Gets all virtual machines and components from the backup policy.

## SYNTAX

```
Get-WBVirtualMachine [[-Policy] <WBPolicy>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Get-WBVirtualMachine** cmdlet gets all virtual machines and hv_win8_1 components from the **WBPolicy** object or the physical machine.

## EXAMPLES

### Example 1:
```
PS C:\> Get-WBVirtualMachines
```

This command queries for virtual machines and  hv_win8_2 components on the machine and lists them.

## PARAMETERS

### -Policy
Specifies the backup policy information contained in the **WBPolicy** object to display.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases: 

Required: False
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

### Windows.ServerBackup.Commands.WBPolicy

## OUTPUTS

### Windows.ServerBackup.Commands.WBVirtualMachine[]

## NOTES

## RELATED LINKS



[Add-WBVirtualMachine](./Add-WBVirtualMachine.md)

[Remove-WBVirtualMachine](./Remove-WBVirtualMachine.md)

