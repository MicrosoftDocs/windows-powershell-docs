---
author: Kateyanne
external help file: WSBackup_Cmdlets.xml
manager: dansimp
Module Name: WindowsServerBackup
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/windowsserverbackup/add-wbvirtualmachine?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-WBVirtualMachine

## SYNOPSIS
Adds a list of virtual machines to the backup policy.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-WBVirtualMachine [-Policy] <WBPolicy> [-All] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-WBVirtualMachine [-Policy] <WBPolicy> [[-VirtualMachine] <WBVirtualMachine[]>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-WBVirtualMachine** cmdlet adds a list of virtual machines to a backup policy contained in the specified **WBPolicy** object.

## EXAMPLES

### Example 1: Add virtual machines to the backup policy
```
PS C:\>$Policy = Get-WBPolicy PS C:\>$VirtualMachines = Get-WBVirtualMachine PS C:\> Add-WBVirtualMachine -Policy $Policy -VirtualMachine $VirtualMachines
```

This example adds the list of volumes in the **$VirtualMachines** variable to the **WBPolicy** object **$Policy**.

The first command stores the result of the Get-WBPolicy cmdlet in the **$Policy** variable.

The second command stores the result of the **Get-WBVirtualMachine** cmdlet in the **$VirtualMachines** variable.

The third command adds the virtual machines listed in the **$VirtualMachines** variable to the backup policy in the **$Policy** variable.

## PARAMETERS

### -All
Indicates that all virtual machines on the computer are added to the policy.

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
Specifies a **WBPolicy** object that contains the backup policy to update.

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
Specifies an array of one or more virtual machines to add to the **WBPolicy** object.

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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WBVirtualMachine](./Get-WBVirtualMachine.md)

[Remove-WBVirtualMachine](./Remove-WBVirtualMachine.md)



