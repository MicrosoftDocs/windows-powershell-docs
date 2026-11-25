---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: wsbcmdlet.dll-Help.xml
Module Name: WindowsServerBackup
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/windowsserverbackup/remove-wbvirtualmachine?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WBVirtualMachine
---

# Remove-WBVirtualMachine

## SYNOPSIS
Removes the list of virtual machines from the backup policy.

## SYNTAX

### WBVirtualMachine
```
Remove-WBVirtualMachine [-Policy] <WBPolicy> [[-VirtualMachine] <WBVirtualMachine[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### All
```
Remove-WBVirtualMachine [-Policy] <WBPolicy> [-All] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-WBVirtualMachine** cmdlet removes the list of virtual machines from the backup policy contained in the **WBPolicy** object.

## EXAMPLES

### Example 1: Remove virtual machines from the backup policy
```
PS C:\> $Policy = Get-WBPolicy
PS C:\> Remove-WBVirtualMachine $Policy -All
```

This example removes all virtual machines from the backup policy.

The first command calls the [Get-WBPolicy](./Get-WBPolicy.md) cmdlet and assigns the result to the $Policy variable.

The second command removes the virtual machines from the backup policy stored in the $Policy variable.

## PARAMETERS

### -All
Indicates that this cmdlet removes all virtual machines from the backup contained in the **WBPolicy** object.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Policy
Specifies the **WBPolicy** object that contains the backup policy that this cmdlet updates.

```yaml
Type: WBPolicy
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualMachine
Specifies an array of one or more virtual machines that this cmdlet removes from the backup policy contained in the **WBPolicy** object.

```yaml
Type: WBVirtualMachine[]
Parameter Sets: WBVirtualMachine
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Windows.ServerBackup.Commands.WBVirtualMachine[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Add-WBVirtualMachine](./Add-WBVirtualMachine.md)

[Get-WBVirtualMachine](./Get-WBVirtualMachine.md)

[Get-WBPolicy](./Get-WBPolicy.md)

